The X3 series of NZXT Kraken liquid coolers uses a different protocol than the X2 series.  These X3 coolers use the HID protocol with 64-byte packets.

# Supported Devices

| USB VID | USB PID | Device Name             |
| ------- | ------- | ----------------------- |
| 0x1E71  | 0x2007  | NZXT Kraken X53/X63/X73 |

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