Some ASUS graphics cards have a single zone RGB controller attached to the first GPU I2C interface which enumerates at either address 0x29, 0x2A, or 0x60 depending on model.  Communication is done using standard 8-bit I2C chip register addressing.

# Registers

| Register Value | Register Description |
| -------------- | -------------------- |
| 0x04           | Red                  |
| 0x05           | Green                |
| 0x06           | Blue                 |
| 0x07           | Mode                 |
| 0x0C           | Sync                 |
| 0x0E           | Apply                |
| 0x20           | Fixed 0x15           |
| 0x21           | Fixed 0x89           |

# Modes

| Mode Value | Mode Description |
| ---------- | ---------------- |
| 0x01       | Static           |
| 0x02       | Breathing        |
| 0x03       | Flashing         |
| 0x04       | Spectrum Cycle   |