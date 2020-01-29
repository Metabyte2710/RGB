The HyperX Alloy Elite keyboard enumerates on USB at 0951:16BE and has three interfaces.  The keyboard uses HID packets that are 264 bytes long.  The protocol looks similar to the Poseidon Z RGB though not identical.

# Color packet

| Byte Index | Description                               |
| ---------- | ----------------------------------------- |
| 0x00       | 0x07                                      |
| 0x01       | 0x06                                      |
| 0x02       | Profile to edit                           |
| 0x03       | Color channel (1: Red, 2: Green, 3: Blue) |
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
| 0x0E       | Key:                                      |
| 0x0F       |                                           |
| 0x10       |                                           |
| 0x11       |                                           |
| 0x12       |                                           |
| 0x13       |                                           |
| 0x14       |                                           |
| 0x15       |                                           |
| 0x16       |                                           |
| 0x17       | Key: Left Arrow                           |
| 0x18       | Key: F1                                   |
| 0x19       | Key: 1                                    |