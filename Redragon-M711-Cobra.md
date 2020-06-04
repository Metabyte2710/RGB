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

# Known Addresses

Addresses without description have been seen in captures but don't know what they hold.

| Address | Size | Description                            |
| ------- | ---- | -------------------------------------- |
| 0x002C  | 2    | Active Profile                         |
| 0x0032  | 6    | Polling Rate (2 bytes), 2 other values |
| 0x003E  | 2    |                                        |
| 0x0446  | 2    |                                        |
| 0x0449  | 6    | Lighting Control                       |
| 0x044F  | 1    |                |
| 0x0451  | 6    |                |
| 0x0457  | 1    |                |
| 0x0459  | 6    |                |
| 0x045F  | 1    |                |
| 0x0461  | 6    |                |
| 0x0471  | 1    |                |
| 0x0469  | 6    |                |
| 0x046F  | 1    |                |

## Polling Rate

| Value | Rate   |
| ----- | ------ |
| 0x01  | 1000Hz |
| 0x02  | 500Hz  |
| 0x04  | 250Hz  |
| 0x08  | 125Hz  |

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