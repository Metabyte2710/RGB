ASRock's Polychrome RGB motherboard lighting system uses a Nuvoton N76E885AT20 controller on [SMBus](SMBus-Interface-Details) that enumerates at device address 0x6A.  Information documented here comes from @EUA who did the reverse engineering work on this board.  His project can be found here:

https://github.com/EUA/AsrLed

## Modes
| Mode | Description |
| ------ | ------ |
| 0x10 | Off |
| 0x11 | Static |
| 0x12 | Breathing |
| 0x13 | Strobe |
| 0x14 | Cycling |
| 0x15 | Random |
| 0x17 | Music |
| 0x18 | Wave |