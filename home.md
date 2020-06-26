## ![OpenRGB](uploads/5b7e633ac9f63b00c8a4c72686206c3f/OpenRGB.png) (formerly OpenAuraSDK)

One of the biggest complaints about RGB is the software ecosystem surrounding it.  Every manufacturer has their own app, their own brand, their own style.  If you want to mix and match devices, you end up with a ton of conflicting, functionally identical apps competing for your background resources.  On top of that, these apps are proprietary and Windows-only.  Some even require online accounts.  What if there was a way to control all of your RGB devices from a single app, on both Windows and Linux, without any nonsense?  That is what OpenRGB sets out to achieve.  One app to rule them all.

OpenRGB is still in its early stages and already supports quite a few products.  I'm always on the lookout for good deals on more popular RGB devices to add support for.

OpenRGB provides a software development kit (SDK) that can be used to integrate your RGB setup into other applications and games.  The OpenRGB SDK uses a network server which can be enabled in the OpenRGB application.  Other applications may then connect to OpenRGB and control the lighting.

## WARNING!

This project provides a tool to probe the SMBus.  This is a potentially dangerous operation if you don't know what you're doing.  Exercise caution when clicking the Detect Devices or Dump Device buttons.  There have been reports of Gigabyte motherboards having serious issues (bricking the RGB or bricking the entire board) when dumping certain devices.  On the same lines, exercise the same caution when using the i2cdump and i2cdetect commands on Linux, as they perform the same functionality.  OpenRGB is not liable for damage caused by improper SMBus access.

As of now, only Gigabyte RGB Fusion 2.0 boards have been reported to have issues.

![OpenRGB_new_icons](uploads/0ef8eb3936fe715217e7e3430c0aae18/OpenRGB_new_icons.PNG)

![OpenRGB_0.11_with_SDK_server](uploads/cedf17f8ae30f8b95703e705c357366a/OpenRGB_0.11_with_SDK_server.PNG)

## Join Our Discord

https://discord.gg/AQwjJPY

## How-Tos

* [Windows Setup and Usage](OpenRGB-Windows-Setup-and-Usage)

## [Frequently Asked Questions](Frequently-Asked-Questions)

## Support OpenRGB

* OpenRGB is a project I created to solve a problem I had with the RGB ecosystem.  My goal isn't to make money off of this project.  That said, people have requested to donate, and donations allow me to buy more RGB stuff to reverse engineer.

* [Donate via PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=4VPTFMD3G4QVG&item_name=OpenRGB+Development&currency_code=USD&source=url)

* Donate via Bitcoin: 1N83YPu7btXYadPS1neB9zX7X1QTdpyZQ

## Supported Devices

### Motherboard RGB Systems

* [ASUS Aura (SMBus Variants)](ASUS-Aura-Overview)
    * ASUS PRIME X370-Pro
    * ASUS PRIME X470-Pro
    * ASUS PRIME X399-A
    * ASUS PRIME B450M-Gaming
    * ASUS PRIME Z270-A
    * ASUS PRIME Z370-A
    * ASUS ROG Crosshair VI Hero
    * ASUS ROG STRIX X399-E Gaming
    * ASUS ROG Strix B450-F Gaming
    * ASUS ROG Strix Z370-E
    * ASUS TUF B450 Plus Gaming
* [ASUS Aura (USB Variants)](ASUS Aura USB)
    * [ASUS Aura Addressable Headers](ASUS-Aura-Addressable-Header)
    * ASUS X570 Motherboards
* [Gigabyte Aorus RGB Fusion 1.0](Gigabyte-RGB-Fusion-1.0)
    * Gigabyte Aorus X370 Gaming 5
* Gigabyte Aorus RGB Fusion 2.0 (SMBus) (EXPERIMENTAL)
    * Disabled by default because we don't have appropriate detection code yet, and it has an address conflict that could brick Z390 Aorus boards.
    * Uncomment DetectRGBFusion2SMBusControllers call in OpenRGB.cpp if you wish to use.
    * ONLY run this on supported motherboards!!!!!
* Gigabyte Aorus RGB Fusion 2.0 (USB)
    * Gigabyte X570 Aorus Extreme
    * Gigabyte X570 Aorus Master
    * Gigabyte X570 Aorus Pro
    * Gigabyte X570 Gaming X
    * Gigabyte X570 I Aorus Pro Wifi
    * Gigabyte TRX40 Aorus Master
    * Gigabyte Z390 Aorus Ultra
* [ASRock Polychrome RGB](ASRock-Polychrome-RGB)
    * ASRock Steel Legend B450M
    * ASRock Fatal1ty B350 Gaming-ITX/ac
    * ASRock B450M/ac
    * ASRock X570 Taichi
* [MSI-RGB](MSI-RGB)
* MSI Mystic Light

### RGB RAM Modules

* [ASUS Aura Based](ASUS-Aura-Overview)
    * G.Skill Trident Z RGB
    * G.Skill Trident Z Neo
    * G.Skill Trident Z Royal
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
* [Crucial Ballistix RGB](Crucial-Ballistix-RGB)
* [Gigabyte Aorus RGB RAM (Partial support)](Gigabyte-RGB-Fusion-2.0-DRAM)

