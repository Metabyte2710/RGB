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

# Modes

The effects all have very strange names.  I'm pretty sure the people who wrote the app didn't speak very good English and used some form of translator and/or autocorrect to come up with some of these atrocities.

| Effect name            | Value | Description                                         |
| ---------------------- | ----- | --------------------------------------------------- |
| Go with the stream     | 0x01  | Rainbow Wave                                        |
| Clouds fly             | 0x02  | Rainbow Wave, but stretched out                     |
| Winding paths          | 0x03  | Color Wheel                                         |
| The trial of light     | 0x04  | Spectrum Cycle                                      |
| Breathing              | 0x05  | Breathing (at least they got this right)            |
| Normally on            | 0x06  | Static                                              |
| Pass without trace     | 0x07  | Reactive (single key lights when pressed)           |
| Ripple graff           | 0x08  | Reactive with ripple from pressed key               |
| Fast run without trace | 0x09  | Reactive with ripple only on key's row              |
| Swift action           | 0x0A  | I think Razer calls this Starlight                  |
| Flowers blooming       | 0x0B  | Spectrum Cycle per key, very colorful               |
| Snow winter jasmine    | 0x0C  | Rainbow Wave, but vertical                          |
| Hurricane              | 0x0D  | Zigzag lines from center of keyboard                |
| Accumulate             | 0x0E  | Colors come in from outer edges and group in middle |
| Digital times          | 0x0F  | A slower version of Swift action (starlight)        |
| Surmount               |       | Seems to fade between hues of selected color        |
| Both ways              | 0x10  | Visor effect that scans back and forth              |
| Fast and the Furious   | 0x12  | Circular rainbow wave that moves to center          |
| Coastal                | 0x14  | Per-key control (did they mean "Custom"?)           |

## Set Mode

| Index | Value | Description       |
| ----- | ----- | ----------------- |
| 0x00  | 0x04  |                   |
| 0x01  | 0xMM  | Mode value + 0x08 |
| 0x02  | 0x00  |                   |
| 0x03  | 0x06  |                   |
| 0x04  | 0x01  |                   |
| 0x05  | 0x00  |                   |
| 0x06  | 0x00  |                   |
| 0x07  | 0x00  |                   |
| 0x08  | 0xMM  | Mode value        |

## Surmount Modes

These modes use a slightly different protocol

Effect "Surmount" - Red         - 04 18 00 06 01 11 00 00 00

Effect "Surmount" - Yellow      - 04 19 00 06 01 11 00 00 01

Effect "Surmount" - Green       - 04 1A 00 06 01 11 00 00 02

Effect "Surmount" - Blue        - 04 1B 00 06 01 11 00 00 03
