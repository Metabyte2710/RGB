The addressable Aura header is a USB device with address 0B05:1872, 0B05:1867, and possibly others.  The messages are 65 bytes in length.  Information provided by Vinay Dargar and Stavros Avramidis and taken from code here:

https://github.com/purpl3F0x/hid_rgb_devices/blob/master/aura_hid.hpp

# Message Format

| Byte index | Function                                  |
| ---------- | ----------------------------------------- |
| 0x00       | 0xEC                                      |
| 0x01       | Control Mode (Direct: 0x40, Effect: 0x3B) |
| 0x02       | Device                                    |
| 0x03       | Start LED                                 |
| 0x04       | Effect Mode                               |
| 0x05 - end | 20 LEDs of color data in RGB order        |

# Effect Modes

| Mode value | Mode description          |
| ---------- | ------------------------- |
| 0x00       | Off                       |
| 0x01       | Static                    |
| 0x02       | Breathing                 |
| 0x03       | Flashing                  |
| 0x04       | Spectrum Cycle            |
| 0x05       | Rainbow                   |
| 0x06       | Spectrum Cycle Breathing  |
| 0x07       | Chase Fade                |
| 0x08       | Spectrum Cycle Chase Fade |
| 0x09       | Chase                     |
| 0x0A       | Spectrum Cycle Chase      |
| 0x0B       | Spectrum Cycle Wave       |
| 0x0C       | Rainbow Pulse             |
| 0x0D       | Random Flicker            |
| 0x0E       | Music                     |
