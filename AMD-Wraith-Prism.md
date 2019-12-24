The AMD Wraith Prism stock cooler is a multi-zone RGB device manufactured for AMD by Cooler Master.  It connects to the motherboard using three connectors - a PWM fan header that runs the fan and powers the LEDs, a USB header for advanced control, and an RGB header for control of the fan color through the motherboard's RGB controller.  The USB interface allows full control of the RGB so it is the interface this information will be focused on.  It enumerates at 2516:0051 and uses USB interrupt transfers to communicate with the host software.

All messages are 64 bytes long.  There appear to be multiple packets that can be sent.

# Enable control
Send this packet to initialize the device after a power cycle or reconnect.  Should be sent once when first opening the device.

| Byte index | Value  |
| ---------- | ------ |
| 0x00       | 0x41   |
| 0x01       | 0x80   |
| 0x02-end   | 0x00   |

