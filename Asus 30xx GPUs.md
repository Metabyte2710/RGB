# Asus 30XX GPU protocol

The communication with these device is very different for writing bytes for some registers. There seem to be complex commands for settings modes and colors of RGB lighting written to device `x67`.

## Writing colors

The command for writing colors seems to be

``` txt
Write to Reg x00: x81 x60
Write to Reg x03: x0B RR BB GG RR GG BB RR BB GG RR BB
Write to Reg x03: x0B GG RR GG BB RR BB GG RR BB GG RR
Write to Reg x03: x0B BB GG RR BB GG RR GG BB RR BB GG
Write to Reg x03: x0B RR BB GG RR GG BB RR BB GG RR BB
Write to Reg x03: x0B GG RR BB GG RR GG BB RR BB GG RR
Write to Reg x03: x0B BB GG RR BB GG RR GG BB RR BB GG
Write to Reg x03: x0B RR BB GG RR GG BB RR BB GG RR BB
Write to Reg x03: x0B GG RR GG BB RR BB GG RR BB GG RR
Write to Reg x03: x02 BB GG
Write to Reg x00: x80 x2F
Write to Reg x01: x01
```

where consecutive `RR GG BB` are 30 series of bytes to set each individual RGB, regardless number of addressable RGBs on the cart (note: ASUS TUF card seems to have 4 of them, ASUS ROG Strix has quite a bit more).

Each line written to `x03` has the form of `[Amount of bytes] [bytes]...` but that doesn't seem to change from command to command.

## Writing modes

``` txt
Write to Reg x00: x80 x20
Write to Reg x02: SS MM
Write to Reg x00: x80 x24
Write to Reg x01: DD
Write to Reg x00: x80 x2F
Write to Reg x01: x01
```

Where `MM` is the mode ID, which so on for OEM included modes seem to be

| Mode           | ID   |
|----------------|------|
| Static         | 0x01 |
| Breathing      | 0x02 |
| Color cycle    | 0x04 |
| Rainbow        | 0x05 |
| Comet          | 0x07 |
| Glowing yoyo   | 0x0C |
| Starry Night   | 0x0D |
| Flash and dash | 0x0A |

And `DD` is direction applied to some of effects

| Direction | ID    |
|-----------|-------|
|Left       | 0x00  |
|Right      | 0x01  |

And `SS` is speed

| Direction | ID   |
|-----------|------|
|Slow       | 0x05 |
|Normal     | 0x00 |
|Fast       | 0xFB |

In OEM all mode settings are followed by color set instruction even if it is not settable in the mode and has no influence. if color is not included in the mode, the OEM outputs red (RR=FF, GG=00, B=00) for the setting.

## OEM Settings

This is a table of what settings OEM allows for each mode.

| Mode           | Color | Speed | Direction | Brightness |
|----------------|-------|-------|-----------| ---------- |
| Static         | Yes   | No    | No        | Yes        |
| Breathing      | Yes   | No    | No        | Yes        |
| Color cycle    | No    | No    | No        | No         |
| Rainbow        | No    | Yes   | Yes       | No         |
| Comet          | Yes   | No    | No        | No         |
| Glowing yoyo   | No    | No    | No        | No         |
| Flash and dash | No    | No    | No        | No         |
