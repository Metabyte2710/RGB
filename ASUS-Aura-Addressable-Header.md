The addressable Aura header is a USB device with address 0B05:1872, 0B05:1867, 0B05:1889, and possibly others.  The ROG Aura Terminal uses this protocol as well.  The messages are 65 bytes in length.  The protocol uses HID write and read operations, though HID feature requests also appear to work on some devices.

Information provided by Vinay Dargar and Stavros Avramidis and taken from code here:

https://github.com/purpl3F0x/hid_rgb_devices/blob/master/aura_hid.hpp

# Request Firmware String

| Byte index | Value |
| ---------- | ----- |
| 0x00       | 0xEC  |
| 0x01       | 0x82  |

## Firmware String Response

| Byte index | Value                                   |
| ---------- | --------------------------------------- |
| 0x00       | 0xEC                                    |
| 0x01       | 0x02                                    |
| 0x02-0x12  | Firmware string (ex. "AUTA0-S072-0101") |

# Request Configuration Table

| Byte index | Value |
| ---------- | ----- |
| 0x00       | 0xEC  |
| 0x01       | 0xB0  |

## Configuration Table Response

| Byte index | Value                                   |
| ---------- | --------------------------------------- |
| 0x00       | 0xEC                                    |
| 0x01       | 0x30                                    |
| 0x03+      | Configuration Table Data (60 bytes)     |

# Set Channel Effect

| Byte index | Function                                  |
| ---------- | ----------------------------------------- |
| 0x00       | 0xEC                                      |
| 0x01       | 0x3B                                      |
| 0x02       | Channel                                   |
| 0x03       | 0x00                                      |
| 0x04       | Effect Mode                               |
| 0x05       | Red                                       |
| 0x06       | Green                                     |
| 0x07       | Blue                                      |

## Effect Modes

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

# Set LED Colors for Direct Mode

| Byte index | Function                                  |
| ---------- | ----------------------------------------- |
| 0x00       | 0xEC                                      |
| 0x01       | 0x40                                      |
| 0x02       | Channel                                   |
| 0x03       | Start LED Index                           |
| 0x04       | Number of LEDs in this packet             |
| 0x05+      | LED Data (3 bytes per LED, RGB order)     |
