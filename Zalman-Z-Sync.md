## Packet IDs

| ID   | Packet Description   |
| ---- | -------------------- |
| 0x32 | Direct mode LED data |
| 0x33 | Apply direct mode    |
| 0x34 |                      |
| 0x35 |                      |
| 0x39 |                      |
| 0x3B |                      |

## 0x32: Direct mode LED data

| Byte | Description   |
| ---- | ------------- |
| 0x00 | 0x32          |
| 0x01 | Channel (0-7) |
| 0x02 |               |
| 0x03 |               |
| 0x04 |               |

## 0x33: Apply direct mode

| Byte | Description  |
| ---- | ------------ |
| 0x00 | 0x33         |
| 0x01 | 0xFF         |