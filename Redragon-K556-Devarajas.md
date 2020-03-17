USB HID, 64-byte packets

Start: 04 01 00 01

End: 04 02 00 02

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