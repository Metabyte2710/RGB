Beginning with the AMD X570 chipset generation, Asus has switched from using SMBus controllers to USB controllers for on-board lighting and 12V RGB non-addressable header control.  The Aura USB controller enumerates at 0B05:18F3 and uses HID request messages for control.  Messages are 65 bytes long and zero-filled.

There seems to be some overlap between these controllers and the addressable header controllers on X470 era boards (which used both an SMBus controller for motherboard and single-zone RGB headers and a USB controller for addressable headers).

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

# Start of update

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0xEC        |
| 0x01       | 0x35        |
| 0x02       | 0x00        |
| 0x03       | 0x00        |
| 0x04       | 0x00        |
| 0x05       | 0x01        |

# Set Colors

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0xEC        |
| 0x01       | 0x36        |
| 0x02       | 0x00        |
| 0x03       | 0xFF        |
| 0x04       | 0x00        |
| 0x05+      | Color data  |