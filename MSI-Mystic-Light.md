MSI Mystic Light is a marketing name for a line of motherboards with lighting controllers from MSI.  These boards use a USB controller with VID 1462.

# Request Firmware Version (APROM)

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x01        |
| 0x01       | 0xB0        |
| 0x02-0x61  | 0xCC        |

## Response

| Byte Index | Description      |
| ---------- | ---------------- |
| 0x00       |                  |
| 0x01       |                  |
| 0x02       | Firmware Version |

Firmware version high value is most significant 4 bits, low value is least significant 4 bits.  Display as \<high value\>.\<low value\>.

# Request Firmware Version (LDROM)

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x01        |
| 0x01       | 0xB6        |
| 0x02-0x61  | 0xCC        |

## Response

| Byte Index | Description      |
| ---------- | ---------------- |
| 0x00       |                  |
| 0x01       |                  |
| 0x02       | Firmware Version |

Firmware version high value is most significant 4 bits, low value is least significant 4 bits.  Display as \<high value\>.\<low value\>.

# Main Feature Packet

This packet contains data for all the motherboard headers and zones.

| Byte Index | Description                        |
| ---------- | ---------------------------------- |
| 0x00       | Report ID, 0x52                    |
| 0x01-0x0A  | Zone Data for J_RGB_1              |
| 0x0B-0x14  | Zone Data for J_PIPE_1             |
| 0x15-0x1E  | Zone Data for J_PIPE_2             |
| 0x1F-0x29  | Rainbow Zone Data for J_RAINBOW_1  |
| 0x2A-0x34  | Rainbow Zone Data for J_RAINBOW_2  |
| 0x35-0x3F  | Corsair Zone Data for J_CORSAIR    |
| 0x40-0x49  | Zone Data for J_CORSAIR_OUTERLL120 |
| 0x4A-0x53  | Zone Data for On-Board LED 0       |
| 0x54-0x5D  | Zone Data for On-Board LED 1       |
| 0x5E-0x67  | Zone Data for On-Board LED 2       |
| 0x68-0x71  | Zone Data for On-Board LED 3       |
| 0x72-0x7B  | Zone Data for On-Board LED 4       |
| 0x7C-0x85  | Zone Data for On-Board LED 5       |
| 0x86-0x8F  | Zone Data for On-Board LED 6       |
| 0x90-0x99  | Zone Data for On-Board LED 7       |
| 0x9A-0xA3  | Zone Data for On-Board LED 8       |
| 0xA4-0xAD  | Zone Data for On-Board LED 9       |
| 0xAE-0xB7  | Zone Data for J_RGB_2              |
| 0xB8       | Save Data Flag                     |

## Zone Data

This sub-packet represents the configuration for a single zone

| Byte Index | Description            |
| ---------- | ---------------------- |
| 0x00       | Effect Mode            |
| 0x01       | Red 1                  |
| 0x02       | Green 1                |
| 0x03       | Blue 1                 |
| 0x04       | Speed/Brightness Flags |
| 0x05       | Red 2                  |
| 0x06       | Green 2                |
| 0x07       | Blue 2                 |
| 0x08       | Color Flags            |
| 0x09       | Padding (0x00)         |

## Rainbow Zone Data

This sub-packet represents a rainbow zone.  It has all of the members of the Zone Data and adds an extra member for the LED count.

| Byte Index | Description      |
| ---------- | ---------------- |
| 0x00-0x09  | Zone Data        |
| 0x0A       | Cycle/LED Number |

## Corsair Zone Data

This sub-packet represents a Corsair zone

| Byte Index | Description      |
| ---------- | ---------------- |
| 0x00       | Effect Mode      |
| 0x01       | Red              |
| 0x02       | Green            |
| 0x03       | Blue             |
| 0x04       | Fan Flags        |
| 0x05       | Corsair Quantity |
| 0x06       | Padding (0x00)   |
| 0x07       | Padding (0x00)   |
| 0x08       | Padding (0x00)   |
| 0x09       | Is Individual?   |






MSI Mystic Light enabled motherboards (MSI MEG X570 described here) use a USB HID based controller that enumerates at 1462:7c35.  The protocol uses set reports with length of 265 bytes each.

Set blue packet:

```
0000   
0010   
0020               52 01 00 00 ff 28 00 00 ff 80 00 01
0030   00 00 ff 28 00 00 ff 80 00 00 00 00 00 00 00 00
0040   00 00 00 01 00 00 ff 28 00 00 ff 80 00 14 01 00
0050   00 ff 28 00 00 ff 80 00 14 01 00 00 ff 28 00 00
0060   ff 82 4c 0a 01 ff 00 00 28 00 00 00 80 00 00 00
0070   00 00 28 00 00 00 81 00 00 00 00 00 00 00 00 00
0080   00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
0090   00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00a0   00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00b0   00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00c0   00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00d0   00 00 00 00 00 00 00 00 00 00 00 00 00
```

Breaking it down:

```
52
01 00 00 ff 28 00 00 ff 80 00
01 00 00 ff 28 00 00 ff 80 00
00 00 00 00 00 00 00 00 00 00
01 00 00 ff 28 00 00 ff 80 00 14
01 00 00 ff 28 00 00 ff 80 00 14
01 00 00 ff 28 00 00 ff 82 4c 0a
01 ff 00 00 28 00 00 00 80 00
00 00 00 00 28 00 00 00 81 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00
```