The Aura system uses one or more Aura controller chips connected via the [System Management Bus (SMBus)](https://en.wikipedia.org/wiki/System_Management_Bus) of the PC.  SMBus is an extended version of the [I<sup>2</sup>C](https://en.wikipedia.org/wiki/I%C2%B2C) interface, which is a common low-level serial bus found on many embedded devices.  I<sup>2</sup>C uses a master-slave topology, with one master device (the PC) able to send and receive data from one or more slave devices (the Aura controllers).

On motherboards, the SMBus master is usually part of the chipset and/or Super IO chip.  Windows does not provide user-accessible drivers for transferring data on the SMBus interfaces, but Linux does.  The [i2c-tools package](https://i2c.wiki.kernel.org/index.php/I2C_Tools) provides user-accessible set, get, and detect functions to talk to I<sup>2</sup>C/SMBus devices on your PC's motherboard.  This was very beneficial in early Aura reverse engineering efforts.

Since Windows does not provide useful SMBus drivers, we need to provide our own user-mode drivers for all the SMBus controllers we intend to support.  Luckily, the Linux source code has I<sup>2</sup>C/SMBus drivers for a wide variety of chipsets we can borrow.  The [inpout32 library](http://www.highrez.co.uk/downloads/inpout32/) allows Windows programs to access "I/O port" memory regions on x86/x64 processors.  This memory region is where the memory-mapped control registers for most SMBus controllers reside.  Combining the Linux i2c source code with inpout32 to set the registers we can port SMBus controller drivers to Windows.  I have already done so for the i2c_smbus_piix4 driver as that's what my AMD X370 chipset uses.

Some chipsets (such as the AMD X370) have multiple SMBus interfaces.  During our reverse engineering efforts, we discovered that there were two identical register sets at 0xB000 and 0xB020 on the X370, with the RAM SMBus on 0xB000 and the onboard Aura controller SMBus on 0xB020.  The Linux driver didn't see this second bus but a quick kernel hack later and it was working.  Luckily on our user-space Windows driver we can just edit the base register address to talk to both buses.

Intel chipsets appear to only have a single SMBus interface.  Asus used this interface to communicate with the RAM.  For the on-board Aura controller, they used the SMBus interface in the Super IO chip.  Unfortunately, Linux does not provide drivers for the SMBus interface on the Super IO controller so I will be writing my own.

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