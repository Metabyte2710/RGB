Logitech keyboards use a USB HID interface.  Some packets are 20 bytes, others are 64 bytes.  Unless a packet is denoted as a 64 byte packet below, assume it is a 20 byte packet.  Any bytes not shown are zero.

Information for this wiki page was gathered from: https://github.com/MatMoul/g810-led

# Commit

Logitech G213 and G413 do not need a commit packet.

### Logitech G410, G512, G513, G610, G810, GPro

| Byte Index | Value |
| ---------- | ----- |
| 0x00       | 0x11  |
| 0x01       | 0xFF  |
| 0x02       | 0x0C  |
| 0x03       | 0x5A  |

### Logitech G815

| Byte Index | Value |
| ---------- | ----- |
| 0x00       | 0x11  |
| 0x01       | 0xFF  |
| 0x02       | 0x10  |
| 0x03       | 0x7F  |

### Logitech G910

| Byte Index | Value |
| ---------- | ----- |
| 0x00       | 0x11  |
| 0x01       | 0xFF  |
| 0x02       | 0x0F  |
| 0x03       | 0x5D  |

# Set Startup Mode

### Logitech G213, G410, G610, G810, GPro

| Byte Index | Value        |
| ---------- | ------------ |
| 0x00       | 0x11         |
| 0x01       | 0xFF         |
| 0x02       | 0x0D         |
| 0x03       | 0x5A         |
| 0x04       | 0x00         |
| 0x05       | 0x01         |
| 0x06       | Startup Mode |

### Logitech G910

| Byte Index | Value        |
| ---------- | ------------ |
| 0x00       | 0x11         |
| 0x01       | 0xFF         |
| 0x02       | 0x10         |
| 0x03       | 0x5E         |
| 0x04       | 0x00         |
| 0x05       | 0x01         |
| 0x06       | Startup Mode |

# Set Onboard Mode

### Logitech G815

| Byte Index | Value        |
| ---------- | ------------ |
| 0x00       | 0x11         |
| 0x01       | 0xFF         |
| 0x02       | 0x11         |
| 0x03       | 0x1A         |
| 0x04       | Onboard Mode |

# Set Key Color

### Logitech G810

64-byte packet

| Byte Index | Value                                                 |
| ---------- | ----------------------------------------------------- |
| 0x00       | 0x12                                                  |
| 0x01       | 0xFF                                                  |
| 0x02       | 0x0C                                                  |
| 0x03       | 0x3D                                                  |
| 0x04       | 0x00                                                  |
| 0x05       | 0x01                                                  |
| 0x06       | 0x00                                                  |
| 0x07       | 0x0C                                                  |
| 0x08       | Key Index 1                                           |
| 0x09       | Red 1                                                 |
| 0x0A       | Green 1                                               |
| 0x0B       | Blue 1                                                |
| 0x0C       | Key Index 2                                           |
| 0x0D       | Red 2                                                 |
| 0x0E       | Green 2                                               |
| 0x0F       | Blue 2                                                |

### Logitech G815

| Byte Index | Value                                                 |
| ---------- | ----------------------------------------------------- |
| 0x00       | 0x11                                                  |
| 0x01       | 0xFF                                                  |
| 0x02       | 0x10                                                  |
| 0x03       | 0x6C                                                  |
| 0x04       | Red                                                   |
| 0x05       | Green                                                 |
| 0x06       | Blue                                                  |
| 0x07+      | Key Index (up to 13 keys can be specified per packet) |

