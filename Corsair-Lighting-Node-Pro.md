The Corsair Lighting Node Pro is an addressable LED strip controller with two channels, each supporting up to 60 LEDs.  It interfaces using USB and enumerates at 1B1C:0C0B.  Packets are 64 bytes long.  The Corsair Commander Pro (1B1C:0C10) shares much of the same functionality.

The Lighting Node Pro appears to reset itself after 20 seconds of inactivity.  I haven't implemented periodic refreshing in OpenRGB, so when you set the colors it will default back to rainbow after 20 seconds.  To fix this, I'll need to add some sort of keep-alive thread to either send the full color data or find some other packet that keeps it from resetting.

It looks like sending the apply packet every few seconds is enough to keep it from reverting to rainbow mode.

# Start Packet

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x38        |
| 0x01       | 0x00        |
| 0x02       | 0x02        |
| 0x03 - end | 0x00        |

# Color Data Packet

| Byte Index | Description                                 |
| ---------- | ------------------------------------------- |
| 0x00       | 0x32                                        |
| 0x01       | Channel (0 or 1)                            |
| 0x02       | Start index                                 |
| 0x03       | Count                                       |
| 0x04       | Color Channel (0: Red, 1: Green, 2: Blue)   |
| 0x05-end   | LED channel values equal to Count           |

# Apply Packet

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x33        |
| 0x01       | 0xFF        |
| 0x02 - end | 0x00        |

# Effect Packet
| Byte Index | Description        |
| ---------- | ------------------ |
| 0x00       | 0x35               |
| 0x01       | Channel (0 or 1)   |
| 0x02       | Strip/Fan Number   |
| 0x03       | Type of device     |
| 0x04       | Effect Mode        |
| 0x05       | Effect Speed       |
| 0x06       | Direction          |
| 0x07       | Fixed/Random Color |
| 0x08       | 0xFF               |