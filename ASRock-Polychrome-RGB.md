ASRock's Polychrome RGB motherboard lighting system uses a Nuvoton N76E885AT20 controller on [SMBus](SMBus-Interface-Details) that enumerates at device address 0x6A.  Information documented here comes from @EUA who did the reverse engineering work on this board.  His project can be found here:

https://github.com/EUA/AsrLed

Register addresses appear to operate as multi-byte values.  Reading one byte from a register address indicates the size, in bytes, of the value it stores.  Reading additional bytes retrieves the data.  To write to a register address, a block transfer of the given size is used.

## Register Addresses
| Address | Size | Function |
| ------ | ------ | ------ |
| 0x00 | 2 | Firmware Version Major.Minor |
| 0x30 | 1 | Mode |

## Modes
To enable a mode, write the mode value to the mode register (0x30).  To set the colors and/or speed for the mode, block write 1-4 bytes to the mode's value (for instance to 0x11 for static).  The number of bytes and format of block is shown in the table below.

| Mode | Description | Bytes | Data |
| ------ | ------ | ------ | ------ |
| 0x10 | Off | 0 | No data |
| 0x11 | Static | 3 | Red, Green, Blue |
| 0x12 | Breathing | 4 | Red, Green, Blue, Speed |
| 0x13 | Strobe | 4 | Red, Green, Blue, Speed |
| 0x14 | Cycling | 4 | Red, Green, Blue, Speed |
| 0x15 | Random | 1 | Speed |
| 0x17 | Music | 3 | Red, Green, Blue |
| 0x18 | Wave | 1 | Speed |