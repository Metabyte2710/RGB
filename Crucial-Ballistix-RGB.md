The Crucial Ballistix RGB RAM enumerates an SMBus device at address 0x21.  It appears to use a 16-bit register scheme similar to Aura, but not exactly the same.  16-bit address values are written to 0x00 followed by byte value writes to 0x01.  Bytes are read from 0x81.  The modules have 8 LEDs each.

The controller appears to use a message packet interface.  There are multiple packet types and the type is indicated by the final write in the sequence, always to register 0x82F0.

# Effect Color (0x01)

| Address | Function |
| ------- | -------- |
| 0x820F  | 0x08     |
| 0x82E9  | 0xFF     |
| 0x82EA  | 0x00     |
| 0x82EB  | 0x00     |
| 0x82EC  | 0x00     |
| 0x82ED  | Red      |
| 0x82EE  | Green    |
| 0x82EF  | Blue     |
| 0x82F0  | 0x01     |

# Brightness (0x83)

| Address | Function               |
| ------- | ---------------------- |
| 0x82EE  | 0xFF                   |
| 0x82FF  | Brightness (0x00-0xFF) |
| 0x82F0  | 0x83                   |

# Effect Mode / Speed (0x84)

0x820F - Effect 2?

0xAF - Water Wave

0xCF - Static

0x82E9

0x82EA 

0x82EB

0x82EC

0x82ED - Effect Red

0x82EE - Effect Green

0x82EF - Effect Blue

0x15 - Gradient Shift

0x16 - Shift

0x17 - Fill

0x18 - Stack

0x19 - Double Stack

0x1A - Breathing

0x1B - Motion Point

0x1C - Inside Out

0x1D - Color Step

0x1E - Flashing, Static, Water Wave

0x82F0 - Apply Changes, 0x01 or 0x84 (possibly saving?)

0x8300 seems to be the base register for red.  8 red bytes are written into 0x01 after writing 0x8300 to 0x00.  Gets automatically updated when effect modes are applied.

0x8340 seems to be the base register for green.  8 green bytes are written into 0x01 after writing 0x8340 to 0x00.

0x8380 seems to be the base register for blue.  8 blue bytes are written into 0x01 after writing 0x8380 to 0x00.