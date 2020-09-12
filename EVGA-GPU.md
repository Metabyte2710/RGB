Some EVGA graphics cards have an RGB controller that enumerates on the GPU I2C bus at address 0x49.  This controller uses basic chip addressing and exposes registers for RGB control.

# Registers

| Register Address | Description |
| ---------------- | ----------- |
| 0x09             | Red         |
| 0x0A             | Green       |
| 0x0B             | Blue        |
| 0x0C             | Mode        |

# Modes

| Mode Value | Description |
| ---------- | ----------- |
| 0x00       | Off         |
| 0x01       | Static      |
| 0x02       | Rainbow     |
| 0x05       | Breathing   |