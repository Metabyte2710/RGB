# Common (applies to both Windows and Linux)

## Why do I have an ASUS Aura DRAM device when I don't have an ASUS motherboard?

Many RGB RAM vendors use an RGB control chip that is nearly identical to the one found on early ASUS Aura motherboards.  Vendors using this controller include G.Skill, Geil, T-Force, A-DATA, and possibly others.  OpenRGB shows all of these devices as "ASUS Aura DRAM" as they use the same driver as the ASUS Aura motherboards with this chip.

## I have an ASUS and/or Gigabyte GPU that's not being detected.

OpenRGB has support for ASUS Aura GPUs and Gigabyte RGB Fusion GPUs.  However, because these vendors are always improving their products and putting more and more RGB, it's possible your GPU uses a different ASUS Aura or RGB Fusion control chip than the one that OpenRGB supports.  The two GPU implementations in OpenRGB only support single lighting zone GPUs.  If your GPU has more than one lighting zone, it is likely not supported.  I would be glad to help add support for more GPUs, but unfortunately reverse engineering GPUs is fairly complicated and requires a good deal of technical expertise.  GPUs are the most difficult RGB devices to reverse engineer that we know of.

# Windows

## OpenRGB won't detect my RAM or Motherboard

OpenRGB uses an interface called SMBus (also referred to as I2C) to communicate with RGB controllers on RAM modules and some motherboards.  On Windows, SMBus access requires administrator privileges using a library called inpout32 (inpoutx64 for the 64-bit version).  You must run OpenRGB as administrator at least once for inpout32 to set up.  Once it has been set up, you may run OpenRGB without administrator and it will be able to access these devices.

If you have problems accessing these devices even after running as administrator, it is possible that a kernel anti-cheat or anti-virus application is blocking the inpout32 driver from functioning.  Riot Games' Vanguard (VALORANT) anti-cheat system has been known to block inpout32 as well as some official RGB applications.  If you have VALORANT installed, you will have to uninstall it or disable the Vanguard anti-cheat in order to use OpenRGB with these devices.

If you do not have such an anti-cheat system installed and are still having problems, make sure any other RGB applications (ASUS Aura, Corsair iCUE, Gigabyte RGB Fusion, etc) are disabled or uninstalled.  This includes disabling their background services.  The SMBus only works properly if one application at a time is accessing it, and if two applications try to control the device at the same time, it can confuse the device or put it in an invalid state.  This behavior can result in OpenRGB not detecting devices properly.

# Linux

## My Razer devices aren't being detected

OpenRGB uses the OpenRazer kernel drivers in Linux.  Most distributions provide OpenRazer packages.  You do not need the OpenRazer daemon but you do need the kernel drivers installed.

## My non-Razer USB devices aren't being detected

You need to install the OpenRGB udev rules.  These are provided in the 99-openrgb.rules file in this repository.  Copy this file to /etc/udev/rules.d and then trigger a rules reload with the following commands:

sudo udevadm control --reload-rules

sudo udevadm trigger