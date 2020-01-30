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
| 0x08       | Key: Escape                               |
| 0x09       | Key: `/~                                  |
| 0x0A       | Key: Tab                                  |
| 0x0B       | Key: Caps Lock                            |
| 0x0C       | Key: Left Shift                           |
| 0x0D       | Key: Left Control                         |
| 0x0E       | Key: Left Arrow                           |
| 0x0F       | Key: Insert                               |
| 0x10       | Key: F1                                   |
| 0x11       | Key: 1                                    |
| 0x12       | Key: Q                                    |
| 0x13       | Key: A                                    |
| 0x14       | Red: 0xFF, Green: 0x00, Blue: 0x11        |
| 0x15       | Key: Windows                              |
| 0x16       | Key: Down Arrow                           |
| 0x17       | Key: Delete                               |
| 0x18       | Key: F2                                   |
| 0x19       | Key: 2                                    |
| 0x1A       | Key: W                                    |
| 0x1B       | Key: S                                    |
| 0x1C       | Red: 0xFF, Green: 0x00, Blue: 0x11        |
| 0x1D       | Key: Left Alt                             |
| 0x1E       | Key: Right Arrow                          |
| 0x1F       | Key: Home                                 |
| 0x20       | Key: F3                                   |
| 0x21       | Key: 3                                    |
| 0x22       | Key: E                                    |
| 0x23       | Key: D                                    |
| 0x24       | Key: Z                                    |
| 0x25       | Red: 0xFF, Green: 0x00, Blue: 0x11        |
| 0x26       | Key: Up Arrow                             |
| 0x27       | Key: End                                  |
| 0x28       | Key: F4                                   |
| 0x29       | Key: 4                                    |
| 0x2A       | Key: R                                    |
| 0x2B       | Key: F                                    |
| 0x2C       | Key: X                                    |
| 0x2D       | Key: Space                                |
| 0x2E       | Key: Number Pad 4                         |
| 0x2F       | Key: Page Up                              |
| 0x30       | Key: F5                                   |
| 0x31       | Key: 5                                    |
| 0x32       | Key: T                                    |
| 0x33       | Key: G                                    |
| 0x34       | Key: C                                    |