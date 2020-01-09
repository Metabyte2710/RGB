The Thermaltake Riing series of cooling products enumerate a USB device with VID 0x264A.  The G3 has PID 0x1FA5 and the Trio has PID 0x2135.

USB messages are 64 bytes long.  Unused bytes are set to zero.

# Initialize Controller

| Byte Index | Value |
| ---------- | ----- |
| 0x00       | 0xFE  |
| 0x01       | 0x33  |

# Save Profile
| Byte Index | Value |
| ---------- | ----- |
| 0x00       | 0x32  |
| 0x01       | 0x53  |