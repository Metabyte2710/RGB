The  Coolermaster mouse pad 750 is about the simplest RGB controller there is. Consisting of a single zone with 2 physical LEDS, addressed as 1 because they can not be controlled independently. The Masterplus Windows app (see screenshot below) allows setting Colour Cycle, Static, Breathing and off but after some playing there was found to be 2 more modes Blink and Breathing Colour Cycle.

[[_TOC_]]

[image](https://gitlab.com/CalcProgrammer1/OpenRGB/uploads/78c1cd4f2aa456b731ba93537be59f73/MP750windows.jpg)

# Report Descriptor

The report descriptor is very basic and does *not* use HID reports at all.

| Byte Index | Description |
| ---------- | ----------- |
| 0x06, 0x00, 0xFF | Usage Page (Vendor Defined 0xFF00) |
| 0x09, 0x01 | Usage (0x01) |
| 0xA1, 0x01 | Collection (Application) |
| 0x09, 0x02 |   Usage (0x02) |
| 0x15, 0x00 |   Logical Minimum (0) |
| 0x26, 0x00, 0xFF |   Logical Maximum (-256) |
| 0x75, 0x08 |   Report Size (8) |
| 0x95, 0x40 |   Report Count (64) |
| 0x81, 0x06 |   Input (Data,Var,Rel,No Wrap,Linear,Preferred State,No Null Position) |
| 0x09, 0x02 |   Usage (0x02) |
| 0x15, 0x00 |   Logical Minimum (0) |
| 0x26, 0x00, 0xFF |   Logical Maximum (-256) |
| 0x75, 0x08 |   Report Size (8) |
| 0x95, 0x40 |   Report Count (64) |
| 0x91, 0x06 |   Output (Data,Var,Rel,No Wrap,Linear,Preferred State,No Null Position,Non-volatile) |
| 0xC0 | End Collection |

# Protocol

The protocol allows for 64 bytes to be sent in any one transaction but the control codes are significantly shorter owing to the simplicity of the device.

| Byte Index | Description |
| ---------- | ----------- |
| 0x00       | Mode |
| 0x01       | Command length in bytes |
| 0x02       | Red or Mode Speed (random colour modes)|
| 0x03       | Green |
| 0x04       | Blue |
| 0x05       | Mode Speed |

# Modes

| Mode       | Description |
| ---------- | ----------- |
| 0x01       | Static |
| 0x02       | Blinking <span title="Not implemented in offical app"><sup>NB</sup></span> |
| 0x03       | Breathing |
| 0x04       | Colour Cycle |
| 0x05       | Breathing Colour Cycle <span title="Not implemented in offical app"><sup>NB</sup></span> |
| 0x07       | Get Mode Report |