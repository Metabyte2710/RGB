Gigabyte's first generation RGB Fusion enabled motherboards use an ITE IT7236AFN microcontroller to control their two-zone RGB lighting system.  This microcontroller attaches to the system via SMBus and enumerates at address 0x28.  The protocol appears to be register mapped with a bank selection register (0xF0) to expand the I/O address space.  Banks 0 and 1 are used in the commands to set modes.

## Bank Selection Register
| Address | Function |
| ------ | ------ |
| 0xF0 | Bank Selection |

## Bank 0 Registers
| Address | Function |
| ------ | ------ |
| 0x00 | Channel 0 Red |
| 0x01 | Channel 0 Green |
| 0x02 | Channel 0 Blue |
| 0x08 | Channel 1 Red |
| 0x09 | Channel 1 Green |
| 0x0A | Channel 1 Blue |

## Bank 1 Registers
| Address | Function |
| ------ | ------ |
| 0x03 | Channel 0 Mode Selection |
| 0x13 | Channel 1 Mode Selection |

## Modes
| Value | Description |
| ----- | ------ |
| 0x10 | Static |
| 0x11 | Pulsing |
