USB HID, 64-byte packets.  Every packet should perform both an HID write operation and an HID read operation sequentially.  Do not use feature reports.

Every packet begins with:

| Index | Value               |
| ----- | ------------------- |
| 0x00  | 0x04                |
| 0x01  | 16-bit Checksum LSB |
| 0x02  | 16-bit Checksum MSB |
| 0x03  | Command Byte        |

The checksum simply adds together all of the bytes in the packet excluding the first three.

# Begin Command (0x01)

| Index | Value               |
| ----- | ------------------- |
| 0x00  | 0x04                |
| 0x01  | Checksum LSB (0x01) |
| 0x02  | Checksum MSB (0x00) |
| 0x03  | 0x01                |

# End Command (0x02)

| Index | Value               |
| ----- | ------------------- |
| 0x00  | 0x04                |
| 0x01  | Checksum LSB (0x02) |
| 0x02  | Checksum MSB (0x00) |
| 0x03  | 0x02                |

# Unknown Command (0x03)

This is set when changing profiles.  It sets byte index 0x04 to value 0x2C.  Possibly a multi-byte data read.  Also sent when opening the app.

# Unknown Command (0x04)

This is set when changing profiles.  Appears to be a multi-packet data transfer, though is only called once with size 0x2C (if format same as 0x11).

# Unknown Command (0x05)

This is set when changing profiles.  It sets byte index 0x04 to value 0x38.  Appears to be a multi-packet data transfer similar to 0x11.

# Set Parameter Command (0x06)

| Index | Value | Description            |
| ----- | ----- | ---------------------- |
| 0x00  | 0x04  |                        |
| 0x01  | 0xNN  | Checksum LSB           |
| 0x02  | 0xNN  | Checksum MSB           |
| 0x03  | 0x06  |                        |
| 0x04  | 0xNN  | Parameter Byte Count   |
| 0x05  | 0xNN  | Parameter Index        |
| 0x06  | 0x00  |                        |
| 0x07  | 0x00  |                        |
| 0x08  | 0xNN  | Parameter Byte 1       |
| 0x09  | 0xNN  | Parameter Byte 2       |
| 0x0A  | 0xNN  | Parameter Byte 3       |

## Parameters

| Parameter Index | Parameter Bytes | Parameter Description          |
| --------------- | --------------- | ------------------------------ |
| 0x00            | 1               | Mode (See Modes table)         |
| 0x01            | 1               | Brightness (0-5)               |
| 0x02            | 1               | Speed (Slow: 5, Fast: 0)       |
| 0x03            | 1               | Direction (R: 0, L: 1)         |
| 0x04            | 1               | Random Color Flag (0/1)        |
| 0x05            | 3               | Mode Color (RGB)               |
| 0x0F            | 1               | Polling Rate (See table)       |
| 0x11            | 1               | Surmount mode color (see table)|

## Modes

The effects all have very strange names.  I'm pretty sure the people who wrote the app didn't speak very good English and used some form of translator and/or autocorrect to come up with some of these atrocities.

| Effect name            | Value | Description                                         |
| ---------------------- | ----- | --------------------------------------------------- |
| Go with the stream     | 0x01  | Rainbow Wave                                        |
| Clouds fly             | 0x02  | Rainbow Wave, but stretched out                     |
| Winding paths          | 0x03  | Color Wheel                                         |
| The trial of light     | 0x04  | Spectrum Cycle                                      |
| Breathing              | 0x05  | Breathing (at least they got this right)            |
| Normally on            | 0x06  | Static                                              |
| Pass without trace     | 0x07  | Reactive (single key lights when pressed)           |
| Ripple graff           | 0x08  | Reactive with ripple from pressed key               |
| Fast run without trace | 0x09  | Reactive with ripple only on key's row              |
| Swift action           | 0x0A  | I think Razer calls this Starlight                  |
| Flowers blooming       | 0x0B  | Spectrum Cycle per key, very colorful               |
| Snow winter jasmine    | 0x0C  | Rainbow Wave, but vertical                          |
| Hurricane              | 0x0D  | Zigzag lines from center of keyboard                |
| Accumulate             | 0x0E  | Colors come in from outer edges and group in middle |
| Digital times          | 0x0F  | A slower version of Swift action (starlight)        |
| Both ways              | 0x10  | Visor effect that scans back and forth              |
| Surmount               | 0x11  | Seems to fade between hues of selected color        |
| Fast and the Furious   | 0x12  | Circular rainbow wave that moves to center          |
| Coastal                | 0x14  | Per-key control (did they mean "Custom"?)           |

## Surmount Mode Colors

| Surmount Index | Surmount Color |
| -------------- | -------------- |
| 0x00           | Red            |
| 0x01           | Yellow         |
| 0x02           | Green          |
| 0x03           | Blue           |

## Polling Rates

| Polling Rate Index | Polling Rate Setting |
| ------------------ | -------------------- |
| 0x00               | 125Hz                |
| 0x01               | 250Hz                |
| 0x02               | 500Hz                |
| 0x03               | 1000Hz               |

# Unknown Command (0x07)

Sent when opening the app.  Seems to be a multi-packet data stream with size 0x38 per packet.  Perhaps this is the key map?  21 packets total.  Three of them have size 0x2A per packet (6 0x38 size followed by 1 0x2A size, repeat 3 times).  All data bytes are zero.  Possibly a read.

# Unknown Command (0x08)

