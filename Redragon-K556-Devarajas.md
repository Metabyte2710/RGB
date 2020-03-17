USB HID, 64-byte packets

Start: 04 01 00 01

End: 04 02 00 02

Custom data: 04 0F 03 06 03 09 00 00 FF FF FF

The 03 bytes seem to indicate number of color bytes

The 09 seems to be the offset in bytes - start at 00

| Index | Value | Description     |
| ----- | ----- | --------------- |
| 0x00  | 0x04  |                 |
| 0x01  | 0x0F  |                 |
| 0x02  | 0x03  | Number of bytes |
| 0x03  | 0x06  |                 |
| 0x04  | 0x03  | Number of bytes |
| 0x05  | 0x09  | Byte offset     |
| 0x06  | 0x00  |                 |
| 0x07  | 0x00  |                 |
| 0x08+ | 0xXX  | RGB data        |