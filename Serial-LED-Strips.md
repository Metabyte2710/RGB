There are several serial protocols for controlling LED strips.  These protocols are often used in combination with Arduino or similar microcontrollers to drive addressable LEDs.  Serial LED strip controllers can be configured in the OpenRGB configuration file.  The following protocols are supported:

| Protocol            | Description                                                                                                                     |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| keyboard_visualizer | From my old Keyboard Visualizer project [Arduino Sketches](https://gitlab.com/CalcProgrammer1/KeyboardVisualizer/-/tree/KeyboardVisualizer_3.x)                                                                        |
| adalight            | Adalight protocol [Arduino Sketch](https://www.electronoobs.com/eng_arduino_tut29_code2.php)                                    |
| tpm2                | TPM2 protocol [Info](https://gist.github.com/jblang/89e24e2655be6c463c56), [Arduino Sketches](https://github.com/rstephan/TPM2) |

An example LED strip configuration:

```
    "LEDStripDevices": {
        "devices": [
            {
                "port": "COM1",
                "baud": 115200,
                "num_leds": 30,
                "protocol": "keyboard_visualizer"
            }
        ]
    }
```

* `port` - COM1 in this case, is the serial port of the Arduino.  On Linux this is usually /dev/ttyX or /dev/ACMX.

* `baud` - 115200 in this case, is the baud rate.  The Arduino sketches use 115200 but it can be modified if you change the sketch.

* `num_leds` - 30 in this case, is the number of LEDs on the strip.  This should match the number of LEDs set in the Arduino sketch, as the two must match for the protocol to function correctly.

* `protocol` - The selected protocol from the above table