## [Aura Interface Details](Aura-Interface-Details)

The Aura controllers use the SMBus interface.  It also appears that some boards use a USB interface, particularly those with an addressable RGB header and X570 generation boards.  These USB controllers are not covered by this project yet.

## [Aura Controller Registers](Aura-Controller-Registers)

The SMBus Aura controllers use a register write system to set colors and settings.  The register memory space is 16 bits (0x0000-0xFFFF) and appears to contain the Aura controller's firmware, non-volatile settings, volatile settings, and some other information.  The color control registers are in the 0x8000 memory block.

## [Aura Software Information](Aura-Software-Information)

## [Known Motherboards](Known-Motherboards)

List of motherboards with their SMBus and Aura controller information.