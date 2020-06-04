Logitech keyboards use a USB HID interface with 20-byte packets.  Any bytes not shown are zero.

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
