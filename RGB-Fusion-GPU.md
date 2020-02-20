Some of Gigabyte's Aorus graphics cards come with a single-zone RGB controller.  The Aorus GeForce GTX 1080Ti Xtreme is one such card.  Its RGB controller is attached via the first GPU I2C bus and enumerates at address 0x47.  Writes are done using block transfers.  Invalid I2C operations on the RGB controller cause the controller to lock up, requiring a reboot before it will respond again.

# Registers

| Register Address | Description                         |
| ---------------- | ----------------------------------- |
| 0x40             | Color Data (R, G, B)                |
| 0x88             | Mode Data (Mode, Speed, Brightness) |
| 0xAB             | Detection value (Read 0x14)         |

# Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x01       | Static           |
| 0x02       | Breathing        |
| 0x04       | Flashing         |