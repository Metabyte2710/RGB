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