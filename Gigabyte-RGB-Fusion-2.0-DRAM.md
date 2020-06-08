Gigabyte's Aorus RGB RAM uses an SMBus controller with address 0x67.  All sticks use the same address and no means of controlling individual sticks is currently known.  The protocol uses a 32-byte data packet written to internal address 0x20 using a block transfer followed by an apply command written to address 0x28 using a byte transfer.

# Data Packet Structure

This 32-byte packet is written to 0x20 using block transfer

| Byte Index | Description        |
| ---------- | ------------------ |
| 0x00       | LED Enable Mask    |
| 0x01       |                    |
| 0x02       |                    |
| 0x03       |                    |
| 0x04       |                    |
| 0x05       |                    |
| 0x06       |                    |
| 0x07       |                    |
| 0x08       |                    |
| 0x09       | Mode               |
| 0x0A       | Brightness (0-100) |
| 0x0B       |                    |
| 0x0C       | Blue               |
| 0x0D       | Green              |
| 0x0E       | Red                |
| 0x0F       |                    |
| 0x10       |                    |
| 0x11       |                    |
| 0x12       |                    |
| 0x13       |                    |
| 0x14       |                    |
| 0x15       |                    |
| 0x16       |                    |
| 0x17       |                    |
| 0x18       |                    |
| 0x19       |                    |
| 0x1A       |                    |
| 0x1B       |                    |
| 0x1C       |                    |
| 0x1D       |                    |
| 0x1E       |                    |
| 0x1F       |                    |

# Apply Command

Write 0x0F to 0x28