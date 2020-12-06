If you wanted to implement support for your USB device then the first step in that process is to know how to talk to the device. 

[[_TOC_]]

# Prequisites

Whilst there is no requisite coding knowledge needed for this step it is assumed that you can

* install and configure windows software
* know how to count in hex ([hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal))
* Are familiar with the terms Header, packet, data and report descriptor as it applies to the USB protocol
* USBPcap [capture format specification](https://desowin.org/usbpcap/captureformat.html)

Further to this you have optionally read
* This quick primer on [USB HID](https://wiki.osdev.org/USB_Human_Interface_Devices)
* the [USB spec](https://www.usb.org/document-library/usb-32-specification-released-september-22-2017-and-ecns)
* the [USB HID Device Class Spec](https://www.usb.org/document-library/device-class-definition-hid-111)

# Software

* [Wireshark](https://www.wireshark.org/download.html) and USBPcap when prompted
* The RGB app supplied by the vendor for your device

# Process

What we're going to be doing over the next few steps is roughly equivalent of witnessing a conversation between 2 people in a language that
 we don't personally speak. Later on we then have to figure out what was said so that we can reproduce that speech. What helps is that we
 are in control of the script. Before doing that though it helps to have some information about the capabilities of the device.

## Isolating the Device

For Linux instructions [please see here](Isolating Devices on Linux).

Ideally what will be needed for the analysis is clear and concise packet captures
 that contain all the information we do need, without any noise from devices that we don't need. The way to get this is to isolate the device
 onto a USB host where it doesn't share that host with any other device, or at least is shared with devices that don't need to communicate to 
 the system. This is doubly tricky if we're trying to inspect packets from the keyboard or mouse that we're using so if you have a second 
 device to use, now is the time to plug it in. A quick rule of thumb to get devices on different hosts is to unplug everything from the front
 panel of your PC and plug the device you want to capture from into there. This assumes that you have USB ports on your front panel and that
 the capture device is a standard USB plug. A device that just has a USB header connector for the motherboard e.g. AMD Wraith Prism, will
 probably already be on it's own host.

First lets figure out which host our device is plugged into. Open Wireshark and select all the USB hosts to find the device and
 then we can start the capture again just focusing on that host. In this example I'm going to be using a Coolermaster MM711.

With Wireshark open, click the first USB host "USBPcap1" and then shift click the last on your computer which for me was "USBPcap4".
 To start the capture you can click the blue shark fin under "File". Windows should prompt you with UAC for each host that you've selected
 as it requires admin rights to monitor. Click "yes" for each prompt.

You should then see something similar to the following screenshot. Note there is some packets already in the list which is the host
 "handshaking" with each device. 

![Wireshark opened capturing all USB hosts](uploads/3c1b6ea3ffbbbedc46c264da0479f6e6/Wireshark_opened_capturing_all_USB_hosts.jpg)

Now we just need to move the mouse a little and see the captured packets.

![Wireshark_capturring_a_MM711_mouse_movement](uploads/d6169acc7e23cedded9b684aef02bfda/Wireshark_capturring_a_MM711_mouse_movement.jpg)

In the screenshot above it shows that Wireshark is talking to 
destination `3.1.1` or when put another way; the MM711 is connected to the root hub 3, and is device 1 on that hub. A side note at this point, the final `.1` is the endpoint on the device which is not 
relevant just yet but may be important later. 

Knowing that the mouse is connected to root hub 3, we can therefore
select just the USBPcap3 device in the next steps. Clearly your 
device may be on a different root hub so make a note of it for later. 

![Wireshark_opened_capturing_just_the_host_of_the_MM711](uploads/c836d94117804884dee467a2f73017a8/Wireshark_opened_capturing_just_the_host_of_the_MM711.jpg)

Stop the capture and discard it without saving before proceeding to the next step.

## Descriptors

For Linux instructions [please see here](Report Descriptors on Linux).

If you have read the USB spec from above you may be aware of the "handshake" a USB device does whenever it's plugged into a host. That little
 bit of data describes how the USB host can talk to the device prior to a driver taking over. OpenRGB will *need* some of that data because
 essentially we want OpenRGB to act as the driver for the RGB device. There is also other parts of the descriptor data that point to what and
 how the device is planning to communicate. Wireshark can capture the
Report Descriptor by running the capture and unplugging, then replugging the device.

1. Open Wireshark
1. Select the appropriate USBPcap from the previous steps
1. Unplug the device
1. Replug the device
1. Stop the capture
1. Save the capture as `xxxx_xxxx_ReportDescriptor.pcapng` in a safe place as it is needed later. 

## Captures

This is where the bulk of the work is done. In order to analyse the
protocol you're going to want some captures of the basics of what
your device can do. That list will include capturing packets for the following

1. Whole device lit as static RED
1. Whole device lit as static GREEN
1. Whole device lit as static BLUE
1. Whole device off
1. One capture that includes all modes using one colour (White is a good choice for this capture)
1. One capture that includes all brightnesses (if supported)
1. One capture that includes speeds for a mode (e.g. slow to fast flashing mode)

It is a good idea to add comments to packets as they are being
captured to make the analysis step easier. You can add comments to packets with a "right click" -> "packet comments". It is suggested to 
tag the first and last packet of a change with any of the variables that can be selected in that mode. That is "Changed to MODE COLOUR SPEED BRIGHTNESS" etc. For example if you are capturing the Breathing mode the packet comment would be "Changed to Breathing PURPLE Speed1 (Slow) full brightness". Alternatively Rainbow mode, which does not require a colour or brightness might be "Changed to Rainbow Speed5 (Fast)".

For each capture it is preferred to have a separate capture save file
".pcapng" which will also assist when analysing and debugging. TO achieve this start each capture fresh by clicking the shark fin with a circular arrow on it (3rd on the toolbar) or select "Capture" -> "Restart". You can even use the keyboard shortcut "Ctrl + R".

When saving each capture please include the device name as well as the mode which will help identify captures in the submission step.

## Submission

Once you've gathered all the packet capture files and other supporting USB info the best place to submit that is in [an appropriate issue](https://gitlab.com/CalcProgrammer1/OpenRGB/-/issues/). Below is a template of the information that someone writing a new controller is going to need. Even if you intend to write the controller yourself adding this info to the issue is a worthwhile step to capture the thoughts of the other developers and also any other users who may have the device.

Title:
```
 Please add support for <Name of device>
```

Description:
```
 Please add support for the <name of device> with <VID Vendor ID>:<PID Product ID>
 
Captures:
 <Initialisation Capture File>
 <Red Capture File>
 <Green Capture File>
 <Blue Capture File>

Modes:
 <Mode0 capture file>
 <Mode1 capture file>
 ...
 <ModeX capture file>
```

Once you have added a comment to an issue you will receive emails for any updates to that issue. This is useful for corresponding with anyone who is writing the code for the device or alternatively you intend to [write the controller](Writing the Controller) also.
 interested in the progress of the controller.!