### Graphics Cards

* [ASUS Aura GPUs](Asus-Aura-GPU)
* [Gigabyte Aorus RGB Fusion GPUs](Gigabyte-RGB-Fusion-GPU)
    * Gigabyte Aorus GTX1080Ti Xtreme Waterforce WB

### LED Strip and Fan Controllers

* [ASUS ROG Aura Terminal](ASUS-Aura-Addressable-Header)
* [NZXT Hue+](NZXT-Hue-Plus)
* [NZXT Hue 2 Devices](NZXT-Hue-2)
    * NZXT Hue 2
    * NZXT Hue 2 Ambient
    * NZXT Smart Device V2
    * NZXT RGB & Fan Controller
* [Corsair Lighting Node Devices](Corsair-Lighting-Node-Devices)
    * Corsair Lighting Node Core
    * Corsair Lighting Node Pro
    * Corsair Commander Pro
    * Corsair LS100
    * [Corsair Lighting Protocol (Arduino)](https://github.com/Legion2/CorsairLightingProtocol)
* [Keyboard Visualizer Arduino LED strips](Keyboard-Visualizer-LED-Strips)
* [E1.31 Streaming ACN Protocol](E1.31)
    * [ESPixelStick](https://github.com/forkineye/ESPixelStick)
    * [WLED](https://github.com/Aircoookie/WLED)
* [Thermaltake Riing Plus](Thermaltake-Riing)

### Fans and Coolers

* [AMD Wraith Prism](AMD-Wraith-Prism)
* NZXT Kraken X42/X52/X62/X72

### Keyboards

* [ASUS ROG Aura Core Laptops](ASUS-Aura-Core)
* [Corsair RGB Keyboards](Corsair-Peripheral-Protocol)
    * Corsair K65 RGB
    * Corsair K65 Lux RGB
    * Corsair K65 RGB Rapidfire
    * Corsair K68 RGB
    * Corsair K70 RGB
    * Corsair K70 Lux RGB
    * Corsair K70 RGB Rapidfire
* [HyperX Alloy Elite](HyperX-Alloy-Elite)
* [Logitech RGB Keyboards](Logitech-Keyboards)
    * Logitech G512
    * Logitech G810 Orion Spectrum
* [MSI Steelseries 3-Zone Keyboard](MSI-3-Zone-Keyboard)
    * MSI GS63VR
* [Redragon Keyboards (and compatibles)](Redragon-K556-Devarajas)
    * Redragon K550 Yama
    * Redragon K552 Kumara
    * Redragon K556 Devarajas
    * Tecware Phantom Elite
    * Warrior Kane TC235
* [TTEsports Poseidon Z RGB](Thermaltake-Poseidon-Z-RGB)

### Mice

* [Corsair Mice](Corsair-Peripheral-Protocol)
    * Corsair M65 Elite
* Glorious Model O
* [Logitech Mice](Logitech-G203)
    * Logitech G203 Prodigy
    * Logitech G403 Prodigy
* [Redragon Mice](Redragon-M711-Cobra)
    * Redragon M711 Cobra
    * Redragon M715 Dagger
* SteelSeries Rival 100 and 300 series

### Mousemats

* Corsair MM800 Polaris

### Other

* Corsair ST100 Headset Stand

### Other projects integrated

* [OpenRazer](https://github.com/openrazer/openrazer) / [OpenRazer-Win32](https://github.com/CalcProgrammer1/openrazer-win32)
    * Keyboards
        * Razer BlackWidow Chroma
        * Razer BlackWidow Chroma V2
        * Razer BlackWidow Chroma Tournament Edition
        * Razer BlackWidow X Tournament Edition Chroma
        * Razer Ornata Chroma
        * Razer Huntsman Elite
    * Mice
        * Razer DeathAdder Chroma
        * Razer DeathAdder Elite
        * Razer Diamondback
        * Razer Mamba Elite
        * Razer Mamba Tournament Edition
        * Razer Naga Chroma
        * Razer Naga Epic Chroma (*)
    * Laptops
        * Razer Blade Stealth
        * Razer Blade Pro (2017)
    * Headsets
        * Razer Kraken 7.1 Chroma
        * Razer Kraken V2 Chroma
        * Razer Tiamat 7.1 V2 (*)
    * Mousemats
        * Razer Firefly
        * Razer Goliathus Extended Chroma
    * Speakers
        * Razer Nommo Chroma
        * Razer Nommo Pro
    * Accessories
        * Razer Base Station Chroma
        * Razer Chroma HDK
        * Razer Core
        * Razer Mug Holder Chroma

(*) - Device not supported in upstream OpenRazer and requires a custom build.

* Faustus (ASUS TUF Laptop Keyboards) (Linux)

## History of OpenRGB

OpenRGB is a continuation of OpenAuraSDK, which itself was created out of reverse engineering work done on the Keyboard Visualizer project.  For a complete history of the RGB projects that led to OpenRGB's creation, see the [History page](History-of-OpenRGB).