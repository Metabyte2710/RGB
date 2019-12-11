ASRock's Polychrome RGB motherboard lighting system uses a Nuvoton N76E885AT20 controller on [SMBus](SMBus-Interface-Details) that enumerates at device address 0x6A.  Information documented here comes from @EUA who did the reverse engineering work on this board.  His project can be found here:

https://github.com/EUA/AsrLed

Register addresses appear to operate as multi-byte values.  Reading one byte from a register address indicates the size, in bytes, of the value it stores.  Reading additional bytes retrieves the data.  To write to a register address, a block transfer of the given size is used.

## Register Addresses
| Address | Size | Function |
| ------ | ------ | ------ |
| 0x00 | 2 | Firmware Version Major.Minor |
| 0x30 | 1 | Mode |

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