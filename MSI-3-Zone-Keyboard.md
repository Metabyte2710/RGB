Several MSI laptop models use a 3-zone RGB keyboard from SteelSeries.  The laptop may have additional lighting zones outside of the keyboard that are part of this same controller.  It attaches to the system via USB at 1770:FF00 and uses the HID protocol.  Commands are sent as HID feature requests.  The packet is 8 bytes long and is sent 7 times, once for each LED channel.

# Message Format

| Byte Index | Function |
| ---------- | -------- |
| 0x00       | 0x01     |
| 0x01       | 0x02     |
| 0x02       | 0x40     |
| 0x03       | LED (1-7)|
| 0x04       | Red      |
| 0x05       | Green    |
| 0x06       | Blue     |
| 0x07       | 0xEC     |