![20190630_121851](/uploads/fbac6826ce8063346cb73e30f6f5528e/20190630_121851.jpg)

The HyperX Predator RGB memory enumerates an SMBus device at the address 0x27.  It uses an SMBus message format with a fixed start and end format.

**Message Format**

| Write Command | Write Value | Function |
| ------ | ------ | ------ |
| 0xE1 | 0x01 | Start of message |
| 0xXX | 0xXX | Message contents |
| 0xE1 | 0x02 | End of message byte 1 |
| 0xE1 | 0x03 | End of message byte 2 |

**Commands**

| Write Command | Function |
| ------ | ------ |
| 0x0D | Brightness (0-100) |
| 0xE1 | Message framing (see above) |
| 0xE3 | Mode Control 1 |
| 0xE4 | Mode Control 2 |
| 0xEC | Red |
| 0xED | Green |
| 0xEE | Blue |