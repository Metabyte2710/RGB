Sapphire has three different versions of their Nitro Glow RGB system.  The first generation of Nitro Glow uses a single-zone I2C controller that enumerates at address 0x55.

# Supported Devices

    * Sapphire RX 580 Nitro+

# Registers

| Register Address | Register Description               |
| ---------------- | ---------------------------------- |
| 0x00             | Mode (see Modes)                   |
| 0x01             | Brightness (see Brightness Values) |
| 0x03             | Red                                |
| 0x04             | Green                              |
| 0x05             | Blue                               |

# Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x00       | Sapphire Blue    |
| 0x01       | Rainbow          |
| 0x02       | PCB Temperature  |
| 0x03       | Fan Speed        |
| 0x04       | Custom           |
| 0x05       | Off              |

# Brightness Values

| Value | Brightness |
| ----- | ---------- |
| 0x00  | 100%       |
| 0x01  | 75%        |
| 0x02  | 50%        |