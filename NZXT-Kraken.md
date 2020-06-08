The NZXT Kraken series of AIO liquid cooling devices support RGB lighting as well as pump and fan control.  The NZXT Kraken controller uses the USB HID protocol with 65 byte writes and 64 byte reads.

# Supported Devices

| Device                      | USB ID    |
| --------------------------- | --------- |
| NZXT Kraken X42/X52/X62/X72 | 1E71:170E |

# Set Effect

| Byte Index | Description                  |
| ---------- | ---------------------------- |
| 0x00       | 0x02                         |
| 0x01       | 0x4C                         |
| 0x02       | Channel, Movement, Direction |
| 0x03       | Mode                         |
| 0x04       | Speed, Size, Color In Set    |
| 0x05       | Color Data (RGB x9)          |
