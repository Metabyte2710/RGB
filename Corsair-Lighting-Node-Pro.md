The Corsair Lighting Node Pro is an addressable LED strip controller with two channels, each supporting up to 60 LEDs.  It interfaces using USB and enumerates at 1B1C:0C0B.  Packets are 64 bytes long.

# Color Data Packet

| Byte Index | Description                               |
| ---------- | ----------------------------------------- |
| 0x00       | 0x32                                      |
| 0x01       | Channel (0 or 1)                          |
| 0x02       | 0x00                                      |
| 0x03       | 0x0A                                      |
| 0x04       | Color Channel (0: Red, 1: Green, 2: Blue) |
| 0x05       | LED 0                                     |

# Apply Packet

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x33        |
| 0x01       | 0xFF        |
| 0x02 - end | 0x00        |