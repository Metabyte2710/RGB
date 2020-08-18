Corsair Hydro Series is a line of all-in-one water cooling devices sold by Corsair.  It appears that these devices are manufactured by Asetek and use an Asetek protocol.  They are not USB HID devices, having no HID descriptors.  This means that they cannot be accessed using hidapi and must instead be accessed using libusb.

# Supported Devices

| USB VID | USB PID | Device Name           |
| ------- | ------- | --------------------- |
| 0x1B1C  | 0x0C15  | Corsair H100i PRO RGB |
| 0x1B1C  | 0x0C13  | Corsair H115i PRO RGB |

# Protocol

The protocol uses USB bulk transfers, but before any bulk operations can be performed it must be initialized using a control transfer.

## Initialization

```
    libusb_control_transfer( dev, 0x40, 0x00, 0xffff, 0x0000, NULL, 0, 0 );
    libusb_control_transfer( dev, 0x40, 0x02, 0x0002, 0x0000, NULL, 0, 0 );
```

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

## RGB Control - Set Rainbow Mode

Request size: 2 bytes

| Byte Index | Value        |
| ---------- | ------------ |
| 0x00       | 0x53         |
| 0x01       | Effect Speed |

Effect speeds

| Value | Description |
| ----- | ----------- |
| 0x30  | Slow        |
| 0x18  | Medium      |
| 0x0C  | Fast        |

Response size: 3 bytes

## RGB Control - Set Shift Mode

## RGB Control - Set Pulse Mode

## RGB Control - Set Blinking Mode

## RGB Control - Set Fixed Mode

Request size: 2 + (3 * [Color count])

| Byte Index | Value        |
| ---------- | ------------ |
| 0x00       | 0x56         |
| 0x01       | Color count  |
| 0x02       | Red          |
| 0x03       | Green        |
| 0x04       | Blue         |

Response size: 3 bytes