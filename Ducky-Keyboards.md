Ducky keyboard protocol information taken from Aurora code: https://github.com/antonpup/Aurora/blob/master/Project-Aurora/Project-Aurora/Devices/Ducky/DuckyDevice.cs

# Supported Devices

| USB VID | USB PID | Device Name                    |
| ------- | ------- | ------------------------------ |
| 0x04D9  | 0x0348  | Ducky Shine 7, Ducky One 2 RGB |
| 0x04D9  | 0x0356  | Ducky One 2 RGB TKL            |

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
| 0x08       | 0x08        |
| 0x09       | 0x00        |
| 0x0A       | 0x00        |
| 0x0B       | 0x00        |
| 0x0C       | 0xAA        |
| 0x0D       | 0xAA        |
| 0x0E       | 0xAA        |
| 0x0F       | 0xAA        |

## Color Packet

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x56        |
| 0x01       | 0x83        |

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