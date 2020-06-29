# Logitech G502

## Basic Info

Captured on a G502 Proteus Spectrum using Logitech GHUB.

VID: 0x046D
PID: 0xC332

## Packet Captures

```txt
DPI off:                          11 ff 02 3c 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
DPI Fixed Red:                    11 ff 02 3c 00 01 ff 00 00 02 00 00 00 00 00 00 00 00 00 00
DPI Fixed Green:                  11 ff 02 3c 00 01 00 ff 00 02 00 00 00 00 00 00 00 00 00 00
DPI Fixed Blue:                   11 ff 02 3c 00 01 00 00 ff 02 00 00 00 00 00 00 00 00 00 00
DPI Cycle Slowest 100 brightness: 11 ff 02 3c 00 03 00 00 00 00 00 4e 20 64 00 00 00 00 00 00
DPI Cycle Fastest 100 brightness: 11 ff 02 3c 00 03 00 00 00 00 00 03 e8 64 00 00 00 00 00 00
DPI Cycle Slowest 1 brightness:   11 ff 02 3c 00 03 00 00 00 00 00 4e 20 01 00 00 00 00 00 00
DPI Cycle Fastest 1 brightness:   11 ff 02 3c 00 03 00 00 00 00 00 03 e8 01 00 00 00 00 00 00
DPI Breathing Red Slowest 100b:   11 ff 02 3c 00 02 ff 00 00 4e 20 00 64 00 00 00 00 00 00 00
DPI Breathing Red Fastest 100b:   11 ff 02 3c 00 02 ff 00 00 03 e8 00 64 00 00 00 00 00 00 00
DPI Breathing Red Fastest 1b:     11 ff 02 3c 00 02 ff 00 00 03 e8 00 01 00 00 00 00 00 00 00

Logo Off:                         11 ff 02 3c 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
Logo Fixed Red:                   11 ff 02 3c 01 01 ff 00 00 02 00 00 00 00 00 00 00 00 00 00
Logo Fixed Green:                 11 ff 02 3c 01 01 00 ff 00 02 00 00 00 00 00 00 00 00 00 00

Direct Red DPI:                   11 ff 02 3a 00 01 ff 00 00 02 00 00 00 00 00 00 00 00 00 00
Direct Red Logo:                  11 ff 02 3a 01 01 ff 00 00 02 00 00 00 00 00 00 00 00 00 00
Direct Green DPI:                 11 ff 02 3a 00 01 00 ff 00 02 00 00 00 00 00 00 00 00 00 00
Direct Green Logo:                11 ff 02 3a 01 01 00 ff 00 02 00 00 00 00 00 00 00 00 00 00
```

## Packet Structure

### Basic Stucture

Modes:
Off: 0x00
Static: 0x01
Breathing: 0x02
Cycle: 0x03

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 11          |
| 0x01       | ff          |
| 0x02       | 02          |
| 0x03       | 3c          |
| 0x04       | Led         |
| 0x05       | Mode        |
| 0x06       | Red         |
| 0x07       | Green       |
| 0x08       | Blue        |
| 0x09       |             |
| 0x0A       |             |
| 0x0B       |             |
| 0x0C       |             |
| 0x0D       |             |
| 0x0E       |             |
| 0x0F       |             |
| 0x10       |             |
| 0x11       |             |
| 0x12       |             |
| 0x13       |             |

### Breathing

Slowest speed: 4e 20

Fastest speed: 03 e8

Highest Brightness: 64

Lowest Brightness: 1 (0?)

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 11          |
| 0x01       | ff          |
| 0x02       | 02          |
| 0x03       | 3c          |
| 0x04       | Led         |
| 0x05       | 02          |
| 0x06       | Red         |
| 0x07       | Green       |
| 0x08       | Blue        |
| 0x09       | Speed       |
| 0x0A       | Speed       |
| 0x0B       | 00          |
| 0x0C       | Brightness  |
| 0x0D       | 00          |
| 0x0E       | 00          |
| 0x0F       | 00          |
| 0x10       | 00          |
| 0x11       | 00          |
| 0x12       | 00          |
| 0x13       | 00          |

### Direct

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 11          |
| 0x01       | ff          |
| 0x02       | 02          |
| 0x03       | 3a          |
| 0x04       | Led         |
| 0x05       | 01          |
| 0x06       | Red         |
| 0x07       | Green       |
| 0x08       | Blue        |
| 0x09       | 00          |
| 0x0A       | 02          |
| 0x0B       | 00          |
| 0x0C       | 00          |
| 0x0D       | 00          |
| 0x0E       | 00          |
| 0x0F       | 00          |
| 0x10       | 00          |
| 0x11       | 00          |
| 0x12       | 00          |
| 0x13       | 00          |