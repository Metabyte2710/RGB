![20200101_181654](uploads/e7d3b08c861d83bac5304b945d59c6c4/20200101_181654.jpg)

The Patriot Viper RGB memory enumerates an SMBus device at 0x77.  It uses an SMBus protocol that uses two SMBus byte writes for writing 3 bytes to an address.  The protocol works as follows:

Write \<Value 1\> to \<Address\>

Write \<Value 2\> to \<Value 3\>

To initiate a write sequence, you have to write 0xFF to address 0xFF twice.

# Addresses

| Address | Value 1   | Value 2    | Value 3     | Description     |
| ------- | --------- | ---------- | ----------- | --------------- |
| 0x01    | 0x04      | 0x00       | 0x00        | Start (?)       |
| 0x03    | Mode      | ?          | ?           | Mode            |
| 0x30    | LED 0 Red | LED 0 Blue | LED 0 Green |                 |
| 0x31    | LED 1 Red | LED 1 Blue | LED 1 Green |                 |
| 0x32    | LED 2 Red | LED 2 Blue | LED 2 Green |                 |
| 0x33    | LED 3 Red | LED 3 Blue | LED 3 Green |                 |
| 0x34    | LED 4 Red | LED 4 Blue | LED 4 Green |                 |
| 0x35    | 0x01      | 0x00       | 0x00        | Apply Changes   |
| 0xFF    | 0xFF      | 0xFF       | 0xFF        | Start Frame (?) |

# Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x00       | Dark             |
| 0x01       | Breathing        |
| 0x02       | Viper            |
| 0x03       | Heartbeat        |
| 0x04       | Marquee          |
| 0x05       | Raindrop         |
| 0x06       | Aurora           |
| 0x07       | Neon             |
