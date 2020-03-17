USB HID, 64-byte packets

# Begin Command Set

| Index | Value |
| ----- | ----- |
| 0x00  | 0x04  |
| 0x01  | 0x01  |
| 0x02  | 0x00  |
| 0x03  | 0x01  |

# End Command Set

| Index | Value |
| ----- | ----- |
| 0x00  | 0x04  |
| 0x01  | 0x02  |
| 0x02  | 0x00  |
| 0x03  | 0x02  |

Custom data: 04 0F 03 06 03 09 00 00 FF FF FF

The 03 bytes seem to indicate number of color bytes

The 09 seems to be the offset in bytes - start at 00

| Index | Value | Description        |
| ----- | ----- | ------------------ |
| 0x00  | 0x04  |                    |
| 0x01  | 0x11  | Byte offset + 0x11 |
| 0x02  | 0x36  | Number of bytes    |
| 0x03  | 0x11  |                    |
| 0x04  | 0x36  | Number of bytes    |
| 0x05  | 0x00  | Byte offset LSB    |
| 0x06  | 0x00  | Byte offset MSB    |
| 0x07  | 0x00  |                    |
| 0x08+ | 0xXX  | RGB data           |

Polling rate 125Hz - 04 16 00 06 01 0f 00 00 00

Polling rate 250Hz - 04 17 00 06 01 0f 00 00 01

Polling rate 500Hz - 04 18 00 06 01 0f 00 00 02

Polling rate 1000Hz - 04 19 00 06 01 0f 00 00 03

The effects all have very strange names.  I'm pretty sure the people who wrote the app didn't speak very good English and used some form of translator and/or autocorrect to come up with some of these atrocities.

| Effect name            | Description                                         |
| ---------------------- | --------------------------------------------------- |
| Go with the stream     | Rainbow Wave                                        |
| Clouds fly             | Rainbow Wave, but stretched out                     |
| Winding paths          | Color Wheel                                         |
| The trial of light     | Spectrum Cycle                                      |
| Breathing              | Breathing (at least they got this right)            |
| Normally on            | Static                                              |
| Pass without trace     | Reactive (single key lights when pressed)           |
| Ripple graff           | Reactive with ripple from pressed key               |
| Fast run without trace | Reactive with ripple only on key's row              |
| Swift action           | I think Razer calls this Starlight                  |
| Flowers blooming       | Spectrum Cycle per key, very colorful               |
| Snow winter jasmine    | Rainbow Wave, but vertical                          |
| Hurricane              | Zigzag lines from center of keyboard                |
| Accumulate             | Colors come in from outer edges and group in middle |
| Digital times          | A slower version of Swift action (starlight)        |
| Surmount               | Seems to fade between hues of selected color        |
| Both ways              | Visor effect that scans back and forth              |
| Fast and the Furious   | Circular rainbow wave that moves to center          |
| Coastal                | Per-key control (did they mean "Custom"?)           |

Effect "Go with the stream"     - 04 08 00 06 01 00 00 00 01

Effect "Clouds fly"             - 04 09 00 06 01 00 00 00 02

Effect "Winding paths"          - 04 0A 00 06 01 00 00 00 03

Effect "The trial of light"     - 04 0B 00 06 01 00 00 00 04

Effect "Breathing"              - 04 0C 00 06 01 00 00 00 05

Effect "Normally on"            - 04 0D 00 06 01 00 00 00 06

Effect "Pass without trace"     - 04 0E 00 06 01 00 00 00 07

Effect "Ripple graff"           - 04 0F 00 06 01 00 00 00 08

Effect "Fast run without trace" - 04 10 00 06 01 00 00 00 09

Effect "Swift action"           - 04 11 00 06 01 00 00 00 0A

Effect "Flowers blooming"       - 04 12 00 06 01 00 00 00 0B

Effect "Snow winter jasmine"    - 04 13 00 06 01 00 00 00 0C

Effect "Hurricane"              - 04 14 00 06 01 00 00 00 0D

Effect "Accumulate"             - 04 15 00 06 01 00 00 00 0E

Effect "Digital times"          - 04 16 00 06 01 00 00 00 0F

Effect "Both ways"              - 04 17 00 06 01 00 00 00 10

Effect "Fast and the furious"   - 04 19 00 06 01 00 00 00 12

Effect "Surmount" - Red         - 04 18 00 06 01 11 00 00 00

Effect "Surmount" - Yellow      - 04 19 00 06 01 11 00 00 01

Effect "Surmount" - Green       - 04 1A 00 06 01 11 00 00 02

Effect "Surmount" - Blue        - 04 1B 00 06 01 11 00 00 03

Effect "Coastal"                - 04 1B 00 06 01 00 00 00 14

