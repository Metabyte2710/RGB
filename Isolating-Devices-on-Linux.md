Isolating a device on a Linux system is much easier as there are command line tools that tell us all the info we need.

# List USB Devices

From the terminal, you can run the `lsusb` command which will give us more than we need.

1. Open the terminal
1. Type `lsusb`
1. Find the device in the list
1. Note the bus and device number as it will be used for the filter in the next step

![image](uploads/d2a6a35f48cc6e272ca5426af08073f0/image.png)

Note: If you didn't already know VID and PID for your device you can also get those details from `lsusb`. In this case the M711 is VID = 2516 and PID = 0101.