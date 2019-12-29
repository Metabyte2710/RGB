The NZXT Hue 2 is an LED strip controller for PC case lighting. It connects to the motherboard using USB. It enumerates a USB device with VID 1E71, PID 2001. The commands are sent to using USB interrupt transfers.

# Direct Packet Structure - 64 Bytes

| Byte index | Function   | Description                           |
| ---------- | ---------- | ------------------------------------- |
| 0x00       | 0x22       |                                       |
| 0x01       | LED group  | 0x10 for first 20, 0x11 for second 20 |
| 0x02       | Channel    | 1, 2, 3, or 4                         |
| 0x03       | 0x00       |                                       |
| 0x04+      | Color Data | 20x (G, R, B) for 60 bytes total      |

# Apply Direct Packet

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

# Get Attached Devices
Device type 0x04 is 10-LED Hue 2 strip.

## Request
| Byte index | Function            | Description                           |
| ---------- | ------------------- | ------------------------------------- |
| 0x00       | 0x20                |                                       |
| 0x01       | 0x03                |                                       |
| 0x02 - end | 0x00                |                                       |

## Response
| Byte index | Function            | Description                           |
| ---------- | ------------------- | ------------------------------------- |
| 0x00       | 0x21                |                                       |
| 0x01       | 0x03                |                                       |
| 0x02       | 0x33                |                                       |
| 0x03       | 0xFF                |                                       |
| 0x04       | 0x70                |                                       |
| 0x05       | 0x06                |                                       |
| 0x06       | 0x53                |                                       |
| 0x07       | 0x55                |                                       |
| 0x08       | 0x34                |                                       |
| 0x09       | 0x33                |                                       |
| 0x0A       | 0x55                |                                       |
| 0x0B       | 0x24                |                                       |
| 0x0C       | 0x18                |                                       |
| 0x0D       | 0x51                |                                       |
| 0x0E       | 0x04                |                                       |
| 0x0F       | Channel 0, Device 0 | Device type                           |
| 0x10       | Channel 0, Device 1 | Device type                           |
| 0x11       | Channel 0, Device 2 | Device type                           |
| 0x12       | Channel 0, Device 3 | Device type                           |
| 0x13       | Channel 0, Device 4 | Device type                           |
| 0x14       | Channel 0, Device 5 | Device type                           |
| 0x15       | Channel 1, Device 0 | Device type                           |
| 0x16       | Channel 1, Device 1 | Device type                           |
| 0x17       | Channel 1, Device 2 | Device type                           |
| 0x18       | Channel 1, Device 3 | Device type                           |
| 0x19       | Channel 1, Device 4 | Device type                           |
| 0x1A       | Channel 1, Device 5 | Device type                           |
| 0x1B       | Channel 2, Device 0 | Device type                           |
| 0x1C       | Channel 2, Device 1 | Device type                           |
| 0x1D       | Channel 2, Device 2 | Device type                           |
| 0x1E       | Channel 2, Device 3 | Device type                           |
| 0x1F       | Channel 2, Device 4 | Device type                           |
| 0x20       | Channel 2, Device 5 | Device type                           |
| 0x21       | Channel 3, Device 0 | Device type                           |
| 0x22       | Channel 3, Device 1 | Device type                           |
| 0x23       | Channel 3, Device 2 | Device type                           |
| 0x24       | Channel 3, Device 3 | Device type                           |
| 0x25       | Channel 3, Device 4 | Device type                           |
| 0x26       | Channel 3, Device 5 | Device type                           |
| 0x27 - end | 0x00                |                                       |