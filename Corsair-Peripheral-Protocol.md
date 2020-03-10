# Corsair NXP Protocol Version 2
## This page has been copied from ckb-next, original [here](https://github.com/ckb-next/ckb-next/wiki/Corsair-Protocol)

I (@CalcProgrammer1) have copied this document here to make some additions and corrections as I implement the Corsair protocol in OpenRGB.  Original document is credit to @ZirconiumX on GitHub.

**If you have a Corsair keyboard or mouse and wish to help with this document, please file an issue mentioning @ZirconiumX and this wiki page.**

## Guidance

If bytes are omitted from the response, it means that we don't think they matter.

If we aren't sure what a command does, we'll put the dubious command in *italics*.

## What we know so far

All packets have a 64 byte payload, padded with zeroes.
The first four bytes of the command are echoed in the response packet.
The protocol is poll based - the mouse may reply to an `0e` command with an arbitrary amount of `01` events terminated with an `03` event before replying.
The protocol uses USB URB interrupts - URB control packets work on most devices, but not on the K95 Platinum.

- `01` - Event from device to host.
- `03` - End of event stack indicator.
- `07` - Write command from host to device - does not get a reply from the board.
- `0e` - Read command from host to device - gets a reply from the board.
- `7f` - Multiple packet stream from host to device - used as a payload in firmware update and colour update.

## Host to device

## `07` fields - write property

### `07 02` - Reset

### `07 02 00` - Medium reset

So named because it takes an amount of time in between the fast reset and the slow reset. 

### `07 02 01` - Fast reset

This seems to be a quick-ish reset.

### `07 02 aa` - Reboot to bootloader

This reboots to the built-in bootloader, appearing as a virtual FAT12 device. Don't try to write to the bootloader through this on Linux at least - the device doesn't take write reordering very well.

### `07 02 f0` - Slow reset

This takes about a second to reset. It's sent after firmware updating, for example.

### `07 04` - Special function control

### `07 04 01` - Special function hardware control

On mice, this makes the physical DPI and sniper buttons control the DPI settings, and the mouse will report an amplified mouse movement accordingly. On keyboards, this lets the hardware control the M-keys. This is the default in HID mode.

### `07 04 02` - Special function software control

On mice, this makes the physical DPI and sniper buttons generate events, but the mouse will do nothing about them by itself. On keyboards, this generates driver events for the M-keys. This is the default in Corsair mode.  On the Polaris MM800 mousepad, this command must be sent before RGB commands apply.

### *`07 05`* - Lighting control

### *`07 05 01`* - Switch to hardware lighting control

The ckb code says this is meant to enable hardware lighting control, like when the device comes out of reset. However, I can't get anything from it. Perhaps it requires you to set a colour and then switch it into hardware mode?

### *`07 05 02 00 0X`* - Switch to software lighting control

**This should be your second packet.**

The ckb code says this is meant to enable software lighting control, like when the device is used by CUE. However, it just turns off all the lights.

`X` needs to be `3` on keyboards. For mice, `X` needs to be `1` to enable lighting, and `0` to disable it.

### `07 13 1X 01 RR GG BB` - Write Xth zone hardware profile colour

`RR`, `GG` and `BB` are the red, green and blue bytes. Note that it does not change the lighting colour, that has to be done with a `07 22` packet.

### *`07 22 ZZ 01`* - Submit mouse colour change

Packet payload is a stream of `NN RR GG BB` bytes for each lighting zone - `NN` is the lighting zone number, and `RR`, `GG` and `BB` are the red, green and blue bytes respectively. `ZZ` is the number of lighting zones.

### *`07 27 00 00 NN`* - Submit keyboard colour change - 9 bit colour

