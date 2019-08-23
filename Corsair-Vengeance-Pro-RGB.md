The Corsair Vengeance Pro RGB memory enumerates an SMBus device in the address range 0x58-0x5D.  This device uses a command based communication protocol, where a defined command packet is issued to a single SMBus address.  The device also has a completion flag that must be polled after issuing a command.  The device will not accept another command until the flag has cleared.

To start a command, two bytes are written before writing to the command register.  This start frame indicates which command format will be sent.

There are two known command formats:

| Value | Command | Length |
| ------ | ------ | ------ |
| 0x01 | Set Mode | 20 Bytes |
| 0x02 | Set Custom Colors | 40 bytes |

The complete send sequence looks like this:

Write <Command Format> to 0x26
Write 0x00 to 0x21

Send command packet to 0x20

Write <Command Format> to 0x82

Finally, the software reads the register 0x41 and waits until it returns 0x00.  This indicates the controller has accepted the command and is ready for the next command.

