NZXT's Hue 2 ecosystem includes several LED and fan controller devices along with a series of ARGB strips and fans which feature an additional detection wire.  Each Hue 2 channel can connect up to 6 devices and automatically detect the sequence of connected devices.  NZXT Hue 2 channels can also connect NZXT Hue 1 devices (i.e. those designed for the Hue Plus) but you cannot mix and match these.  You also cannot mix and match Hue 1 and Hue 2 devices on the same channel.

The Hue 2 uses the USB HID protocol with 64-byte reads and writes.

# Descriptor

<details>
<summary>Click to see content</summary>
<code>
0x06, 0x00, 0xFF,  // Usage Page (Vendor Defined 0xFF00)
0x09, 0x01,        // Usage (0x01)
0xA1, 0x01,        // Collection (Application)
0x85, 0x10,        //   Report ID (16)
0x09, 0x01,        //   Usage (0x01)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x10,        //   Report ID (16)
0x09, 0x01,        //   Usage (0x01)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x12,        //   Report ID (18)
0x09, 0x02,        //   Usage (0x02)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x12,        //   Report ID (18)
0x09, 0x02,        //   Usage (0x02)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x20,        //   Report ID (32)
0x09, 0x03,        //   Usage (0x03)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x20,        //   Report ID (32)
0x09, 0x03,        //   Usage (0x03)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x22,        //   Report ID (34)
0x09, 0x04,        //   Usage (0x04)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x22,        //   Report ID (34)
0x09, 0x04,        //   Usage (0x04)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x24,        //   Report ID (36)
0x09, 0x05,        //   Usage (0x05)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x24,        //   Report ID (36)
0x09, 0x05,        //   Usage (0x05)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x26,        //   Report ID (38)
0x09, 0x06,        //   Usage (0x06)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x26,        //   Report ID (38)
0x09, 0x06,        //   Usage (0x06)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x28,        //   Report ID (40)
0x09, 0x07,        //   Usage (0x07)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x28,        //   Report ID (40)
0x09, 0x07,        //   Usage (0x07)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0xF2,        //   Report ID (-14)
0x09, 0x08,        //   Usage (0x08)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0xF2,        //   Report ID (-14)
0x09, 0x08,        //   Usage (0x08)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0xFE,        //   Report ID (-2)
0x09, 0x09,        //   Usage (0x09)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0xFE,        //   Report ID (-2)
0x09, 0x09,        //   Usage (0x09)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0xFA,        //   Report ID (-6)
0x09, 0x0A,        //   Usage (0x0A)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0xFA,        //   Report ID (-6)
0x09, 0x0A,        //   Usage (0x0A)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0xA2,        //   Report ID (-94)
0x09, 0x0B,        //   Usage (0x0B)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0xA2,        //   Report ID (-94)
0x09, 0x0B,        //   Usage (0x0B)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x60,        //   Report ID (96)
0x09, 0x0C,        //   Usage (0x0C)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x60,        //   Report ID (96)
0x09, 0x0C,        //   Usage (0x0C)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x62,        //   Report ID (98)
0x09, 0x0D,        //   Usage (0x0D)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x62,        //   Report ID (98)
0x09, 0x0D,        //   Usage (0x0D)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x66,        //   Report ID (102)
0x09, 0x0E,        //   Usage (0x0E)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x66,        //   Report ID (102)
0x09, 0x0E,        //   Usage (0x0E)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x64,        //   Report ID (100)
0x09, 0x0F,        //   Usage (0x0F)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x64,        //   Report ID (100)
0x09, 0x0F,        //   Usage (0x0F)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x11,        //   Report ID (17)
0x09, 0x10,        //   Usage (0x10)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x13,        //   Report ID (19)
0x09, 0x11,        //   Usage (0x11)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x21,        //   Report ID (33)
0x09, 0x12,        //   Usage (0x12)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x23,        //   Report ID (35)
0x09, 0x13,        //   Usage (0x13)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x25,        //   Report ID (37)
0x09, 0x14,        //   Usage (0x14)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x27,        //   Report ID (39)
0x09, 0x15,        //   Usage (0x15)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x29,        //   Report ID (41)
0x09, 0x16,        //   Usage (0x16)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0xFF,        //   Report ID (-1)
0x09, 0x17,        //   Usage (0x17)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0xFB,        //   Report ID (-5)
0x09, 0x18,        //   Usage (0x18)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0xA3,        //   Report ID (-93)
0x09, 0x19,        //   Usage (0x19)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x61,        //   Report ID (97)
0x09, 0x1A,        //   Usage (0x1A)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x63,        //   Report ID (99)
0x09, 0x1B,        //   Usage (0x1B)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x67,        //   Report ID (103)
0x09, 0x1C,        //   Usage (0x1C)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x65,        //   Report ID (101)
0x09, 0x1D,        //   Usage (0x1D)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0xC0,              // End Collection

// 463 bytes
</code>
</details>

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