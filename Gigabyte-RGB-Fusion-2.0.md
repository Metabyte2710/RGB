Gigabyte's second generation of RGB Fusion enabled motherboards use an ITE8297 controller that enumerates a USB device at 048D:8297.  This device is controlled using the HID protocol.

Report ID is 0xCC.  Packet size is 23 bytes.

## Static Color Packet

| Byte Index | Value       |
| ---------- | ----------- |
| 0x00       | Zone Byte 0 |
| 0x01       | Zone Byte 1 |
| 0x02-0x09  | 0x00        |
| 0x0A       | 0x01        |
| 0x0B       | 0x5A        |
| 0x0C       | 0x00        |
| 0x0D       | Red         |
| 0x0E       | Green       |
| 0x0F       | Blue        |

## Apply Packet

| Byte Index | Value |
| ---------- | ----- |
| 0x00       | 0x28  |
| 0x01       | 0xFF  |
|