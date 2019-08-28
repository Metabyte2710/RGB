![20190630_122649](/uploads/95e6e067b974595cba13163797dbaff0/20190630_122649.jpg)

![20190630_122624](/uploads/08cd8c470b8b825bd253fd66a18fa938/20190630_122624.jpg)

The Corsair Vengeance RGB memory enumerates an SMBus device in the address range 0x58-0x5D.  This device uses SMBus byte commands to control its single RGB zone.

**Commands**

| Command | Function |
| ------ | ------ |
| 0xA4 | Fade time (0 for static/no fading) |
| 0xA5 | Hold time | 
| 0xA6 | Mode |
| 0xB0 | Red |
| 0xB1 | Green |
| 0xB2 | Blue |

**Modes**

| Mode Value | Mode |
| ------ | ------ |
| 0x00 | Single color (static or pulsing) |
| 0x01 | Fade through colors |
| 0x02 | Pulse through colors |

There may be additional color commands for the fade/pulse sequences.  I have not discovered these, but my guess is the Asus Aura support for Corsair RGB doesn't change these colors.  I used the Asus Aura app to reverse engineer this controller.