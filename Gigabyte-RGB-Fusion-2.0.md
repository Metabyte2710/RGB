Gigabyte's second generation of RGB Fusion enabled motherboards use an ITE8297 controller that enumerates a USB device at 048D:8297.  This device is controlled using the HID protocol.

## Static Color Packet

| Byte Index | Value               |
| ---------- | ------------------- |
| 0x00       | Report ID: 0xCC     |
| 0x01       | Header              |
| 0x02       | Zone 0              |
| 0x03       |                     |
| 0x04       |                     |
| 0x05       |                     |
| 0x06       | Zone 1              |
| 0x07       |                     |
| 0x08       |                     |
| 0x09       |                     |
| 0x0A       | 0x00                |
| 0x0B       | Effect              |
| 0x0C       | Max Brightness 0x5A |
| 0x0D       | Min Brightness 0x00 |
| 0x0E       | Color 0 Red         |
| 0x0F       | Color 0 Green       |
| 0x10       | Color 0 Blue        |
| 0x11       | 0x00                |
| 0x12       | Color 1 Red         |
| 0x13       | Color 1 Green       |
| 0x14       | Color 1 Blue        |

## Apply Packet

| Byte Index | Value |
| ---------- | ----- |
| 0x00       | 0x28  |
| 0x01       | 0xFF  |
|