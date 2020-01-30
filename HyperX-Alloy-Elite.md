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
| 0x0E       | Key: F12                                  |
| 0x0F       |                                           |
| 0x10       | Key: F9                                   |
| 0x11       | Key: 9                                    |
| 0x12       | Key: O                                    |
| 0x13       | Key: L                                    |
| 0x14       | Key: ,/<                                  |
| 0x15       |                                           |
| 0x16       |                                           |
| 0x17       | Key: Left Arrow                           |
| 0x18       | Key: F1                                   |
| 0x19       | Key: 1                                    |
| 0x1A       | Key: Q                                    |
| 0x1B       | Key: A                                    |
| 0x1C       |                                           |
| 0x1D       | Key: Left Windows                         |
| 0x1E       |                                           |
| 0x1F       |                                           |
| 0x20       | Key: F10                                  |
| 0x21       | Key: 0                                    |
| 0x22       | Key: P                                    |
| 0x23       | Key: ;/:                                  |
| 0x24       | Key: ./>                                  |
| 0x25       |                                           |
| 0x26       |                                           |
| 0x27       |                                           |
| 0x28       | Key: F2                                   |
| 0x29       | Key: 2                                    |
| 0x2A       | Key: W                                    |
| 0x2B       | Key: S                                    |
| 0x2C       | Key: Z                                    |
| 0x2D       | Key: Left Alt                             |
| 0x2E       |                                           |
| 0x2F       | Key: Backspace                            |
| 0x30       | Key: F11                                  |
| 0x31       | Key: -/_                                  |
| 0x32       | Key: [/{                                  |
| 0x33       | Key: '/"                                  |
| 0x34       | Key: //?                                  |
| 0x35       |                                           |
| 0x36       |                                           |
| 0x37       |                                           |
| 0x38       | Key: F3                                   |
| 0x39       | Key: 3                                    |
| 0x3A       | Key: E                                    |
| 0x3B       | Key: D                                    |
| 0x3C       | Key: X                                    |
| 0x3D       |                                           |
| 0x3E       |                                           |
| 0x3F       |                                           |
| 0x40       |                                           |
| 0x41       |                                           |
| 0x42       |                                           |
| 0x43       |                                           |
| 0x44       |                                           |
| 0x45       |                                           |
| 0x46       |                                           |
| 0x47       |                                           |
| 0x48       | Key: F4                                   |
| 0x49       | Key: 4                                    |
| 0x4A       | Key: R                                    |
| 0x4B       | Key: F                                    |
| 0x4C       | Key: C                                    |
| 0x4D       | Key: Space                                |
| 0x4E       |                                           |
| 0x4F       |                                           |
| 0x50       |                                           |
| 0x51       |                                           |
| 0x52       |                                           |
| 0x53       |                                           |
| 0x54       |                                           |
| 0x55       |                                           |
| 0x56       |                                           |
| 0x57       |                                           |
| 0x58       | Key: F5                                   |
| 0x59       | Key: 5                                    |
| 0x5A       | Key: T                                    |
| 0x5B       | Key: G                                    |
| 0x5C       | Key: V                                    |
| 0x5D       |                                           |
| 0x5E       |                                           |
| 0x5F       |                                           |
| 0x60       |                                           |
| 0x61       |                                           |
| 0x62       |                                           |
| 0x63       |                                           |
| 0x64       |                                           |
| 0x65       |                                           |
| 0x66       |                                           |
| 0x67       |                                           |
| 0x68       | Key: F6                                   |
| 0x69       | Key: 6                                    |
| 0x6A       | Key: Y                                    |
| 0x6B       | Key: H                                    |
| 0x6C       | Key: B                                    |
| 0x6D       |                                           |
| 0x6E       |                                           |
| 0x6F       |                                           |
| 0x70       |                                           |
| 0x71       |                                           |
| 0x72       |                                           |
| 0x73       |                                           |
| 0x74       |                                           |
| 0x75       |                                           |
| 0x76       |                                           |
| 0x77       |                                           |
| 0x78       | Key: F7                                   |
| 0x79       | Key: 7                                    |
| 0x7A       | Key: U                                    |
| 0x7B       | Key: J                                    |
| 0x7C       | Key: N                                    |
| 0x7D       | Key: Right Alt                            |
| 0x7E       | Key: ]/}                                  |
| 0x7F       |                                           |
| 0x80       |                                           |
| 0x81       |                                           |
| 0x82       |                                           |
| 0x83       |                                           |
| 0x84       |                                           |
| 0x85       |                                           |
| 0x86       |                                           |
| 0x87       |                                           |
| 0x88       | Key: F8                                   |
| 0x89       | Key: 8                                    |
| 0x8A       | Key: I                                    |
| 0x8B       | Key: K                                    |
| 0x8C       | Key: M                                    |
| 0x8D       |                                           |
| 0x8E       | Key: \\/\|                                 |
| 0x8F       |                                           |