Must be preceded by a stream of [`7f` packets](https://github.com/mattanger/ckb-next/wiki/Corsair-Protocol#7f-nn-ss-00---write-multiple-packet-stream), in the sequence of red values per key (one byte, least significant three bits of colour), followed by green (same format), followed by blue (same format). The bytes must be contiguous - the green bytes must start at the end of the red bytes, even if this is in the middle of a packet.

`NN` indicates the number of bytes in the `7f` packet stream payloads (60 byte payload per packet) - must be a multiple of 3 (for red, green and blue).

### *`07 28 0C 0N 0F`* - Submit keyboard colour change - 24 bit colour

Must be preceded by a stream of [`7f` packets](https://github.com/mattanger/ckb-next/wiki/Corsair-Protocol#7f-nn-ss-00---write-multiple-packet-stream), in the sequence of:

`C` is the colour type, `N` is the number of packets (not bytes!) for this colour, `F` is a finish marker - `1` if not finished, `2` if finished. If setting the keyboard to a single static colour, for example blue, it is not necessary to send packets for red and green (this is actually how the corsair protocol behaves) and `F` is set to `2`; that said, sending subsequent red and green packets would result in layering regardless. Below is an example of a layered RGB colour change. 

- Red values per key (one byte of colour) in 3 `7f` packets.
- `07 28 01 03 01` - `C` for red is `1`, `0N` is number of packets for this colour - `3`, `0F` is `1` - packets are not finished.
- Green values per key (one byte of colour) in 3 `7f` packets.
- `07 28 02 03 01` - `C` for green is `2`, `0N` is number of packets for this colour - `3`, `0F` is `1` - packets are not finished.
- Blue values per key (one byte of colour) in 3 `7f` packets.
- `07 28 03 03 02` - `C` for blue is `3`, `0N` is number of packets for this colour - `3`, `0F` is `2` - packet stream is finished.

## `0e` fields - read property

### `0e 01` - Firmware identification.

**This should be your first packet!**

ckb-next only parses from the first 16 bytes. This packet seems to have two forms, which diverge at the 21st byte according to whether the device is a keyboard or mouse.

Example response (common):
```
0e [Read command]
01 [Firmware information]
00 [Invalid bytes here from the host are accepted and ignored]
00 [Invalid bytes here from the host are accepted and ignored]
01 [??? - Possibly 16.8M colour support?]
01 [???]
00 [???]
01 [???]
06 [Firmware version low byte]
02 [Firmware version high byte - firmware is 2.06]
04 [Bootloader version low byte]
00 [Bootloader version high byte - bootloader is v4]
1c [Corsair USB Vendor ID low byte]
1b [Corsair USB Vendor ID high byte - Corsair's USB vendor ID is 1b1c]
2e [Corsair USB Product ID low byte]
1b [Corsair USB Product ID high byte - 1b2e is the M65 Pro RGB Mouse]
01 [Poll rate in milliseconds]
01 [???]
01 [???]
01 [???]
30 [???]
```

Continuation from a keyboard:
```
c0 [??? - keyboard identification byte?]
ff [???] 
40 [???]
00 [???]
03 [???]
00 [???]
00 [???]
00 [???]
02 [??? - varies between keyboards]
04 [??? - varies between keyboards]
01 [??? - varies between keyboards]
02 [??? - varies between keyboards]
```

Continuation from a mouse:
```
c1 [??? - mouse identification byte?]
ff [???]
40
01
56 [Bitmask of the lighting zones on the mouse - with the LSB as zeroth bit, this has zones 1, 2, 4 and 6]
00
01
01
00
00
00
00
00
00
00
00
01
00
00
01
00
00
00
01
00
01
aa
00
6c
dc
02
```

Continuation from a mousepad:
```
c2 [??? - mousepad identification byte?]
ff [???] 
40 
00
00
00
...
```

### *`0e 0e`* - ???

This is a bool.

Example response:
```
0e [Read command]
0e [???]
00 [??? - seems to be ignored]
00 [??? - seems to be ignored]
00 [??? - 0 for my M65 Pro, 1 for @l2y's Strafe RGB]
```

### `0e 13` - Mouse-related functions (we think)

### *`0e 13 01 00`*, *`0e 13 01 01`* - ???

This seems to be multiple booleans.

Example response:
```
0e [Read command]
13 [Mouse]
01 [???]
00 [???]
01 [??? - bool?]
01 [??? - bool?]
```

### `0e 13 02` - Mouse DPI.

There are six mouse DPI modes - sniper mode at 0, and 5 user-selectable modes from 1-6.

### `0e 13 02 00` - Mouse DPI indicator mode - note this is not the same as the DPI mode.

Example response:
```
0e [Read command]
13 [Mouse]
02 [DPI]
00 [DPI Indicator mode]
02 [User mode 2]
```

### `0e 13 02 01` - Mouse DPI mode.

Example response:
```
0e [Read command]
13 [Mouse]
02 [DPI]
01 [DPI Mode]
02 [User mode 2]
```

### *`0e 13 03 00`*, `0e 13 03 01` - Mouse lift height.

There are 4 lift height modes, from Low at 1 to High at 5. Anything outside this range should be accepted, but assumed to be Low.

Example response:
```
0e [Read command]
13 [Mouse]
03 [Lift height]
01 [??? - the mouse accepts 0 and 1, but doesn't reply to anything outside of that]
02 [Medium lift height]
```

### *`0e 13 04 00`*, `0e 13 04 01` - Mouse angle snap.

Mouse angle snap is either off (0) or on (1).

Example response:
```
0e [Read command]
13 [Mouse]
04 [Angle snap]
01 [??? - the mouse accepts 0 and 1, but doesn't reply to anything outside of that]
00 [Angle snap is off]
```

### *`0e 13 05 00`*, `0e 13 05 01` - DPI enabled bitmask.

Returns a bit mask of all enabled DPI settings, where the Nth bit is set if the Nth DPI setting is enabled.

Example response:
```
0e [Read command]
13 [Mouse]
05 [DPI bitmask]
01 [??? - the mouse accepts 0 and 1 but doesn't reply to anything outside of that]
3f [All six DPI modes are enabled]
```

### *`0e 13 06 00`*, *`0e 13 06 01`* - ???

This might return a percentage? But of what?

Example response:
```
0e [Read command]
13 [Mouse]
06 [???]
00 [???]
64 [100 - I think this is a percentage, but of what?]
```

### *`0e 13 07 00`*, *`0e 13 07 01`* - ???

This seems to be a boolean.

Example response:
```
0e [Read command]
13 [Mouse]
07 [???]
00 [???]
01 [I think this is a bool, but I need to dig more.]
```

### *`0e 13 0a 00`*, *`0e 13 0a 01`* - ???

This could be a boolean? Or a int.

Example response:
```
0e [Read command]
13 [Mouse]
0a [???]
00 [???]
00 [??? - Helpful, I know, but it *does* return something]
```

### *`0e 13 0b 00`*, *`0e 13 0b 01`* - ???

This is a bool. It's set with `... 01` but clear with `... 00`.

Example response:
```
0e [Read command]
13 [Mouse]
0b [???]
01 [???]
01 [A bool, I think.]
```

### *`0e 13 0c 00`*, *`0e 13 0c 01`* - ???

This is an int of some form, I think. It gives an int with `... 01`, but zeroes with `... 00`.

Example response:
```
0e [Read command]
13 [Mouse]
0c [???]
01 [???]
0a [???]
ff [??? - 0xff0a (converting endian) is 65,290. Any ideas?]
```

### `0e 13 1X 01` - Query Xth zone hardware profile colour

Returns the current colour of the Xth zone. It responds to zone 0 and 1 on my mouse.

Example response:
```
0e [Read command]
13 [Mouse]
11 [Lighting zone 1 (logo light) hardware colour]
01 [???]
ff [Colour red channel]
ff [Colour green channel]
00 [Colour blue channel]
```

### *`0e 13 dX 00`*, `0e 13 dX 01` - Query Xth DPI zone info.

This returns the X and Y DPI, as well as the DPI light RGB info.

Example response:
```
0e [Read command]
13 [Mouse]
d2 [DPI zone 2 info]
01 [???]
00 [???]
dc [X DPI low byte]
05 [X DPI high byte]
dc [Y DPI low byte]
05 [Y DPI high byte]
ff [DPI light red channel]
ff [DPI light green channel]
ff [DPI light blue channel]
```

### `0e 15` - mode information

### `0e 15 01 0X` - Query Xth mode ID

This returns a 16-byte GUID, plus a 4-byte "modified" flag for the Xth mode.
With the exception of the K95, most keyboards and mice have only one mode.

Example response:
```
0e [Read command]
15 [Mode ID]
01 [??? - required to be 1]
01 [Query 1st mode ID]
<16 byte little endian GUID, omitted for brevity>
<4 byte little endian modified flag, omitted for brevity>
```

### `0e 16` - mode names

### `0e 16 01 0X` - Query Xth mode name

This returns a null-terminated 16 character UTF-16LE string.

Example response:
```
0e [Read command]
16 [Mode name]
01 [??? - required to be 1]
01 [Query 1st mode name]
48
00 [U+0048 'H']
77 
00 [U+0077 'w']
4d 
00 [U+004d 'M']
<etc for another 26 bytes>
```

## `7f NN SS 00` - Write multiple packet stream

When the protocol needs to send a message that is more than a 64-byte packet long, it sends a series of `7f` packets containing the data, with an incrementing nonce in `NN`, and the data length in `SS` (no more than 60 bytes per packet). This is used in firmware update, for transmitting the firmware packets, and in updating the colours, because there are so many keys.