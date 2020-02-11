Some MSI motherboards use the Super IO chip's PWM controllers to drive RGB channels.  This system presents an interface quite different from the others that OpenRGB supports.  There is a project that implements control of these boards already:

https://github.com/nagisa/msi-rgb

Supported Super-IO chips:

* Nuvoton NCT6795 (0xD350)

* Nuvoton NCT6797 (0xD450)

The RGB control registers are in bank 0x12.

| Register | Function |
| -------- | -------- |
| 0xE0     | Color channel enable, 0bRGB00000, full on when disabled |
| 0xE4     | Smooth pulsing |
| 0xF0     | Red 0 and 1    |
| 0xF1     | Red 2 and 3    |
| 0xF2     | Red 4 and 5    |
| 0xF3     | Red 6 and 7    |
