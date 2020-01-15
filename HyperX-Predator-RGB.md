![20190630_121851](/uploads/fbac6826ce8063346cb73e30f6f5528e/20190630_121851.jpg)

The HyperX Predator and Fury RGB memory modules enumerate an SMBus device at the address 0x27.  It uses an SMBus message format with a fixed start and end format.

**Message Format**

| Write Command | Write Value | Function         |
| ------------- | ----------- | ---------------- |
| 0xE1          | 0x01        | Start of message |
| 0xXX          | 0xXX        | Message contents |
| 0xE1          | 0x02        | Message done     |
| 0xE1          | 0x03        | Apply changes    |

**Commands**

| Write Command | Function                        |
| ------------- | ------------------------------- |
| 0x11          | Slot 0 LED 0 Red                |
| 0x12          | Slot 0 LED 0 Green              |
| 0x13          | Slot 0 LED 0 Blue               |
| 0x14          | Slot 0 LED 1 Red                |
| 0x15          | Slot 0 LED 1 Green              |
| 0x16          | Slot 0 LED 1 Blue               |
| 0x17          | Slot 0 LED 2 Red                |
| 0x18          | Slot 0 LED 2 Green              |
| 0x19          | Slot 0 LED 2 Blue               |
| 0x1A          | Slot 0 LED 3 Red                |
| 0x1B          | Slot 0 LED 3 Green              |
| 0x1C          | Slot 0 LED 3 Blue               |
| 0x1D          | Slot 0 LED 4 Red                |
| 0x1E          | Slot 0 LED 4 Green              |
| 0x1F          | Slot 0 LED 4 Blue               |
| 0x21          | Slot 0 LED 0 Brightness (0-100) |
| 0x24          | Slot 0 LED 1 Brightness (0-100) |
| 0x27          | Slot 0 LED 2 Brightness (0-100) |
| 0x2A          | Slot 0 LED 3 Brightness (0-100) |
| 0x2D          | Slot 0 LED 4 Brightness (0-100) |
| 0x41          | Slot 1 LED 0 Red                |
| 0x42          | Slot 1 LED 0 Green              |
| 0x43          | Slot 1 LED 0 Blue               |
| 0x44          | Slot 1 LED 1 Red                |
| 0x45          | Slot 1 LED 1 Green              |
| 0x46          | Slot 1 LED 1 Blue               |
| 0x47          | Slot 1 LED 2 Red                |
| 0x48          | Slot 1 LED 2 Green              |
| 0x49          | Slot 1 LED 2 Blue               |
| 0x4A          | Slot 1 LED 3 Red                |
| 0x4B          | Slot 1 LED 3 Green              |
| 0x4C          | Slot 1 LED 3 Blue               |
| 0x4D          | Slot 1 LED 4 Red                |
| 0x4E          | Slot 1 LED 4 Green              |
| 0x4F          | Slot 1 LED 4 Blue               |
| 0x51          | Slot 1 LED 0 Brightness (0-100) |
| 0x54          | Slot 1 LED 1 Brightness (0-100) |
| 0x57          | Slot 1 LED 2 Brightness (0-100) |
| 0x5A          | Slot 1 LED 3 Brightness (0-100) |
| 0x5D          | Slot 1 LED 4 Brightness (0-100) |
| 0x71          | Slot 2 LED 0 Red                |
| 0x72          | Slot 2 LED 0 Green              |
| 0x73          | Slot 2 LED 0 Blue               |
| 0x74          | Slot 2 LED 1 Red                |
| 0x75          | Slot 2 LED 1 Green              |
| 0x76          | Slot 2 LED 1 Blue               |
| 0x77          | Slot 2 LED 2 Red                |
| 0x78          | Slot 2 LED 2 Green              |
| 0x79          | Slot 2 LED 2 Blue               |
| 0x7A          | Slot 2 LED 3 Red                |
| 0x7B          | Slot 2 LED 3 Green              |
| 0x7C          | Slot 2 LED 3 Blue               |
| 0x7D          | Slot 2 LED 4 Red                |
| 0x7E          | Slot 2 LED 4 Green              |
| 0x7F          | Slot 2 LED 4 Blue               |
| 0x81          | Slot 2 LED 0 Brightness (0-100) |
| 0x84          | Slot 2 LED 1 Brightness (0-100) |
| 0x87          | Slot 2 LED 2 Brightness (0-100) |
| 0x8A          | Slot 2 LED 3 Brightness (0-100) |
| 0x8D          | Slot 2 LED 4 Brightness (0-100) |
| 0xA1          | Slot 3 LED 0 Red                |
| 0xA2          | Slot 3 LED 0 Green              |
| 0xA3          | Slot 3 LED 0 Blue               |
| 0xA4          | Slot 3 LED 1 Red                |
| 0xA5          | Slot 3 LED 1 Green              |
| 0xA6          | Slot 3 LED 1 Blue               |
| 0xA7          | Slot 3 LED 2 Red                |
| 0xA8          | Slot 3 LED 2 Green              |
| 0xA9          | Slot 3 LED 2 Blue               |
| 0xAA          | Slot 3 LED 3 Red                |
| 0xAB          | Slot 3 LED 3 Green              |
| 0xAC          | Slot 3 LED 3 Blue               |
| 0xAD          | Slot 3 LED 4 Red                |
| 0xAE          | Slot 3 LED 4 Green              |
| 0xAF          | Slot 3 LED 4 Blue               |
| 0xB1          | Slot 3 LED 0 Brightness (0-100) |
| 0xB4          | Slot 3 LED 1 Brightness (0-100) |
| 0xB7          | Slot 3 LED 2 Brightness (0-100) |
| 0xBA          | Slot 3 LED 3 Brightness (0-100) |
| 0xBD          | Slot 3 LED 4 Brightness (0-100) |
| 0xD1          | ?                               |
| 0xD2          | ?                               |
| 0xDD          | Effect Brightness (0-100)       |
| 0xE1          | Message framing (see above)     |
| 0xE2          | ?                               |
| 0xE3          | Mode Control 1                  |
| 0xE4          | Mode Control 2                  |
| 0xE5          | Mode Control 3                  |
| 0xEC          | Effect Red                      |
| 0xED          | Effect Green                    |
| 0xEE          | Effect Blue                     |

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