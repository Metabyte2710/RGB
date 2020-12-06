In my Keyboard Visualizer project, I published some Arduino sketches for controlling WS2812B LED strips with an Arduino via serial port.  OpenRGB supports these Arduino sketches.  Serial LED strip controllers can be configured in the OpenRGB configuration file.

An example LED strip configuration:

```
    "LEDStripDevices": {
        "devices": [
            {
                "port": "COM1",
                "baud": 115200,
                "num_leds": 30
            }
        ]
    }
```

* `port` - COM1 in this case, is the serial port of the Arduino.  On Linux this is usually /dev/ttyX or /dev/ACMX.

* `baud` - 115200 in this case, is the baud rate.  The Arduino sketches use 115200 but it can be modified if you change the sketch.

* `num_leds` - 30 in this case, is the number of LEDs on the strip.  This should match the number of LEDs set in the Arduino sketch, as the two must match for the protocol to function correctly.