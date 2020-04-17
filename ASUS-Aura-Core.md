Asus ROG laptops feature an RGB keyboard sold with the "Aura Core" branding.  These keyboards connect to the laptop motherboard via USB at addresses 0B05:1854, 0B05:1869, and 0B05:1866.  Information documented here was gathered from Will Roberts' rogauracore project (https://github.com/wroberts/rogauracore).  The USB messages are always 17 bytes long.

# Mode / Color Data

| Byte index | Value  |
| ---------- | ------ |
| 0x00       | 0x5D   |
| 0x01       | 0xB3   |
| 0x02       | Zone   |
| 0x03       | Mode   |
| 0x04       | Red    |
| 0x05       | Green  |
| 0x06       | Blue   |
| 0x07       | Speed  |

# Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x00       | Static           |
| 0x01       | Breathing        |
| 0x02       | Color Cycle      |


# Brightness

| Byte index | Value      |
| ---------- | ---------- |
| 0x00       | 0x5A       |
| 0x01       | 0xBA       |
| 0x02       | 0xC5       |
| 0x03       | 0xC4       |
| 0x04       | Brightness |

# Set

| Byte index | Value  |
| ---------- | ------ |
| 0x00       | 0x5D   |
| 0x01       | 0xB5   |
| 0x02 - end | 0x00   |

# Apply

| Byte index | Value  |
| ---------- | ------ |
| 0x00       | 0x5D   |
| 0x01       | 0xB4   |
| 0x02 - end | 0x00   |