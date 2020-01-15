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

| Write Command | Function                                   |
| ------------- | ------------------------------------------ |
| 0x11          | Slot 0 LED 0 Red                           |
| 0x12          | Slot 0 LED 0 Green                         |
| 0x13          | Slot 0 LED 0 Blue                          |
| 0x14          | Slot 0 LED 1 Red                           |
| 0x15          | Slot 0 LED 1 Green                         |
| 0x16          | Slot 0 LED 1 Blue                          |
| 0x17          | Slot 0 LED 2 Red                           |
| 0x18          | Slot 0 LED 2 Green                         |
| 0x19          | Slot 0 LED 2 Blue                          |
| 0x1A          | Slot 0 LED 3 Red                           |
| 0x1B          | Slot 0 LED 3 Green                         |
| 0x1C          | Slot 0 LED 3 Blue                          |
| 0x1D          | Slot 0 LED 4 Red                           |
| 0x1E          | Slot 0 LED 4 Green                         |
| 0x1F          | Slot 0 LED 4 Blue                          |
| 0x21          | Slot 0 LED 0 Brightness (0-100)            |
| 0x24          | Slot 0 LED 1 Brightness (0-100)            |
| 0x27          | Slot 0 LED 2 Brightness (0-100)            |
| 0x2A          | Slot 0 LED 3 Brightness (0-100)            |
| 0x2D          | Slot 0 LED 4 Brightness (0-100)            |
| 0x41          | Slot 1 LED 0 Red                           |
| 0x42          | Slot 1 LED 0 Green                         |
| 0x43          | Slot 1 LED 0 Blue                          |
| 0x44          | Slot 1 LED 1 Red                           |
| 0x45          | Slot 1 LED 1 Green                         |
| 0x46          | Slot 1 LED 1 Blue                          |
| 0x47          | Slot 1 LED 2 Red                           |
| 0x48          | Slot 1 LED 2 Green                         |
| 0x49          | Slot 1 LED 2 Blue                          |
| 0x4A          | Slot 1 LED 3 Red                           |
| 0x4B          | Slot 1 LED 3 Green                         |
| 0x4C          | Slot 1 LED 3 Blue                          |
| 0x4D          | Slot 1 LED 4 Red                           |
| 0x4E          | Slot 1 LED 4 Green                         |
| 0x4F          | Slot 1 LED 4 Blue                          |
| 0x51          | Slot 1 LED 0 Brightness (0-100)            |
| 0x54          | Slot 1 LED 1 Brightness (0-100)            |
| 0x57          | Slot 1 LED 2 Brightness (0-100)            |
| 0x5A          | Slot 1 LED 3 Brightness (0-100)            |
| 0x5D          | Slot 1 LED 4 Brightness (0-100)            |
| 0x71          | Slot 2 LED 0 Red                           |
| 0x72          | Slot 2 LED 0 Green                         |
| 0x73          | Slot 2 LED 0 Blue                          |
| 0x74          | Slot 2 LED 1 Red                           |
| 0x75          | Slot 2 LED 1 Green                         |
| 0x76          | Slot 2 LED 1 Blue                          |
| 0x77          | Slot 2 LED 2 Red                           |
| 0x78          | Slot 2 LED 2 Green                         |
| 0x79          | Slot 2 LED 2 Blue                          |
| 0x7A          | Slot 2 LED 3 Red                           |
| 0x7B          | Slot 2 LED 3 Green                         |
| 0x7C          | Slot 2 LED 3 Blue                          |
| 0x7D          | Slot 2 LED 4 Red                           |
| 0x7E          | Slot 2 LED 4 Green                         |
| 0x7F          | Slot 2 LED 4 Blue                          |
| 0x81          | Slot 2 LED 0 Brightness (0-100)            |
| 0x84          | Slot 2 LED 1 Brightness (0-100)            |
| 0x87          | Slot 2 LED 2 Brightness (0-100)            |
| 0x8A          | Slot 2 LED 3 Brightness (0-100)            |
| 0x8D          | Slot 2 LED 4 Brightness (0-100)            |
| 0xA1          | Slot 3 LED 0 Red                           |
| 0xA2          | Slot 3 LED 0 Green                         |
| 0xA3          | Slot 3 LED 0 Blue                          |
| 0xA4          | Slot 3 LED 1 Red                           |
| 0xA5          | Slot 3 LED 1 Green                         |
| 0xA6          | Slot 3 LED 1 Blue                          |
| 0xA7          | Slot 3 LED 2 Red                           |
| 0xA8          | Slot 3 LED 2 Green                         |
| 0xA9          | Slot 3 LED 2 Blue                          |
| 0xAA          | Slot 3 LED 3 Red                           |
| 0xAB          | Slot 3 LED 3 Green                         |
| 0xAC          | Slot 3 LED 3 Blue                          |
| 0xAD          | Slot 3 LED 4 Red                           |
| 0xAE          | Slot 3 LED 4 Green                         |
| 0xAF          | Slot 3 LED 4 Blue                          |
| 0xB1          | Slot 3 LED 0 Brightness (0-100)            |
| 0xB4          | Slot 3 LED 1 Brightness (0-100)            |
| 0xB7          | Slot 3 LED 2 Brightness (0-100)            |
| 0xBA          | Slot 3 LED 3 Brightness (0-100)            |
| 0xBD          | Slot 3 LED 4 Brightness (0-100)            |
| 0xD1          | Timer MSB                                  |
| 0xD2          | Timer LSB                                  |
| 0xD3          | Effect on time MSB                         |
| 0xD4          | Effect on time LSB                         |
| 0xD5          | Change time MSB                            |
| 0xD6          | Change time LSB                            |
| 0xD7          | Fade in time MSB                           |
| 0xD8          | Fade in time LSB                           |
| 0xD9          | Fade out time MSB                          |
| 0xDA          | Fade out time LSB                          |
| 0xDB          | Effect off time MSB                        |
| 0xDC          | Effect off time LSB                        |
| 0xDD          | Effect brightness                          |
| 0xE1          | Message framing (see above)                |
| 0xE2          | Mode Control 0 (no parameters)             |
| 0xE3          | Mode Control 1 (speed, brightness )        |
| 0xE4          | Mode Control 2 (speed, brightness, color ) |
| 0xE5          | Mode Control 3 (independent control mode)  |
| 0xEA          | Effect cycle delay MSB                     |
| 0xEB          | Effect cycle delay LSB                     |
| 0xEC          | Effect Red                                 |
| 0xED          | Effect Green                               |
| 0xEE          | Effect Blue                                |

