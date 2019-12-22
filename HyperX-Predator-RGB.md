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
| 0x71 | LED 0 Red |
| 0x72 | LED 0 Green |
| 0x73 | LED 0 Blue |
| 0x74 | LED 1 Red |
| 0x75 | LED 1 Green |
| 0x76 | LED 1 Blue |
| 0x77 | LED 2 Red |
| 0x78 | LED 2 Green |
| 0x79 | LED 2 Blue |
| 0x7A | LED 3 Red |
| 0x7B | LED 3 Green |
| 0x7C | LED 3 Blue |
| 0x7D | LED 4 Red |
| 0x7E | LED 4 Green |
| 0x7F | LED 4 Blue |
| 0x81 | LED 0 Brightness (0-100) |
| 0x84 | LED 1 Brightness (0-100) |
| 0x87 | LED 2 Brightness (0-100) |
| 0x8A | LED 3 Brightness (0-100) |
| 0x8D | LED 4 Brightness (0-100) |
| 0xD1 | ? |
| 0xD2 | ? |
| 0xDD | Effect Brightness (0-100) |
| 0xE1 | Message framing (see above) |
| 0xE2 | ? |
| 0xE3 | Mode Control 1 |
| 0xE4 | Mode Control 2 |
| 0xE5 | Mode Control 3 |
| 0xEC | Effect Red |
| 0xED | Effect Green |
| 0xEE | Effect Blue |

## Modes

| Value | Mode Selection | Description                      |
| ----- | -------------- | -------------------------------- |
| 0x02  | 0xE4           | Bounce                           |
| 0x03  | 0xE4           | Breathing                        |
| 0x04  | 0xE3           | Cycle                            |
| 0x05  | 0xE3           | Rainbow                          |
| 0x06  | 0xE4           | Blink                            |
| 0x07  | 0xE4           | Heartbeat                        |
| 0x08  | 0xE4           | Comet                            |
| 0x09  | 0xE4           | Static                           |
| 0x21  | 0xE5           | Direct (Individually addressable |