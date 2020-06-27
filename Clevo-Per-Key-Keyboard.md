Some Clevo laptops include a keyboard with per-key RGB lighting.  The device enumerates on USB with ID 048D:8910.  It uses HID feature reports that are 7 bytes long.

# Packet Structure

| Byte index | Description  |
| ---------- | ------------ |
| 0x00       | 0xCC         |
| 0x01       | Command ID   |
| 0x02       | Command Data |
| 0x03       |              |
| 0x04       |              |
| 0x05       |              |
| 0x06       |              |

# 0x09: Set Brightness:

Brightness steps from official app: 00, 02, 04, 06, 0A

| Byte index | Description                           |
| ---------- | ------------------------------------- |
| 0x00       | 0xCC                                  |
| 0x01       | 0x09                                  |
| 0x02       | Brightness (0x00 - 0x0A)              |
| 0x03       | 0x00 if brightness ix 0x00, else 0x02 |
| 0x04       | 0x00                                  |
| 0x05       |                                       |
| 0x06       | 0x00 or 0x0A                          |

Set Key Color: [CC 01 <KeyID> <Red> <Green> <Blue> <unknown, sometimes 00 sometimes 6C>]

Last byte possibly some kind of CRC?  Or maybe an apply byte?