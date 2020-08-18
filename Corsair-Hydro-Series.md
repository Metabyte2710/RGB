Corsair Hydro Series is a line of all-in-one water cooling devices sold by Corsair.  It appears that these devices are manufactured by Asetek and use an Asetek protocol.  They are not USB HID devices, having no HID descriptors.  This means that they cannot be accessed using hidapi and must instead be accessed using libusb.

# Supported Devices

| USB VID | USB PID | Device Name           |
| ------- | ------- | --------------------- |
| 0x1B1C  | 0x0C15  | Corsair H100i PRO RGB |

# Protocol

The protocol uses USB bulk transfers.

## Firmware Request

Request size: 1 byte

| Byte Index | Value |
| ---------- | ----- |
| 0x00       | 0xAA  |

Response size: 7 bytes

| Byte Index | Value |
| ---------- | ----- |
| 0x00       |       |
| 0x01       |       |
| 0x02       |       |
| 0x03       | W     |
| 0x04       | X     |
| 0x05       | Y     |
| 0x06       | Z     |

Firmware string should be formatted as W.X.Y.Z