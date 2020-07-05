The NZXT Kraken series of AIO liquid cooling devices support RGB lighting as well as pump and fan control.  The NZXT Kraken controller uses the USB HID protocol with 65 byte writes and 64 byte reads.

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
0x85, 0x70,        //   Report ID (112)
0x09, 0x0A,        //   Usage (0x0A)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x70,        //   Report ID (112)
0x09, 0x0A,        //   Usage (0x0A)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x72,        //   Report ID (114)
0x09, 0x0B,        //   Usage (0x0B)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x72,        //   Report ID (114)
0x09, 0x0B,        //   Usage (0x0B)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x73,        //   Report ID (115)
0x09, 0x0C,        //   Usage (0x0C)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x73,        //   Report ID (115)
0x09, 0x0C,        //   Usage (0x0C)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x74,        //   Report ID (116)
0x09, 0x0D,        //   Usage (0x0D)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x74,        //   Report ID (116)
0x09, 0x0D,        //   Usage (0x0D)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x2A,        //   Report ID (42)
0x09, 0x0E,        //   Usage (0x0E)
0x15, 0x00,        //   Logical Minimum (0)
0x26, 0xFF, 0x00,  //   Logical Maximum (255)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0xB1, 0x82,        //   Feature (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x2A,        //   Report ID (42)
0x09, 0x0E,        //   Usage (0x0E)
0x91, 0x82,        //   Output (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position,Volatile)
0x85, 0x11,        //   Report ID (17)
0x09, 0x0F,        //   Usage (0x0F)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x13,        //   Report ID (19)
0x09, 0x10,        //   Usage (0x10)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0xFF,        //   Report ID (-1)
0x09, 0x11,        //   Usage (0x11)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x71,        //   Report ID (113)
0x09, 0x12,        //   Usage (0x12)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x75,        //   Report ID (117)
0x09, 0x13,        //   Usage (0x13)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x21,        //   Report ID (33)
0x09, 0x14,        //   Usage (0x14)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x23,        //   Report ID (35)
0x09, 0x15,        //   Usage (0x15)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x25,        //   Report ID (37)
0x09, 0x16,        //   Usage (0x16)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x27,        //   Report ID (39)
0x09, 0x17,        //   Usage (0x17)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x29,        //   Report ID (41)
0x09, 0x18,        //   Usage (0x18)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0x85, 0x2B,        //   Report ID (43)
0x09, 0x19,        //   Usage (0x19)
0x75, 0x08,        //   Report Size (8)
0x95, 0x3F,        //   Report Count (63)
0x81, 0x82,        //   Input (Data,Var,Abs,No Wrap,Linear,Preferred State,No Null Position)
0xC0,              // End Collection
 
// 412 bytes
</code>
</details>

# Supported Devices

| Device                      | USB ID    |
| --------------------------- | --------- |
| NZXT Kraken X42/X52/X62/X72 | 1E71:170E |

# Send Effect

| Byte Index | Description                  |
| ---------- | ---------------------------- |
| 0x00       | 0x02                         |
| 0x01       | 0x4C                         |
| 0x02       | Channel, Movement, Direction |
| 0x03       | Mode                         |
| 0x04       | Speed, Size, Color In Set    |
| 0x05       | Color Data (9x R/G/B)        |

# Status Update

Perform an HID read to get this packet

To get liquid temperature, (pkt[0x01] + (0.1 * pkt[0x2]))

Firmware string is \<Major\>.\<Minor\>.\<Patch\>

| Byte Index | Description             |
| ---------- | ----------------------- |
| 0x00       |                         |
| 0x01       | Liquid Temperature x1   |
| 0x02       | Liquid Temperature x0.1 |
| 0x03       | Fan Speed MSB           |
| 0x04       | Fan Speed LSB           |
| 0x05       | Pump Speed MSB          |
| 0x06       | Pump Speed LSB          |
| 0x07       |                         |
| 0x08       |                         |
| 0x09       |                         |
| 0x0A       |                         |
| 0x0B       | Firmware Major          |
| 0x0C       | Firmware Minor MSB      |
| 0x0D       | Firmware Minor LSB      |
| 0x0E       | Firmware Patch          |