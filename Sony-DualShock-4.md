Sony's Dualshock 4 controller features a light bar whose color can be changed sending reports with ID 0x11 or 0x05 (Bluetooth and USB, respectively). In order to detect if the controller is connected via Bluetooth or USB, the driver requests calibration data (request 0x02), which on Bluetooth sets the device to send reports with ID 0x11 instead of ID 0x01 (which is used by USB reports). 

## USB Mode

| Pos  | Value | Description                                                  |
| ---- | ----- | ------------------------------------------------------------ |
| 0    | 0x05  | Report ID                                                    |
| 1    | 0x07  | The last three bits enable blinking, the lightbar and rumble |
| 2    | 0x00  | -                                                            |
| 3    | 0x00  | -                                                            |
| 4    | 0x00  | Rumble (strong)                                              |
| 5    | 0x00  | Rumble (weak)                                                |
| 6    | Red   | Red value for the lightbar                                   |
| 7    | Green | Green value for the lightbar                                 |
| 8    | Blue  | Blue value for the lightbar                                  |
| 9    | 0x00  | Led blinking delay (on)                                      |
| 10   | 0x00  | Led blinking delay (off)                                     |

## Bluetooth mode

|         | Value | Description                                                  |
| ------- | ----- | ------------------------------------------------------------ |
| 0       | 0x11  | Report ID                                                    |
| 1       | 0xC0  | The first two bits control HID + CRC while the last 6 bits control BT polling rate |
| 2       | 0x00  | -                                                            |
| 3       | 0x07  | The last three bits enable blinking, the lightbar and rumble |
| 4       | 0x00  | -                                                            |
| 5       | 0x00  | -                                                            |
| 6       | 0x00  | Rumble (strong)                                              |
| 7       | 0x00  | Rumble (weak)                                                |
| 8       | Red   | Red value for the lightbar                                   |
| 9       | Green | Green value for the lightbar                                 |
| 10      | Blue  | Blue value for the lightbar                                  |
| 11      | 0x00  | Led blinking delay (on)                                      |
| 12      | 0x00  | Led blinking delay (off)                                     |
| 13 - 73 | 0x00  | -                                                            |
| 74      | CRC32 | First byte of the CRC32 checksum                             |
| 75      | CRC32 | Second byte of the CRC32 checksum                            |
| 76      | CRC32 | Third byte of the CRC32 checksum                             |
| 77      | CRC32 | Last byte of the CRC32 checksum                              |

Please note that the CRC32 checksum has to be calculated with the transaction type + report type byte (0xa2) at the beginning, but it has to be removed to be used with the hidapi library, as it is already added.

