Ducky keyboard protocol information taken from Aurora code: https://github.com/antonpup/Aurora/blob/master/Project-Aurora/Project-Aurora/Devices/Ducky/DuckyDevice.cs

# Supported Devices

| USB VID | USB PID | Device Name                    |
| ------- | ------- | ------------------------------ |
| 0x04D9  | 0x0348  | Ducky Shine 7, Ducky One 2 RGB |
| 0x04D9  | 0x0356  | Ducky One 2 RGB TKL            |

# Entering Software Control Mode

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x41        |
| 0x01       | 0x01        |

# Setting Colors

The color update cycle on the Ducky keyboard consists of ten packets.  This packet set consists of one initialize color packet, eight color packets, and one terminate color packet.

## Initialize Color Packet

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x56        |
| 0x01       | 0x81        |
| 0x02       | 0x00        |
| 0x03       | 0x00        |
| 0x04       | 0x01        |
| 0x05       | 0x00        |
| 0x06       | 0x00        |
| 0x07       | 0x00        |
| 0x08       | 0x08 for direct, 0x01 for wave, 0x02 for alpha effect |
| 0x09       | 0x00        |
| 0x0A       | 0x00        |
| 0x0B       | 0x00        |
| 0x0C       | 0xAA        |
| 0x0D       | 0xAA        |
| 0x0E       | 0xAA        |
| 0x0F       | 0xAA        |

## Color Packet

| Byte Index | Description                        |
| ---------- | ---------------------------------- |
| 0x00       | 0x56                               |
| 0x01       | 0x83                               |
| 0x02       | Packet ID (0-7)                    |
| ...        |                                    |
| 0x05-end   | Start of data for non-0 ID packets |
| ...        |                                    |
| 0x19-end   | Start of data for 0 ID packet      |

The first (of eight) color packets has additional fixed values:

| Byte Index | Description |
| ---------- | ----------- |
| 0x04       | 0x01        |
| ...        |             |
| 0x08       | 0x80        |
| 0x09       | 0x01        |
| ...        |             |
| 0x0B       | 0xC1        |
| ...        |             |
| 0x10       | 0xFF        |
| 0x11       | 0xFF        |
| 0x12       | 0xFF        |
| 0x13       | 0xFF        |

## Terminate Color Packet

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x51        |
| 0x01       | 0x28        |
| ...        |             |
| 0x04       | 0xFF        |

# Setting Effects

Setting an effect uses 3 packets - an Initialize, a Color Data, and a Terminate.

| Byte Index | Description     |
| ---------- | --------------- |
| 0x00       | 0x56            |
| 0x01       | 0x83            |
| ...        |                 |
| 0x04       | 0x01            |
| ...        |                 |
| 0x09       | 0x32            |
| ...        |                 |
| 0x0B       | 0xC1            |
| 0x0C       | 0x09            |
| ...        |                 |
| 0x10       | 0xFF            |
| 0x11       | 0xFF            |
| 0x12       | 0xFF            |
| 0x13       | 0xFF            |
| 0x14       | 0x08            |
| ...        |                 |
| 0x16       | 0x0C            |
| ...        |                 |
| 0x1B       | 0x40            |

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x51        |
| 0x01       | 0x28        |
| ...        |             |
| 0x04       | 0xFF        |