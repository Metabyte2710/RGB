In order to support a new RGB device in OpenRGB, we must first understand how to talk to the device.  This includes which hardware interface(s) the device uses to connect to the PC as well as the communication protocol in which commands are sent.  To learn this information, there are many reverse engineering techniques and tools which we can use.

Step 1:  Determine hardware interface(s)

The first step in reverse engineering a new device is to determine what interface it connects to the PC with.  For external devices, this is almost always USB.  If it plugs into a USB port or USB header on the motherboard, that's all you need to know.  If it uses an RGB header, then your device doesn't actually have a controller built in.  Your motherboard's on-board RGB controller is responsible for controlling RGB headers.  That leads us to on-board RGB devices, which is where the confusion really starts.  On-board devices can use any number of interfaces, but in practice we have only seen two interfaces used - SMBus and USB.  SMBus is a low level interface present on most motherboards and is used to communicate with various chips on the motherboard.  USB can also be used for motherboard devices.  As for DDR memory modules, these only have an SMBus connection and a memory bus connection, and the memory bus is incredibly unlikely to be used for RGB.  RGB memory modules almost certainly use SMBus.  Graphics cards pose another unique situation - their RGB controllers almost always use I2C (very similar to SMBus) but the I2C controller is built into the GPU and is accessed via proprietary, undocumented libraries on Windows.

SMBus Issues

SMBus is a rather difficult situation compared to USB.  There are easy ways to communicate with USB devices built into every modern OS.  SMBus, on the other hand, is not meant for direct user access and does not have an API on Windows.  Linux does, however, provide userspace access to SMBus/I2C devices using i2c-dev and i2c-tools.  The SMBus controllers are typically memory mapped in I/O memory space.  By using some code from the Linux kernel along with the InpOut32 library, I was able to port the i2c-piix4 and i2c-i801 SMBus controller drivers to Windows.  PIIX4 is used on AMD platforms and i801 is used on Intel platforms.

AMD's chipsets actually provide two identical SMBus controllers while Intel's chipsets only provide one.  This apparently led ASUS to wire the RGB controller on their Intel boards to the SMBus controller in the Nuvoton Super-IO chip.  Linux did not provide a driver for this controller, so I wrote one based on the Nuvoton datasheet.

Reverse engineering tools

Wireshark.  Wireshark is a packet capture tool that can capture network and USB traffic.  USB capture in Wireshark is provided on Windows by the bundled USBPcap application and the usbmon interface on Linux.

SMBus sniffer branches (i2c_sniffer_piix4 and i2c_sniffer_i801).  These are tools I hacked up from the OpenAuraSDK source code that monitor the SMBus controller for activity and then print any transfers that occur.

API Monitor.  This tool can hook a Windows process and print out all calls to specific DLL files.  This can be useful for learning how unknown devices communicate if not SBMus or USB.  Try to hook as many DLL files as possible and then see what gets called when changing light modes.  If any functions look promising, this tool lets you see the memory before and after each call to try to determine the arguments.

