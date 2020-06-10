Gigabyte's Aorus RGB RAM uses an SMBus controller with address 0x67.  All sticks use the same address and no means of controlling individual sticks is currently known.  The protocol uses a 32-byte data packet written to internal address 0x20 using a block transfer followed by an apply command written to address 0x28 using a byte transfer.

# Data Packet Structure

This 32-byte packet is written to 0x20 using block transfer

| Byte Index | Description        |
| ---------- | ------------------ |
| 0x00       | LED Enable Mask    |
| 0x01       |                    |
| 0x02       |                    |
| 0x03       |                    |
| 0x04       |                    |
| 0x05       |                    |
| 0x06       |                    |
| 0x07       |                    |
| 0x08       |                    |
| 0x09       | Mode               |
| 0x0A       | Brightness (0-100) |
| 0x0B       |                    |
| 0x0C       | Blue               |
| 0x0D       | Green              |
| 0x0E       | Red                |
| 0x0F       |                    |
| 0x10       |                    |
| 0x11       |                    |
| 0x12       |                    |
| 0x13       |                    |
| 0x14       | Timer 0            |
| 0x15       | Timer 0            |
| 0x16       | Timer 1            |
| 0x17       | Timer 1            |
| 0x18       | Timer 2            |
| 0x19       | Timer 2            |
| 0x1A       |                    |
| 0x1B       |                    |
| 0x1C       | Color Cycle Count  |
| 0x1D       |                    |
| 0x1E       | Repetition Count   |
| 0x1F       |                    |

### Color Cycle Pattern

Pulse, Flash, Cycle, Droplet, and Wave modes support cycling through a series of colors.  The number of colors is set by the Color Cycle Count value.  The colors cycle in the following order:

| Slot | Color   |
| ---- | ------- |
| 1    | Red     |
| 2    | Orange  |
| 3    | Yellow  |
| 4    | Green   |
| 5    | Blue    |
| 6    | Magenta |
| 7    | Pink    |

If the Color Cycle Count is greater than 7, it looks like additional slots are all black.  Maybe there's a way to change these slot values.

When the Color Cycle Count is zero:

* Pulse, Flash - Disables cycling and uses provided color

* Cycle, Wave - Sits at slot 1 (Red)

* Droplet - First LED lights briefly with previous color and fades to black

### Modes

| Mode Value | Mode Description    |
| ---------- | ------------------- |
| 0x01       | Static              |
| 0x02       | Pulse               |
| 0x03       | Flash               |
| 0x04       | Color Cycle         |
| 0x05       | Color Droplet       |
| 0x06       | Wave / Color Strobe |
| 0x07       | Cascade             |

# Apply Command

Write 0x0F to 0x28