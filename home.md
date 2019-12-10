The goal of this project is to create an easy-to-use open source software program and library for accessing and controlling RGB lights on various PC hardware including ASUS Aura RGB devices on motherboards and RAM modules. The ASUS Aura controller appears to be used on RAM products such as G.Skill's Trident Z RGB. Ideally we would be able to get AURA working on both Windows and Linux. This project has been spun off of Keyboard Visualizer's AsusAuraWindows branch.  While this project initially focused only on Asus Aura, it has grown to cover many other devices which also use the SMBus interface.  This Wiki is a place to document the reverse engineering efforts and protocols for various devices.

Tested Motherboards:

* ASUS PRIME X370-Pro
* ASUS PRIME X470-Pro
* ASUS PRIME X399-A
* ASUS PRIME B450M-Gaming
* ASUS PRIME Z270-A
* ASUS PRIME Z370-A
* ASUS ROG Strix B450-F Gaming
* ASUS ROG Strix Z370-E

Tested RAM:

* G.Skill Trident Z RGB
* Geil Super Luce
* Team T-Force Delta RGB
* OLOy WarHawk RGB
* Corsair Vengeance RGB ([experimental support](Corsair-Vengeance-RGB))
* Corsair Vengeance Pro RGB ([experimental support](Corsair-Vengeance-Pro-RGB))
* HyperX Predator RGB ([experimental support](HyperX-Predator-RGB))

## [Aura Interface Details](Aura-Interface-Details)

The Aura controllers use the SMBus interface.  It also appears that some boards use a USB interface, particularly those with an addressable RGB header.  Those controllers are not covered by this project yet.

## [Aura Controller Registers](Aura-Controller-Registers)

The SMBus Aura controllers use a register write system to set colors and settings.  The register memory space is 16 bits (0x0000-0xFFFF) and appears to contain the Aura controller's firmware, non-volatile settings, volatile settings, and some other information.  The color control registers are in the 0x8000 memory block.

## [Aura Software Information](Aura-Software-Information)

## [Known Motherboards](Known-Motherboards)

List of motherboards with their SMBus and Aura controller information.

