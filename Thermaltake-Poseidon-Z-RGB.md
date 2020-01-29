The Thermaltake Poseidon Z RGB keyboard connects via USB at 264A:3006.  It uses the HID protocol.  Packets are 264 bytes long.

Early reverse engineering can be seen in this document: [Poseidon.Z.RGB.Reverse.Engineering.xlsx](uploads/24f17a890da664d0eda7e32eab2e73a8/Poseidon.Z.RGB.Reverse.Engineering.xlsx)

# Control Packet (0x02)

| Byte Index | Description                             |
| ---------- | --------------------------------------- |
| 0x00       | 0x07                                    |
| 0x01       | 0x02                                    |
| 0x02       | 0x01                                    |
| 0x03       | 0x00                                    |
| 0x04       | 0x00                                    |
| 0x05       | 0x00                                    |
| 0x06       | 0x00                                    |
| 0x07       | 0x00                                    |
| 0x08       | Profile to activate                     |
| 0x09       | 0x00                                    |
| 0x0A       | Direction (0: From Left, 1: From Right) |
| 0x0B       | 0x00                                    |
| 0x0C       | Mode                                    |
| 0x0D       | Brightness (0-4)                        |
| 0x0E       | 0x00                                    |
| 0x0F       | 0x00                                    |
| 0x10       | 0x08                                    |
| 0x11       | 0x00                                    |
| 0x12       | 0x05                                    |
| 0x13       | 0x50                                    |

## Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x00       | Static           |
| 0x01       | Reactive         |
| 0x02       | Arrow Flow       |
| 0x03       | Wave             |
| 0x04       | Ripple           |