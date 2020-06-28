![image](uploads/6e850e25aea3ba31034275516a243ede/image.png)

The Tecknet M008 RGB mouse enumerates at 04D9:FC05.  RGB control on Interface 2.  Protocol is HID using 16-byte feature reports.  Any bytes not shown are zero.

# Select Profile Packet

Profiles range from 0 to 4.

| Byte Index | Description      |
| ---------- | ---------------- |
| 0x00       | 0x02             |
| 0x01       | 0x01             |
| 0x02       | 0x01             |
| 0x03       | Profile          |

# Set LED Packet

| Byte Index | Description      |
| ---------- | ---------------- |
| 0x00       | 0x02             |
| 0x01       | 0x04             |
| 0x02       | Red (Inverted)   |
| 0x03       | Green (Inverted) |
| 0x04       | Blue (Inverted)  |
| 0x05       | Brightness       |
| 0x06       | Breathing Speed  |

## Brightness

| Value | Description |
| ----- | ----------- |
| 0x00  | Off         |
| 0x01  | Low         |
| 0x02  | Medium      |
| 0x03  | High        |

## Breathing Speed

| Value | Description   |
| ----- | ------------- |
| 0x00  | Not Breathing |
| 0x01  | Fastest       |
| 0x03  | Medium        |
| 0x06  | Slowest       |