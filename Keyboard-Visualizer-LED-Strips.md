In my Keyboard Visualizer project, I published some Arduino sketches for controlling WS2812B LED strips with an Arduino.  OpenRGB supports these Arduino sketches.  To configure an LED strip in OpenRGB, create a file called ledstrip.txt in the same directory as the OpenRGB executable.  In this file, add one ledstrip line per attached Arduino LED strip.

The format of the ledstrip line is:

ledstrip=COM1,115200,30

* The first entry, COM1 in this case, is the serial port of the Arduino.  On Linux this is usually /dev/ttyX or /dev/ACMX.

* The second entry, 115200 in this case, is the baud rate.  The Arduino sketches use 115200 but it can be modified if you change the sketch.

* The third entry, 30 in this case, is the number of LEDs on the strip.  This should match the number of LEDs set in the Arduino sketch, as the two must match for the protocol to function correctly.