## Modes

| Value | Mode Selection | Description                          | Time registers | Slow Time Setting | Fast Time Setting |
| ----- | -------------- | ------------------------------------ | -------------- | ----------------- | ----------------- |
| 0x01  | 0xE3           | Off                                  |                |                   |                   |
| 0x02  | 0xE4           | Bounce                               | Timer          | 0x07D0            | 0x0064            |
| 0x03  | 0xE4           | Breathing                            |                |                   |                   |
| 0x04  | 0xE3           | Cycle                                |                |                   |                   |
| 0x05  | 0xE3           | Rainbow                              |                |                   |                   |
| 0x06  | 0xE4           | Blink                                | Off, On        | 0x07D0, 0x07D0    | 0x01F4, 0x07D0    |
| 0x07  | 0xE4           | Heartbeat                            |                |                   |                   |
| 0x08  | 0xE4           | Comet                                |                |                   |                   |
| 0x09  | 0xE4           | Static                               |                |                   |                   |
| 0x21  | 0xE5           | Individually Addressable Static      |                |                   |                   |
| 0x22  | 0xE5           | Individually Addressable Chase Left  |                |                   |                   |
| 0x23  | 0xE5           | Individually Addressable Chase Right |                |                   |                   |
| 0x24  | 0xE5           | Individually Addressable Breathing   |                |                   |                   |
| 0x25  | 0xE5           | Individually Addressable Blink       |                |                   |                   |
| 0x26  | 0xE5           | Individually Addressable Heartbeat   |                |                   |                   |