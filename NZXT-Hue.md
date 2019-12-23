The NZXT Hue+ is an LED strip controller for PC case lighting.  It connects to the motherboard using USB.  It enumerates a USB serial interface with VID 04D8, PID 00DF (Microchip MCP2200).  The commands are sent to the corresponding serial port.

# Packet Structure

| Byte index | Function   | Description                         |
| ---------- | ---------- | ----------------------------------- |
| 0x00       | Fixed 0x4B |                                     |
| 0x01       | Channel    | 0: Both, 1: Channel 1, 2: Channel 2 |
| 0x02       | Mode       | See Modes section below             |
| 0x03       |            |                                     |
| 0x04       |            |                                     |
| 0x05+      | Color Data | 40x (G, R, B) for 120 bytes total   |

# Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x00       | Fixed            |
| 0x01       | Fading           |
| 0x02       | Spectrum Cycle   |
| 0x03       | Marquee          |
| 0x04       | Cover Marquee    |
| 0x05       | Alternating      |
| 0x06       | Pulsing          |
| 0x07       | Breathing        |
| 0x08       | Alert            |
| 0x09       | Candlelight      |
| 0x0A       |                  |
| 0x0B       |                  |
| 0x0C       | Wings            |
| 0x0D       | Wave             |
| 0x0E       | Direct           |