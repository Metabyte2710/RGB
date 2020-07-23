MSI's line of GeForce RTX 2xxx series graphics cards include RGB lighting via an I2C controller at address 0x68 on the GPU I2C bus.  We were unable to determine a good method of probing the I2C device directly, especially as it is on address 0x68 which is known to be a potential brick risk for some Gigabyte Z390 boards.  Instead, we're using the PCI subvendor IDs to identify and detect these cards.

# Supported Devices

Note: Vendor and Device ID represent the nVidia GPU chipset and will be common to all cards using that chipset, even non-MSI cards.  The sub-vendor and sub-device IDs are MSI specific.

| PCI Vendor ID | PCI Device ID | PCI Sub-Vendor ID | PCI Sub-Device ID | Device Name                        |
| ------------- | ------------- | ----------------- | ----------------- | ---------------------------------- |
| 0x10DE        | 0x1F06        | 0x1462            | 0xC752            | MSI GeForce RTX2060 Super Gaming X |