The Crucial Ballistix RGB RAM enumerates an SMBus device at address 0x21.  It appears to use a 16-bit register scheme similar to Aura, but not exactly the same.  16-bit address values are written to 0x00 followed by byte value writes to 0x01.  Bytes are read from 0x81.  The modules have 8 LEDs each.

0x8300 seems to be the base register for red.  8 red bytes are written into 0x01 after writing 0x8300 to 0x00.

0x8340 seems to be the base register for green.  8 green bytes are written into 0x01 after writing 0x8340 to 0x00.

0x8380 seems to be the base register for blue.  8 blue bytes are written into 0x01 after writing 0x8380 to 0x00.