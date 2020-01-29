The Thermaltake Poseidon Z RGB keyboard connects via USB at 264A:3006.  It uses the HID protocol.  Packets are 264 bytes long.

Early reverse engineering can be seen in this document: [Poseidon.Z.RGB.Reverse.Engineering.xlsx](uploads/24f17a890da664d0eda7e32eab2e73a8/Poseidon.Z.RGB.Reverse.Engineering.xlsx)

# Control Packet (0x02)

| Byte Index | Description                             |
| ---------- | --------------------------------------- |
| 0x00       | 0x07                                    |
| 0x01       | 0x02                                    |
| 0x02       | Profile to activate                     |
| 0x03       | 0x00                                    |
| 0x04       | 0x00                                    |
| 0x05       | 0x00                                    |
| 0x06       | 0x00                                    |
| 0x07       | 0x00                                    |
| 0x08       | Profile to edit (0 if not editing)      |
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

# Color Packet

| Byte Index | Description                               |
| ---------- | ----------------------------------------- |
| 0x00       | 0x07                                      |
| 0x01       | 0x09                                      |
| 0x02       | Profile to edit                           |
| 0x03       | Color channel (0: Red, 1: Green, 2: Blue) |
| 0x04       | 0x00                                      |
| 0x05       | 0x00                                      |
| 0x06       | 0x00                                      |
| 0x07       | 0x00                                      |
| 0x08       | Escape Key                                |
| 0x09       | `/~ Key                                   |
| 0x0A       | Tab Key                                   |
| 0x0B       | Caps Lock Key                             |
| 0x0C       | Left Shift Key                            |
| 0x0D       | Left Control Key                          |
| 0x0E       | Left Arrow Key                            |
| 0x0F       | Insert Key                                |
| 0x10       | F1 Key                                    |
| 0x11       | 1 Key                                     |
| 0x12       | Q Key                                     |
| 0x13       | A Key                                     |
| 0x14       | Red: 0xFF, Green: 0x00, Blue: 0x11        |
| 0x15       | Windows Key                               |
| 0x16       | Down Arrow Key                            |
| 0x17       | Delete Key                                |
| 0x18       | F2 Key                                    |
| 0x19       | 2 Key                                     |
| 0x1A       | W Key                                     |
| 0x1B       | S Key                                     |
| 0x1C       | Red: 0xFF, Green: 0x00, Blue: 0x11        |
| 0x1D       | Left Alt Key                              |
| 0x1E       | Right Arrow Key                           |
| 0x1F       | Home Key                                  |
| 0x20       | F3 Key                                    |
| 0x21       | 3 Key                                     |
| 0x22       | E Key                                     |
| 0x23       | D Key                                     |
| 0x24       | Z Key                                     |
| 0x25       | Red: 0xFF, Green: 0x00, Blue: 0x11        |