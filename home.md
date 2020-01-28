## ![OpenRGB](uploads/5b7e633ac9f63b00c8a4c72686206c3f/OpenRGB.png) (formerly OpenAuraSDK)

The goal of this project is to create an easy-to-use open source software program and library for accessing and controlling RGB lights on various PC hardware including motherboards, RAM modules, graphics cards, cooling devices, and peripherals.

This project originally focused only on ASUS Aura.  It was spun off of Keyboard Visualizer's AsusAuraWindows branch to learn more about the details behind the Aura protocol and to develop a more flexible, compatible, and reliable driver for Aura.  Our Aura implementation is now quite solid and supports multiple generations of Aura controller across both Intel and AMD platforms.  It also supports Aura-compatible controllers used across multiple manufacturers of RGB memory modules including G.Skill Trident Z RGB and others.  It is still lacking a few capabilities, namely saving settings to persist across reboots, but the core functionality of setting colors and modes is there.

After getting a solid Aura implementation, the project branched out into other manufacturers and categories of RGB devices.  A major focus was to develop a software API that could reliably represent as many RGB devices as possible, exposing their various modes and describing their LED layouts via zones, that was generic enough to write a user application without specifically targeting any one manufacturer.  To this extent, the generic_rgb_interface_test branch was created which became the foundation of OpenRGB.  The goal of OpenRGB is to both develop new drivers for unsupported devices and integrate existing open source drivers for devices that do have some sort of open support.  The goal is to be the one-stop solution to open source RGB lighting control!

## Motherboard RGB Systems

* [ASUS Aura (SMBus Variants)](ASUS-Aura-Overview)
    * ASUS PRIME X370-Pro
    * ASUS PRIME X470-Pro
    * ASUS PRIME X399-A
    * ASUS PRIME B450M-Gaming
    * ASUS PRIME Z270-A
    * ASUS PRIME Z370-A
    * ASUS ROG Strix B450-F Gaming
    * ASUS ROG Strix Z370-E

* [Gigabyte Aorus RGB Fusion 1.0](Gigabyte-RGB-Fusion-1.0)
    * Gigabyte Aorus X370 Gaming 5

## RGB RAM Modules

* [ASUS Aura Based](ASUS-Aura-Overview)
    * G.Skill Trident Z RGB
    * Geil Super Luce
    * Team T-Force Delta RGB
    * OLOy WarHawk RGB
    * ADATA SPECTRIX RGB

* [Corsair Vengeance RGB](Corsair-Vengeance-RGB)

* [Corsair Vengeance Pro RGB](Corsair-Vengeance-Pro-RGB)

* [HyperX RGB Memory](HyperX-Predator-RGB)
    * HyperX Predator RGB
    * HyperX Fury RGB

* [Patriot Viper RGB](Patriot-Viper-RGB)

## LED Strip Controllers

* [NZXT Hue+](NZXT-Hue-Plus)

* [NZXT Hue 2](NZXT-Hue-2)

* [Corsair Lighting Node Pro](Corsair-Lighting-Node-Pro)

* [Corsair Commander Pro](Corsair-Lighting-Node-Pro)

* [Keyboard Visualizer Arduino LED strips](Keyboard-Visualizer-LED-Strips)

* [E1.31 Streaming ACN Protocol](E1.31)

## Fans and Coolers

* [AMD Wraith Prism](AMD-Wraith-Prism)

## Keyboards

* [MSI Steelseries 3-Zone Keyboard](MSI-3-Zone-Keyboard)

* [TTEsports Poseidon Z RGB](Poseidon-Z-RGB)

## Other projects integrated

* Razer Chroma SDK (Windows)
* OpenRazer (Linux)
* Faustus (ASUS TUF Laptop Keyboards) (Linux)

## Under investigation, not yet working:

* [Crucial Ballistix RGB](Crucial-Ballistix-RGB)
* [OpenRazer on Windows](https://github.com/rsandoz/razer-drivers-win32)
* Gigabyte Aorus Xtreme GTX1080Ti Waterforce
* ASRock Fatal1ty B350 Gaming-ITX/ac ([ASRock Polychrome RGB](ASRock-Polychrome-RGB))
* Look into MSI support: https://github.com/nagisa/msi-rgb