The NZXT Hue 2 is an LED strip controller for PC case lighting. It connects to the motherboard using USB. It enumerates a USB device with VID 1E71, PID 2001. The commands are sent to using USB interrupt transfers.

Main Packet Structure - 64 Bytes

| Byte index | Function   | Description                         |
| ---------- | ---------- | ----------------------------------- |
| 0x00       | Fixed 0x22 |                                     |
| 0x01       | Mode       | Also selects which group of LEDs    |
| 0x02       | Channel    | 1, 2, 3, or 4                       |
| 0x03       | 0x00       |                                     |
| 0x04+      | Color Data | 20x (G, R, B) for 60 bytes total    |