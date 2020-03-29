USB HID, 64-byte packets.  Every packet should perform both an HID write operation and an HID read operation sequentially.  Do not use feature reports.

# Begin Command Set

| Index | Value |
| ----- | ----- |
| 0x00  | 0x04  |
| 0x01  | 0x01  |
| 0x02  | 0x00  |
| 0x03  | 0x01  |

# End Command Set

| Index | Value |
| ----- | ----- |
| 0x00  | 0x04  |
| 0x01  | 0x02  |
| 0x02  | 0x00  |
| 0x03  | 0x02  |

Custom data: 04 0F 03 06 03 09 00 00 FF FF FF

The 03 bytes seem to indicate number of color bytes

The 09 seems to be the offset in bytes - start at 00

| Index | Value | Description        |
| ----- | ----- | ------------------ |
| 0x00  | 0x04  |                    |
| 0x01  | 0x11  | Byte offset + 0x11 |
| 0x02  | 0x36  | Number of bytes    |
| 0x03  | 0x11  |                    |
| 0x04  | 0x36  | Number of bytes    |
| 0x05  | 0x00  | Byte offset LSB    |
| 0x06  | 0x00  | Byte offset MSB    |
| 0x07  | 0x00  |                    |
| 0x08+ | 0xXX  | RGB data           |

Polling rate 125Hz - 04 16 00 06 01 0f 00 00 00

Polling rate 250Hz - 04 17 00 06 01 0f 00 00 01

Polling rate 500Hz - 04 18 00 06 01 0f 00 00 02

Polling rate 1000Hz - 04 19 00 06 01 0f 00 00 03

# Modes

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
| Surmount               |       | Seems to fade between hues of selected color        |
| Both ways              | 0x10  | Visor effect that scans back and forth              |
| Fast and the Furious   | 0x12  | Circular rainbow wave that moves to center          |
| Coastal                | 0x14  | Per-key control (did they mean "Custom"?)           |

## Parameters

| Parameter Index | Parameter Bytes | Parameter Description   |
| --------------- | --------------- | ----------------------- |
| 0x00            | 1               | Mode (See Modes table)  |
| 0x01            | 1               | Brightness (0-5)        |
| 0x02            | 1               | Speed (Slow: 5, Fast: 0)|
| 0x03            | 1               | Direction (R: 0, L: 1)  |
| 0x04            | 1               | Random Color Flag (0/1) |
| 0x05            | 3               | Mode Color (RGB)        |

## Set Parameter

| Index | Value | Description            |
| ----- | ----- | ---------------------- |
| 0x00  | 0x04  |                        |
| 0x01  | 0xNN  | Parameter value + 0x08 |
| 0x02  | 0x00  |                        |
| 0x03  | 0x06  |                        |
| 0x04  | 0xNN  | Parameter Byte Count   |
| 0x05  | 0xNN  | Parameter Index        |
| 0x06  | 0x00  |                        |
| 0x07  | 0x00  |                        |
| 0x08  | 0xNN  | Parameter Byte 1       |
| 0x09  | 0xNN  | Parameter Byte 2       |
| 0x0A  | 0xNN  | Parameter Byte 3       |

## Surmount Modes

These modes use a slightly different protocol

Effect "Surmount" - Red         - 04 18 00 06 01 11 00 00 00

Effect "Surmount" - Yellow      - 04 19 00 06 01 11 00 00 01

Effect "Surmount" - Green       - 04 1A 00 06 01 11 00 00 02

Effect "Surmount" - Blue        - 04 1B 00 06 01 11 00 00 03

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