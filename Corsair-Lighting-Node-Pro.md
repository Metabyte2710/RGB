The Corsair Lighting Node Pro is an addressable LED strip controller with two channels, each supporting up to 60 LEDs.  It interfaces using USB and enumerates at 1B1C:0C0B.  Packets are 64 bytes long.  The Corsair Commander Pro (1B1C:0C10) shares much of the same functionality but also includes fan control.

The Lighting Node Pro appears to reset itself after 20 seconds of inactivity.  I haven't implemented periodic refreshing in OpenRGB, so when you set the colors it will default back to rainbow after 20 seconds.  To fix this, I'll need to add some sort of keep-alive thread to either send the full color data or find some other packet that keeps it from resetting.

It looks like sending the apply packet every few seconds is enough to keep it from reverting to rainbow mode.

All write packets are 64 bytes long and are zero-filled.  All read packets are 16 bytes.

# Fan Control (0x2x)

## Get Fan RPM (0x21)

Request:

| Byte Index | Description       |
| ---------- | ----------------- |
| 0x00       | 0x21              |
| 0x01       | Fan Channel (0-5) |

Response:

| Byte Index | Description       |
| ---------- | ----------------- |
| 0x00       |                   |
| 0x01       | Fan RPM MSB       |
| 0x02       | Fan RPM LSB       |

## Get Fan Command - Fixed Percent (0x22)

Request:

| Byte Index | Description       |
| ---------- | ----------------- |
| 0x00       | 0x22              |
| 0x01       | Fan Channel (0-5) |

Response:

| Byte Index | Description       |
| ---------- | ----------------- |
| 0x00       |                   |
| 0x01       | Fan Command       |

## Set Fan Command - Fixed Percent (0x23)

| Byte Index | Description         |
| ---------- | ------------------- |
| 0x00       | 0x23                |
| 0x01       | Fan Channel (0-5)   |
| 0x02       | Fan Percent (0-100) |

## Set Fan Command - Fixed RPM (0x24)

| Byte Index | Description         |
| ---------- | ------------------- |
| 0x00       | 0x24                |
| 0x01       | Fan Channel (0-5)   |
| 0x02       | Fan RPM MSB         |
| 0x03       | Fan RPM LSB         |

## Set Fan Configuration (0x28)

| Byte Index | Description       |
| ---------- | ----------------- |
| 0x00       | 0x28              |
| 0x01       | 0x02              |
| 0x02       | Fan Channel (0-5) |
| 0x23       | Fan Configuration |

### Fan Configuration Values

| Value | Description              |
| ----- | ------------------------ |
| 0x00  | Automatic / Disconnected |
| 0x01  | 3-Pin Fan                |
| 0x02  | 4-Pin Fan                |

# RGB Control (0x3x)

## Direct Control (0x32)

| Byte Index | Description                                 |
| ---------- | ------------------------------------------- |
| 0x00       | 0x32                                        |
| 0x01       | Channel (0 or 1)                            |
| 0x02       | Start index                                 |
| 0x03       | Count                                       |
| 0x04       | Color Channel (0: Red, 1: Green, 2: Blue)   |
| 0x05-end   | LED channel values equal to Count           |

## Commit (0x33)

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x33        |
| 0x01       | 0xFF        |

## Begin (0x34)

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x34        |
| 0x01       | Channel     |

## Effect Configuration (0x35)

| Byte Index | Description        |
| ---------- | ------------------ |
| 0x00       | 0x35               |
| 0x01       | Channel (0 or 1)   |
| 0x02       | Device index       |
| 0x03       | Type of device     |
| 0x04       | Effect Mode        |
| 0x05       | Effect Speed       |
| 0x06       | Direction          |
| 0x07       | Fixed/Random Color |
| 0x08       | 0xFF               |
| 0x09       | Color 0 Red        |
| 0x0A       | Color 0 Green      |
| 0x0B       | Color 0 Blue       |
| 0x0C       | Color 1 Red        |
| 0x0D       | Color 1 Green      |
| 0x0E       | Color 1 Blue       |
| 0x0F       | Color 2 Red        |
| 0x10       | Color 2 Green      |
| 0x11       | Color 2 Blue       |
| 0x12       | Temperature 0      |
| 0x13       |                    |
| 0x14       | Temperature 1      |
| 0x15       |                    |
| 0x16       | Temperature 2      |
| 0x17       |                    |

### Device Types

| Device Type Value | Device Type Description |
| ----------------- | ----------------------- |
| 0x0A              | Corsair LED Strip       |
| 0x0C              | Corsair HD-series Fan   |
| 0x01              | Corsair SP-series Fan   |
| 0x02              | Corsair ML-series Fan   |

### Effect Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x00       | Rainbow Wave     |
| 0x01       | Color Shift      |
| 0x02       | Color Pulse      |
| 0x03       | Color Wave       |
| 0x04       | Static           |
| 0x05       | Temperature      |
| 0x06       | Visor            |
| 0x07       | Marquee          |
| 0x08       | Blink            |
| 0x09       | Sequential       |
| 0x0A       | Rainbow          |

### Speeds

| Speed Value | Speed Description |
| ----------- | ----------------- |
| 0x00        | Fast              |
| 0x01        | Medium            |
| 0x02        | Slow              |

## Temperature (0x36)

## Reset (0x37)

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | 0x37        |
| 0x01       | Channel     |

## Port State (0x38)

| Byte Index | Description                             |
| ---------- | --------------------------------------- |
| 0x00       | 0x38                                    |
| 0x01       | Channel                                 |
| 0x02       | 1: Hardware Control 2: Software Control |

## Brightness (0x39)

## LED Count (0x3A)

## Protocol (0x3B)