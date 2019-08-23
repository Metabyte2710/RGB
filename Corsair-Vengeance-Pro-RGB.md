![20190630_122720](/uploads/c45540b398b97d3e89bbb61d984426cd/20190630_122720.jpg)

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

| Byte | Function | Value |
| ------ | ------ | ------ |
| 0x00 | Mode | See Modes table |
| 0x01 | Speed | 0: Slow, 1: Medium, 2: Fast |
| 0x02 | Custom color | 0: Random colors, 1: Custom colors |
| 0x03 | Direction | 0: Up, 1: Down, 2: Left, 3: Right, 1: Vertical, 3: Horizontal |
| 0x04 | Custom color 1 Red | Used if Custom color is 1 |
| 0x05 | Custom color 1 Green | Used if Custom color is 1 |
| 0x06 | Custom color 1 Blue | Used if Custom color is 1 |
| 0x07 | Fixed | 0xFF |
| 0x08 | Custom color 2 Red | Used if Custom color is 1 |
| 0x09 | Custom color 2 Green | Used if Custom color is 1 |
| 0x0A | Custom color 2 Blue | Used if Custom color is 1 |
| 0x0B | Fixed | 0xFF |
| 0x0C | Fixed | 0x00 |
| 0x0D | Fixed | 0x00 |
| 0x0E | Fixed | 0x00 |
| 0x0F | Fixed | 0x00 |
| 0x10 | Fixed | 0x00 |
| 0x11 | Fixed | 0x00 |
| 0x12 | Fixed | 0x00 |
| 0x13 | Fixed | 0x00 |

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