Gigabyte's second generation of RGB Fusion enabled motherboards use an ITE8297 controller that enumerates a USB device at 048D:8297.  This device is controlled using the HID protocol.

Information gathered from https://github.com/jackun/IT8297-rgb-controller and https://github.com/summerblind/aorusx570-rgb

## Effect Packet

| Byte Index | Value                  |
| ---------- | ---------------------- |
| 0x00       | Report ID: 0xCC        |
| 0x01       | Header                 |
| 0x02       | Zone 0 (32-bit)        |
| 0x03       |                        |
| 0x04       |                        |
| 0x05       |                        |
| 0x06       | Zone 1 (32-bit)        |
| 0x07       |                        |
| 0x08       |                        |
| 0x09       |                        |
| 0x0A       | 0x00                   |
| 0x0B       | Effect                 |
| 0x0C       | Max Brightness 0x5A    |
| 0x0D       | Min Brightness 0x00    |
| 0x0E       | Color 0 Red            |
| 0x0F       | Color 0 Green          |
| 0x10       | Color 0 Blue           |
| 0x11       | 0x00                   |
| 0x12       | Color 1 Red            |
| 0x13       | Color 1 Green          |
| 0x14       | Color 1 Blue           |
| 0x15       | 0x00                   |
| 0x16       | Fade in time (16-bit)  |
| 0x17       |                        |
| 0x18       | Fade out time (16-bit) |
| 0x19       |                        |
| 0x1A       | Hold time (16-bit)     |
| 0x1B       |                        |
| 0x1C       | ? time (16-bit)        |
| 0x1D       |                        |
| 0x1E       | Number of colors       |
| 0x1F       | ?                      |
| 0x20       | ?                      |
| 0x21       | ?                      |
| 0x22 - end | 0x00                   |

## Apply Packet

| Byte Index | Value |
| ---------- | ----- |
| 0x00       | 0x28  |
| 0x01       | 0xFF  |
|