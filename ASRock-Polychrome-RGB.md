![AsrockTaichiX470](uploads/a6f9e86b31d19ac05fa066d867a7249a/AsrockTaichiX470.png)

ASRock's Polychrome RGB motherboard lighting system uses a Nuvoton N76E885AT20 controller on [SMBus](SMBus-Interface-Details) that enumerates at device address 0x6A.  Information documented here comes from @EUA who did the reverse engineering work on this board.  His project can be found here:

https://github.com/EUA/AsrLed

Based on this comment: https://gitlab.com/CalcProgrammer1/OpenAuraSDK/issues/35#note_260299163, it looks like ASRock's first boards didn't actually use the Polychrome RGB branding and instead were called ASR LED.  The protocol changed slightly in the later firmware revisions, which were used on boards with the Polychrome branding.  More information can be found here:

https://github.com/RattyDAVE/asrock-leds/blob/master/NOTES.md

# ASR LED (Firmware 1.10)

## Register Addresses
Register addresses operate as multi-byte values.  Reading one byte from a register address indicates the size, in bytes, of the value it stores.  Reading additional bytes retrieves the data.  To write to a register address, a block transfer of the given size is used.

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

# Polychrome RGB (Firmware 2.10(?) and 3.0)

## Register Addresses
Register addresses appear to multi-byte values.  Reading one byte from a register address indicates the size, in bytes, of the value it stores.  Reading additional bytes retrieves the data.  To write to a register address, a block transfer of the given size is used.

| Address | Size | Function |
| ------ | ------ | ------ |
| 0x00 | 2 | Firmware Version Major.Minor |
| 0x30 | 1 | Mode |
| 0x34 | 3 | Color (Red, Green, Blue) |

## Modes
To enable a mode, write the mode value to the mode register (0x30).  To set the speed for the mode, block write 1 byte to the mode's value (for instance to 0x11 for static).  To set the colors for the mode, block write 3 bytes (Red, Green, Blue) to the color register (0x34).

| Mode | Description | Bytes | Data |
| ------ | ------ | ------ | ------ |
| 0x10 | Off | 0 | No data |
| 0x11 | Static | 0 | No data |
| 0x12 | Breathing | 1 | Speed |
| 0x13 | Strobe | 1 | Speed |
| 0x14 | Cycling | 1 | Speed |
| 0x15 | Random | 1 | Speed |
| 0x17 | Wave | 1 | Speed |
| 0x18 | Spring | 1 | Speed |
| 0x19 | Stack | 1 | Speed |
| 0x1A | Cram | 1 | Speed |
| 0x1B | Scan | 1 | Speed |
| 0x1C | Neon | 1 | Speed |
| 0x1D | Water | 1 | Speed |
| 0x1E | Rainbow | 1 | Speed |