## Packet IDs

| ID   | Packet Description   |
| ---- | -------------------- |
| 0x32 | Direct mode LED data |
| 0x33 | Apply direct mode    |
| 0x34 |                      |
| 0x35 | Configure channel    |
| 0x39 |                      |
| 0x3B |                      |

## 0x32: Direct mode LED data

| Byte  | Description                               |
| ----- | ----------------------------------------- |
| 0x00  | 0x32                                      |
| 0x01  | Channel (0-7)                             |
| 0x02  | 0x00                                      |
| 0x03  | 0x18                                      |
| 0x04  | Color Channel (0: Red, 1: Green, 2: Blue) |
| 0x05+ | Color Channel Data                        |

## 0x33: Apply direct mode

| Byte | Description  |
| ---- | ------------ |
| 0x00 | 0x33         |
| 0x01 | 0xFF         |

## 0x35: Configure channel

| Byte | Description   |
| ---- | ------------- |
| 0x00 | 0x35          |
| 0x01 | Channel (0-7) |
| 0x02 | 0x00          |
| 0x03 | LED Count     |
| 0x04 | Mode          |
| 0x05 | 0x01          |
| 0x06 | 0x00          |
| 0x07 | 0x00          |
| 0x08 | 0x00          |
| 0x09 | Color 1       |
| 0x0A | Color 1       |
| 0x0B | Color 1       |
| 0x0C | Color 2       |
| 0x0D | Color 2       |
| 0x0E | Color 2       |
| 0x0F | Color 3       |
| 0x10 | Color 3       |
| 0x11 | Color 3       |

### Modes

| Mode Value | Mode Description | Color 1 | Color 2 | Color 3 |
| ---------- | ---------------- | ------- | ------- | ------- |
| 0x00       | Rainbow Wave     | No      | No      | No      |
| 0x01       | Color Shift      | Yes     | Yes     | No      |
| 0x02       | Color Pulse      | Yes     | Yes     | No      |
| 0x03       | Color Wave       | Yes     | Yes     | No      |
| 0x04       | Static           | Yes     | No      | No      |
| 0x05       | Temperature      | Yes     | Yes     | Yes     |
| 0x06       | Visor            | Yes     | Yes     | No      |
| 0x07       | Marquee          | Yes     | No      | No      |
| 0x08       | Blink            | Yes     | Yes     | No      |
| 0x09       | Sequential       | Yes     | No      | No      |
| 0x0A       | Rainbow          | No      | No      | No      |