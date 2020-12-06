If you have read the USB spec you may be aware of the "handshake" a USB device does whenever it's plugged into a host. That little
 bit of data describes how the USB host can talk to the device prior to a driver taking over. OpenRGB will use some of that data because
 essentially we want OpenRGB to act as the driver for the RGB device. There is also other parts of the descriptor data that point to what and
 how the device is planning to communicate.

1. Open the terminal
1. Determine the Vendor Identification (VID) and Product Identification (PID) by running `lsusb` and noting the xxxx:xxxx of your device
1. `lsusb -vd xxxx:xxxx >> xxxx_xxxx_DeviceDescriptor.txt` substituting the X's from the previous step
1. `sudo usbhid-dump -d xxxx:xxxx >> xxxx_xxxx_ReportDescriptor.txt` again substituting the X's. NB:This step has to be run as root
1. You should now have two text files saved in the directory which you can check by typing `ls`.
 Save them in a safe place for now as we will need them later.