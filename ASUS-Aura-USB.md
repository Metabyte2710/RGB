Some of the documentation provided here comes from @inlart's blog: https://blog.inlart.com/post/openrgb-asus-x570/

Beginning with the AMD X70 chipset generation, Asus started using USB-based Aura controllers.  On the X470 generation boards, an Aura SMBus controller drives the on-board lighting and the 12V RGB headers while an Aura USB controller drives the addressable headers.  For the X570 generation, ASUS switched to a single Aura USB controller that controls on-board lighting, 12V RGB non-addressable headers, and addressable headers from a single location.  The protocols of these two types of Aura USB controllers differ but have some overlap.  This page documents the X570-generation Aura USB controller while the [ASUS Aura Addressable Header](ASUS-Aura-Addressable-Header) page documents the X470-generation addressable header controller that also powers the ROG Aura Terminal.

The Aura USB controller enumerates at 0B05:18F3 and uses HID request messages for control.  Messages are 65 bytes long and zero-filled.

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