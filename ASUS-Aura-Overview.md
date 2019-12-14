![AsusZ270Prime-A](uploads/7e85b9c03aaec294a2e38b9f5c4886f0/AsusZ270Prime-A.jpg)

ASUS's Aura lighting system uses one or more custom AURA controllers on [SMBus](SMBus-Interface-Details).  Most boards have the controller enumerate at address 0x4E, though some boards use other addresses.  It also appears that some boards use a USB interface, particularly those with an addressable RGB header and X570 generation boards.  These USB controllers are not covered by this project yet.

Aura controllers appear to use an internal register layout.  There are internal addresses.  They appear to use a reversed byte ordering from the Linux i2c-tools.

For 8-bit I<sup>2</sup>C device ID **dev** and 16-bit register address **reg**:

Write:

```
    //Write Aura register
    bus->i2c_smbus_write_word_data(dev, 0x00, ((reg << 8) & 0xFF00) | ((reg >> 8) & 0x00FF));

    //Write Aura value
    bus->i2c_smbus_write_byte_data(dev, 0x01, val);
```

Read:

```
    //Write Aura register
    bus->i2c_smbus_write_word_data(dev, 0x00, ((reg << 8) & 0xFF00) | ((reg >> 8) & 0x00FF));

    //Read Aura value
    return(bus->i2c_smbus_read_byte_data(dev, 0x81));
```

Write colors block:

```
    //Write Aura register (0x8000 for colors)
    bus->i2c_smbus_write_word_data(dev, 0x00, ((AURA_REG_COLORS << 8) & 0xFF00) | ((AURA_REG_COLORS >> 8) & 0x00FF));

    //Write Aura color array
    bus->i2c_smbus_write_block_data(dev, 0x03, 15, colors);
```

## [Aura Controller Registers](Aura-Controller-Registers)

The SMBus Aura controllers use a register write system to set colors and settings.  The register memory space is 16 bits (0x0000-0xFFFF) and appears to contain the Aura controller's firmware, non-volatile settings, volatile settings, and some other information.  The color control registers are in the 0x8000 memory block.

## [Aura Software Information](Aura-Software-Information)

## [Known Motherboards](Known-Motherboards)

List of motherboards with their SMBus and Aura controller information.