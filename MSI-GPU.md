MSI's line of GeForce RTX 2xxx series graphics cards include RGB lighting via an I2C controller at address 0x68 on the GPU I2C bus.  We were unable to determine a good method of probing the I2C device directly, especially as it is on address 0x68 which is known to be a potential brick risk for some Gigabyte Z390 boards.  Instead, we're using the PCI subvendor IDs to identify and detect these cards.

# Supported Devices

Note: Vendor and Device ID represent the nVidia GPU chipset and will be common to all cards using that chipset, even non-MSI cards.  The sub-vendor and sub-device IDs are MSI specific.

| PCI Vendor ID | PCI Device ID | PCI Sub-Vendor ID | PCI Sub-Device ID | Device Name                              |
| ------------- | ------------- | ----------------- | ----------------- | ---------------------------------------- |
| 0x10DE        | 0x1F06        | 0x1462            | 0xC752            | MSI GeForce RTX 2060 Super Gaming X      |
| 0x10DE        | 0x1E84        | 0x1462            | 0xC726            | MSI GeForce RTX 2070 Super Gaming X Trio |
| 0x10DE        | 0x1E87        | 0x1462            | 0x3726            | MSI GeForce RTX 2080 Gaming X Trio       |
| 0x10DE        | 0x1E81        | 0x1462            | 0xC724            | MSI GeForce RTX 2080 Super Gaming X Trio |
| 0x10DE        | 0x1E07        | 0x1462            | 0x3715            | MSI GeForce RTX 2080Ti Gaming X Trio     |
| 0x10DE        | 0x1F08        | 0x1462            | 0x3754            | MSI GeForce RTX 2060 Gaming Z 6G         |
| 0x10DE        | 0x1F06        | 0x1462            | 0xC754            | MSI GeForce RTX 2060 Super ARMOR OC      |
| 0x10DE        | 0x1F02        | 0x1462            | 0x3734            | MSI GeForce RTX 2070 ARMOR               |
| 0x10DE        | 0x1E07        | 0x1462            | 0x3717            | MSI GeForce RTX 2080Ti Sea Hawk EK X     |

# I2C Registers

| Register Address | Register Description |
| ---------------- | -------------------- |
| 0x36             | Brightness           |
| 0x38             | Speed                |
| 0x26             |                      |
| 0x30             | Red 1                |
| 0x31             | Green 1              |
| 0x32             | Blue 1               |
| 0x27             | Red 2                |
| 0x28             | Green 2              |
| 0x29             | Blue 2               |
| 0x2A             | Red 3                |
| 0x2B             | Green 3              |
| 0x2C             | Blue 3               |
| 0x22             | Mode                 |
| 0x3F             | Apply                |

# Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x01       | Off              |
| 0x08       | Rainbow          |
| 0x13       | Static           |
| 0x1A       | Raindrop         |
| 0x07       | Magic            |
| 0x05       | Patrolling       |
| 0x06       | Streaming        |
| 0x15       | Lightning        |
| 0x1F       | Wave             |
| 0x16       | Meteor           |