Sent when changing a key binding.  Seems to be a multi-packet data stream with size 0x38 per packet.  Perhaps this is the key map?  21 packets total.  Three of them have size 0x2A per packet (6 0x38 size followed by 1 0x2A size, repeat 3 times).

# Unknown Command (0x09)

Sent when opening the app.

# Unknown Command (0x0A)

Sent when changing a key binding

# Unknown Read Data Command (0x0F)

Sent when opening the app.  Seems to be a multi-packet data stream with size 0x38 per packet.  7 packets total, with the last packet having a size of 0x2A instead of 0x38.  All data bytes are zero.  I think this is reading out color data.

# Read Custom Color Data Command? (0x10)

Changing profile sends this command with all zeros, but it seems to follow the same number of bytes and offset format of command 0x11.  Perhaps a direct color mode?  It could be some other per-key data as well.

# Write Custom Color Data Command (0x11)

| Index | Value | Description        |
| ----- | ----- | ------------------ |
| 0x00  | 0x04  |                    |
| 0x01  | 0x11  | Checksum LSB       |
| 0x02  | 0x36  | Checksum MSB       |
| 0x03  | 0x11  |                    |
| 0x04  | 0x36  | Number of bytes    |
| 0x05  | 0x00  | Byte offset LSB    |
| 0x06  | 0x00  | Byte offset MSB    |
| 0x07  | 0x00  |                    |
| 0x08+ | 0xXX  | RGB data           |

# Keymap

| Color data index | Key          |
| ---------------- | ------------ |
| 0x00             | Escape       |
| 0x01             | F1           |
| 0x02             | F2           |
| 0x03             | F3           |
| 0x04             | F4           |
| 0x05             | F5           |
| 0x06             | F6           |
| 0x07             | F7           |
| 0x08             | F8           |
| 0x09             | F9           |
| 0x0A             | F10          |
| 0x0B             | F11          |
| 0x0C             | F12          |
| 0x0D             |              |
| 0x0E             | Print Screen |
| 0x0F             | Scroll Lock  |
| 0x10             | Pause/Break  |
| 0x11             |              |
| 0x12             |              |
| 0x13             |              |
| 0x14             |              |
| 0x15             | `/~          |
| 0x16             | 1            |
| 0x17             | 2            |
| 0x18             | 3            |
| 0x19             | 4            |
| 0x1A             | 5            |
| 0x1B             | 6            |
| 0x1C             | 7            |
| 0x1D             | 8            |
| 0x1E             | 9            |
| 0x1F             | 0            |
| 0x20             | -/_          |
| 0x21             | =/+          |
| 0x22             | Backspace    |
| 0x23             | Insert       |
| 0x24             | Home         |
| 0x25             | Page Up      |
| 0x26             | Num Lock     |
| 0x27             | Num Pad /    |
| 0x28             | Num Pad *    |
| 0x29             | Num Pad -    |
| 0x30             | Tab          |
| 0x31             | Q            |
| 0x32             | W            |
| 0x33             | E            |
| 0x34             | R            |
| 0x35             | T            |
| 0x36             | Y            |
| 0x37             | U            |
| 0x38             | I            |
| 0x39             | O            |
| 0x3A             | P            |
| 0x3B             | [/{          |
| 0x3C             | ]/}          |
| 0x3D             | \/|          |
| 0x3E             | Delete       |
| 0x3F             | End          |
| 0x40             | Page Down    |
| 0x41             | Num Pad 7    |
| 0x42             | Num Pad 8    |
| 0x43             | Num Pad 9    |
| 0x44             | Num Pad +    |
| 0x45             | Caps Lock    |
| 0x46             | A            |
| 0x47             | S            |
| 0x48             | D            |
| 0x49             | F            |
| 0x4A             | G            |
| 0x4B             | H            |
| 0x4C             | J            |
| 0x4D             | K            |
| 0x4E             | L            |
| 0x4F             | ;/:          |
| 0x50             | '/"          |
| 0x51             |              |
| 0x52             | Enter        |
| 0x53             |              |
| 0x54             |              |
| 0x55             |              |
| 0x56             | Num Pad 4    |
| 0x57             | Num Pad 5    |
| 0x58             | Num Pad 6    |
| 0x59             |              |
| 0x5A             | Left Shift   |
| 0x5B             |              |
| 0x5C             | Z            |
| 0x5D             | X            |
| 0x5E             | C            |
| 0x5F             | V            |
| 0x60             | B            |
| 0x61             | N            |
| 0x62             | M            |
| 0x63             | ,/<          |
| 0x64             | ./>          |
| 0x65             | /?           |
| 0x66             |              |
| 0x67             | Right Shift  |
| 0x68             |              |
| 0x69             | Up Arrow     |
| 0x6A             |              |
| 0x6B             | Num Pad 1    |
| 0x6C             | Num Pad 2    |
| 0x6D             | Num Pad 3    |
| 0x6E             | Num Pad Enter |
| 0x6F             | Left Control |
| 0x70             | Windows Key  |
| 0x71             | Left Alt     |
| 0x72             | Space Bar    |
| 0x73             | Right Alt    |
| 0x74             | Function     |
| 0x75             | Context      |
| 0x76             |              |
| 0x77             | Right Control |
| 0x78             |              |
| 0x79             |              |
| 0x7A             |              |
| 0x7B             |              |
| 0x7C             |              |
| 0x7D             | Left Arrow   |
| 0x7E             | Down Arrow   |
| 0x7F             | Right Arrow  |
| 0x80             |              |
| 0x81             | Num Pad 0    |
| 0x82             | Num Pad .    |
| 0x83             |              |