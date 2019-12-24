The AMD Wraith Prism stock cooler is a multi-zone RGB device manufactured for AMD by Cooler Master.  It connects to the motherboard using three connectors - a PWM fan header that runs the fan and powers the LEDs, a USB header for advanced control, and an RGB header for control of the fan color through the motherboard's RGB controller.  The USB interface allows full control of the RGB so it is the interface this information will be focused on.  It enumerates at 2516:0051 and uses USB interrupt transfers to communicate with the host software.

All messages are 64 bytes long.  There appear to be multiple packets that can be sent.

# Enable control
Send this packet to initialize the device after a power cycle or reconnect.  Should be sent once when first opening the device.

| Byte index | Value  |
| ---------- | ------ |
| 0x00       | 0x41   |
| 0x01       | 0x80   |
| 0x02 - end | 0x00   |

# Remap LEDs
This packet maps the individual LEDs to effect channels.  There seems to be some limitation on which LEDs map to which channels.  This is not fully understood.

| Byte index | Value  | Description             |
| ---------- | ------ |                         |
| 0x00       | 0x51   |                         |
| 0x01       | 0xA0   |                         |
| 0x02       | 0x01   |                         |
| 0x03       | 0x00   |                         |
| 0x04       | 0x00   |                         |
| 0x05       | 0x03   |                         |
| 0x06       | 0x00   |                         |
| 0x07       | 0x00   |                         |
| 0x08       | 0x05   | Channel for Logo LED    |
| 0x09       | 0x06   | Channel for Fan LED     |
| 0x0A       | 0x07   | Channel for Ring LED 0  |
| 0x0B       | 0x07   | Channel for Ring LED 1  |
| 0x0C       | 0x07   | Channel for Ring LED 2  |
| 0x0D       | 0x07   | Channel for Ring LED 3  |
| 0x0E       | 0x07   | Channel for Ring LED 4  |
| 0x0F       | 0x07   | Channel for Ring LED 5  |
| 0x10       | 0x07   | Channel for Ring LED 6  |
| 0x11       | 0x07   | Channel for Ring LED 7  |
| 0x12       | 0x07   | Channel for Ring LED 8  |
| 0x13       | 0x07   | Channel for Ring LED 9  |
| 0x14       | 0x07   | Channel for Ring LED 10 |
| 0x15       | 0x07   | Channel for Ring LED 11 |
| 0x16       | 0x07   | Channel for Ring LED 12 |
| 0x17       | 0x07   | Channel for Ring LED 13 |
| 0x18       | 0x07   | Channel for Ring LED 14 |
| 0x19 - end | 0x00   |                         |