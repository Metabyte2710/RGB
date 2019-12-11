## OpenRGB (formerly OpenAuraSDK)

The goal of this project is to create an easy-to-use open source software program and library for accessing and controlling RGB lights on various PC hardware including motherboards, RAM modules, graphics cards, cooling devices, and peripherals.

This project originally focused only on ASUS Aura.  It was spun off of Keyboard Visualizer's AsusAuraWindows branch to learn more about the details behind the Aura protocol and to develop a more flexible, compatible, and reliable driver for Aura.  Our Aura implementation is now quite solid and supports multiple generations of Aura controller across both Intel and AMD platforms.  It also supports Aura-compatible controllers used across multiple manufacturers of RGB memory modules including G.Skill Trident Z RGB and others.  It is still lacking a few capabilities, namely saving settings to persist across reboots, but the core functionality of setting colors and modes is there.

After getting a solid Aura implementation, the project branched out into other manufacturers and categories of RGB devices.  A major focus was to develop a software API that could reliably represent as many RGB devices as possible, exposing their various modes and describing their LED layouts via zones, that was generic enough to write a user application without specifically targeting any one manufacturer.  To this extent, the generic_rgb_interface_test branch was created which became the foundation of OpenRGB.  The goal of OpenRGB is to both develop new drivers for unsupported devices and integrate existing open source drivers for devices that do have some sort of open support.  The goal is to be the one-stop solution to open source RGB lighting control!

## [ASUS Aura Devices](ASUS-Aura-Overview):

Motherboards:

* ASUS PRIME X370-Pro
* ASUS PRIME X470-Pro
* ASUS PRIME X399-A
* ASUS PRIME B450M-Gaming
* ASUS PRIME Z270-A
* ASUS PRIME Z370-A
* ASUS ROG Strix B450-F Gaming
* ASUS ROG Strix Z370-E

Aura RAM:

* G.Skill Trident Z RGB
* Geil Super Luce
* Team T-Force Delta RGB
* OLOy WarHawk RGB
* ADATA SPECTRIX RGB

## Non-Aura RAM

* Corsair Vengeance RGB ([experimental support](Corsair-Vengeance-RGB))
* Corsair Vengeance Pro RGB ([experimental support](Corsair-Vengeance-Pro-RGB))
* HyperX Predator RGB ([experimental support](HyperX-Predator-RGB))

## Other projects integrated in generic RGB interface branch:

* Razer Chroma SDK (Windows)
* OpenRazer (Linux)
* E1.31 (Linux)
* KeyboardVisualizer Arduino LED strips

## Under investigation, not yet working:

* Gigabyte Aorus X370 Gaming 5 (RGB Fusion 1.0)
* AMD Wraith Prism
* Gigabyte Aorus Xtreme GTX1080Ti Waterforce
* TTEsports Poseidon Z RGB

