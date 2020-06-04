USB protocol, 16 byte USB HID control packets with report ID 0.

02 F3 46 04 02 - Start?

# Packet Structure

| Index | Value | Description              |
| ----- | ----- | ------------------------ |
| 0x00  | 0x02  |                          |
| 0x01  | 0xF3  |                          |
| 0x02  | 0x49  | Start address LSB        |
| 0x03  | 0x04  | Start address MSB        |
| 0x04  | 0xNN  | Number of bytes          |
| 0x05  | 0x00  |                          |
| 0x06  | 0x00  |                          |
| 0x07  | 0x00  |                          |
| 0x08+ | 0xXX  | Start of data            |

# Apply Settings

| Index | Value | Description |
| ----- | ----- | ----------- |
| 0x00  | 0x02  |             |
| 0x01  | 0xF1  |             |
| 0x02  | 0x02  |             |
| 0x03  | 0x04  |             |

# Lighting Control

| Index | Value | Description              |
| ----- | ----- | ------------------------ |
| 0x00  | 0x02  |                          |
| 0x01  | 0xF3  |                          |
| 0x02  | 0x49  |                          |
| 0x03  | 0x04  |                          |
| 0x04  | 0x06  |                          |
| 0x05  | 0x00  |                          |
| 0x06  | 0x00  |                          |
| 0x07  | 0x00  |                          |
| 0x08  | 0xRR  | Red channel              |
| 0x09  | 0xGG  | Green channel            |
| 0x0A  | 0xBB  | Blue channel             |
| 0x0B  | 0xEE  | Off (0x00) / On (0x01 )  |
| 0x0C  | 0xSS  | Speed (See speed values) |
| 0x0D  | 0xMM  | Mode (See mode values)   |
| 0x0E  | 0x00  |                          |
| 0x0F  | 0x00  |                          |

## Speeds

| Speed Setting | Speed value |
| ------------- | ----------- |
| Slow          | 0x08        |
| Medium        | 0x05        |
| Fast          | 0x02        |

## Modes

| Mode value | Mode description |
| ---------- | ---------------- |
| 0x00       | ??? (Wave?)      |
| 0x02       | Static           |
| 0x04       | Breathing        |
| 0x08       | Rainbow          |
| 0x10       | Flashing         |