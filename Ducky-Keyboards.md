Ducky keyboard protocol information taken from Aurora code: https://github.com/antonpup/Aurora/blob/master/Project-Aurora/Project-Aurora/Devices/Ducky/DuckyDevice.cs

# Supported Devices

| USB VID | USB PID | Device Name                    |
| ------- | ------- | ------------------------------ |
| 0x04D9  | 0x0348  | Ducky Shine 7, Ducky One 2 RGB |
| 0x04D9  | 0x0356  | Ducky One 2 RGB TKL            |

# Starting Packet

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

# Color Change Packet

        public static byte[] DuckyInitColourBytes => new byte[] { 0x01, 0x00, 0x00, 0x00, 0x80, 0x01, 0x00, 0xC1, 0x00, 0x00, 0x00, 0x00, 0xFF, 0xFF, 0xFF, 0xFF };
        public static byte[] DuckyTerminateColourBytes => new byte[] { 0x51, 0x28, 0x00, 0x00, 0xFF };

There are 8 packets in a color change sequence.

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x56        |
| 0x01       | 0x83        |
| 0x02       | Packet ID   |
| 0x03       |             |
