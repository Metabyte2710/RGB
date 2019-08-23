The Corsair Vengeance Pro RGB memory enumerates an SMBus device in the address range 0x58-0x5D.  This device uses a command based communication protocol, where a defined command packet is issued to a single SMBus address.  The device also has a completion flag that must be polled after issuing a command.  The device will not accept another command until the flag has cleared.

To start a command, two bytes are written before writing to the command register.  This start frame indicates which command format will be sent.

There are two known command formats:

| Value | Command | Length |
| ------ | ------ | ------ |
| 0x01 | Set Mode | 20 Bytes |
| 0x02 | Set Custom Colors | 40 bytes |

The complete send sequence looks like this:

1. Write <Command Format> to 0x26
2. Write 0x00 to 0x21
3. Send command packet to 0x20
4. Write <Command Format> to 0x82

Finally, the software reads the register 0x41 and waits until it returns 0x00.  This indicates the controller has accepted the command and is ready for the next command.

**Set Mode Packet**

The Set Mode packet sets the controller's effect, speed, direction, and effect colors.

| Byte | Function |
| ------ | ------ |
| 0x00 | Mode |
| 0x01 | Speed | 
| 0x02 | Custom color |
| 0x03 | Direction |
| 0x04 | Custom color 1 Red |
| 0x05 | Custom color 1 Green |
| 0x06 | Custom color 1 Blue |
| 0x07 | 0xFF |
| 0x08 | Custom color 2 Red |
| 0x09 | Custom color 2 Green |
| 0x0A | Custom color 2 Blue |
| 0x0B | 0xFF |
| 0x0C | 0x00 |
| 0x0D | 0x00 |
| 0x0E | 0x00 |
| 0x0F | 0x00 |
| 0x10 | 0x00 |
| 0x11 | 0x00 |
| 0x12 | 0x00 |
| 0x13 | 0x00 |

Modes

| Value | Name | Speeds | Custom Colors | Directions |
| ------ | ------ | ------ | ------ | ------ |
| 0x00 | Color Shift | S/M/F | Random/Alternating | None |
| 0x01 | Color Pulse | S/M/F | Random/Alternating | None |
| 0x02 | ? | ? | ? | ? |
| 0x03 | Rainbow Wave | S/M/F | None | Up/Down/Left/Right |
| 0x04 | Color Wave | S/M/F | Random/Alternating | Up/Down/Left/Right |
| 0x05 | Visor | S/M/F | Random/Alternating | Horizontal/Vertical |
| 0x06 | Rain | S/M/F | Random/Alternating | Up/Down |
| 0x07 | Marquee | S/M/F | Single | None |
| 0x08 | Rainbow | S/M/F | None | None |
| 0x09 | Sequential | S/M/F | Random/Single | Up/Down |