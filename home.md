The goal of this project is to create an easy-to-use open source software program and library for accessing and controlling ASUS Aura RGB devices on motherboards and RAM modules. The ASUS Aura controller appears to be used on RAM products such as G.Skill's Trident Z RGB. Ideally we would be able to get AURA working on both Windows and Linux. This project has been spun off of Keyboard Visualizer's AsusAuraWindows branch.

##[Aura Interface Details](Aura-Interface-Details)

The Aura controllers use the SMBus interface.  It also appears that some boards use a USB interface, particularly those with an addressable RGB header.  Those controllers are not covered by this project yet.

##[Aura Controller Registers](Aura-Controller-Registers)

The SMBus Aura controllers use a register write system to set colors and settings.  The register memory space is 16 bits (0x0000-0xFFFF) and appears to contain the Aura controller's firmware, non-volatile settings, volatile settings, and some other information.  The color control registers are in the 0x8000 memory block.

##[Aura Software Information](Aura-Software-Information)

##[Known Motherboards](Known-Motherboards)

List of motherboards with their SMBus and Aura controller information.

