The NZXT Kraken series of AIO liquid cooling devices support RGB lighting as well as pump and fan control.  The NZXT Kraken controller uses the USB HID protocol with 65 byte writes and 64 byte reads.

# Supported Devices

| Device                      | USB ID    |
| --------------------------- | --------- |
| NZXT Kraken X42/X52/X62/X72 | 1E71:170E |

# Send Effect

| Byte Index | Description                  |
| ---------- | ---------------------------- |
| 0x00       | 0x02                         |
| 0x01       | 0x4C                         |
| 0x02       | Channel, Movement, Direction |
| 0x03       | Mode                         |
| 0x04       | Speed, Size, Color In Set    |
| 0x05       | Color Data (9x R/G/B)        |

# Status Update

Perform an HID read to get this packet

To get liquid temperature, (pkt[0x01] + (0.1 * pkt[0x2]))

Firmware string is \<Major\>.\<Minor\>.\<Patch\>

| Byte Index | Description             |
| ---------- | ----------------------- |
| 0x00       |                         |
| 0x01       | Liquid Temperature x1   |
| 0x02       | Liquid Temperature x0.1 |
| 0x03       | Fan Speed MSB           |
| 0x04       | Fan Speed LSB           |
| 0x05       | Pump Speed MSB          |
| 0x06       | Pump Speed LSB          |
| 0x07       |                         |
| 0x08       |                         |
| 0x09       |                         |
| 0x0A       |                         |
| 0x0B       | Firmware Major          |
| 0x0C       | Firmware Minor MSB      |
| 0x0D       | Firmware Minor LSB      |
| 0x0E       | Firmware Patch          |