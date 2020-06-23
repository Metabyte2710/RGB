NZXT's Hue 2 ecosystem includes several LED and fan controller devices along with a series of ARGB strips and fans which feature an additional detection wire.  Each Hue 2 channel can connect up to 6 devices and automatically detect the sequence of connected devices.  NZXT Hue 2 channels can also connect NZXT Hue 1 devices (i.e. those designed for the Hue Plus) but you cannot mix and match these.  You also cannot mix and match Hue 1 and Hue 2 devices on the same channel.

The Hue 2 uses the USB HID protocol with 64-byte reads and writes.

# Devices

| USB VID | USB PID | Hue 2 ARGB Channels | Fan Channels | Device Name               |
| ------- | ------- | ------------------- | ------------ | ------------------------- |
| 0x1E71  | 0x2001  | 4                   | 0            | NZXT Hue 2                |
| 0x1E71  | 0x2002  | 2                   | 0            | NZXT Hue 2 Ambient        |
| 0x1E71  | 0x2006  | 2                   | 3            | NZXT Smart Device V2      |
| 0x1E71  | 0x2009  | 2                   | 3            | NZXT RGB & Fan Controller |

# Direct Packet Structure

| Byte index | Function   | Description                           |
| ---------- | ---------- | ------------------------------------- |
| 0x00       | 0x22       |                                       |
| 0x01       | LED group  | 0x10 for first 20, 0x11 for second 20 |
| 0x02       | Channel    | Bitfield, 1, 2, 4, or 8               |
| 0x03       | 0x00       |                                       |
| 0x04+      | Color Data | 20x (G, R, B) for 60 bytes total      |

# Apply Direct Packet

| Byte index | Function    | Description                           |
| ---------- | ----------- | ------------------------------------- |
| 0x00       | 0x22        |                                       |
| 0x01       | 0xA0        |                                       |
| 0x02       | Channel     | Bitfield, 1, 2, 4, or 8               |
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

# Effect Packet Structure

| Byte index | Function    | Description                           |
| ---------- | ----------- | ------------------------------------- |
| 0x00       | 0x28        |                                       |
| 0x01       | 0x03        |                                       |
| 0x02       | Channel     | Bitfield, 1, 2, 4, or 8               |
| 0x03       | 0x28        |                                       |
| 0x04       | Mode        |                                       |
| 0x05       | Speed       | 0: Slowest, 4: Fastest                |
| 0x06       | Direction   | 0 or 1                                |
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

# Get Firmware Information

## Request
| Byte index | Function            | Description                           |
| ---------- | ------------------- | ------------------------------------- |
| 0x00       | 0x10                |                                       |
| 0x01       | 0x01                |                                       |
| 0x02 - end | 0x00                |                                       |

## Response
| Byte index | Function            | Description                           |
| ---------- | ------------------- | ------------------------------------- |
| 0x11       | Firmware XX         | Display as XX.YY.ZZ                   |
| 0x12       | Firmware YY         |                                       |
| 0x13       | Firmware ZZ         |                                       |

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

# Device Types

| Device type value | Device                | Number of LEDs |
| ----------------- | --------------------- | -------------- |
| 0x01              | Hue Plus LED Strip    | 10             |
| 0x02              | Aer 1 RGB Fan         | 8              |
| 0x04              | Hue 2 LED Strip       | 10             |
| 0x0B              | Aer 2 RGB Fan (120mm) | 8              |
| 0x0C              | Aer 2 RGB Fan (140mm) | 8              |