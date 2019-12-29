The NZXT Hue 2 is an LED strip controller for PC case lighting. It connects to the motherboard using USB. It enumerates a USB device with VID 1E71, PID 2001. The commands are sent to using USB interrupt transfers.

# Direct Packet Structure - 64 Bytes

| Byte index | Function   | Description                           |
| ---------- | ---------- | ------------------------------------- |
| 0x00       | 0x22       |                                       |
| 0x01       | LED group  | 0x10 for first 20, 0x11 for second 20 |
| 0x02       | Channel    | 1, 2, 3, or 4                         |
| 0x03       | 0x00       |                                       |
| 0x04+      | Color Data | 20x (G, R, B) for 60 bytes total      |

# Effect Packet Structure - 64 Bytes

| Byte index | Function    | Description                           |
| ---------- | ----------- | ------------------------------------- |
| 0x00       | 0x28        |                                       |
| 0x01       | 0x03        |                                       |
| 0x02       | Channel     | 1, 2, 3, or 4                         |
| 0x03       | 0x28        |                                       |
| 0x04       | Mode        |                                       |
| 0x05       | ?           |                                       |
| 0x06       | ?           |                                       |
| 0x07       | ?           |                                       |
| 0x08       | Color Count |                                       |
| 0x09       | ?           |                                       |
| 0x0A+      | Color Data  | G, R, B color data                    |

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

# Apply packet?

| Byte index | Function    | Description                           |
| ---------- | ----------- | ------------------------------------- |
| 0x00       | 0x22        |                                       |
| 0x01       | 0xA0        |                                       |
| 0x02       | Channel     | 1, 2, 3, or 4                         |
| 0x03       | 0x00        |                                       |
| 0x04       | 0x01        |                                       |
| 0x05       | 0x00        |                                       |
| 0x06       | 0x00        |                                       |
| 0x07       | 0x28        |                                       |
| 0x08       | 0x00        |                                       |
| 0x09       | 0x00        |                                       |
| 0x0A       | 0x80        |                                       |
| 0x0B       | 0x00        |                                       |
| 0x0C       | 0x32        |                                       |
| 0x0D       | 0x00        |                                       |
| 0x0E       | 0x00        |                                       |
| 0x0F       | 0x01        |                                       |
| 0x10 - end | 0x00        |                                       |