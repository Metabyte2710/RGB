ASRock's Polychrome RGB motherboard lighting system uses a Nuvoton N76E885AT20 controller on [SMBus](SMBus-Interface-Details) that enumerates at device address 0x6A.  Information documented here comes from @EUA who did the reverse engineering work on this board.  His project can be found here:

https://github.com/EUA/AsrLed

## Firmware Version
Reading three bytes from address 0x00 gets the firmware version.  The first byte read should be 0x02, then the second and third bytes are the major and minor version numbers, respectively.

## Modes
Address 0x30 is the mode setting address.  The current mode can be read by reading two bytes from this address.  The second byte contains the mode.  A new mode is set by writing a new mode value to it.

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