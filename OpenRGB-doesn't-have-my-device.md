You've [searched the wiki](https://gitlab.com/CalcProgrammer1/OpenRGB/-/wikis/Supported-Devices), you've [looked into the code](https://gitlab.com/CalcProgrammer1/OpenRGB/-/tree/master), you [came to Discord](https://discord.gg/AQwjJPY) and your device is not supported...   

yet! Here's an overview of what needs to occur in order to support a new device.

[[_TOC_]]

# Check Existing Issues

The first step in asking for a new device is to go to the [issues page](https://gitlab.com/CalcProgrammer1/OpenRGB/-/issues) and check to see if someone has already requested support for it. Chances are if someone is already working on it you'll just want to add yourself to that issue to receive notifications or you can add relevant information where needed.

If reading through the list of issues leaves you feeling lonely and you're the only one asking for the device, it's time to create a [new device issue](https://gitlab.com/CalcProgrammer1/OpenRGB/-/issues/new). There is a `New Device` template which can be selected from the list.

![image](uploads/29b03320e0ca2506fdc3a8ae4ecb33aa/image.png)

You would then proceed to fill in the relevant details for the new device.

# Talking to the Device

The next step involves figuring out how to talk to the device to tell it how to change modes and what colours, and speeds to light up the world! Next to writing the code itself this is the most tedious part of the process and requires it's own page to explain in detail. The one line summary though is we're going to monitor
how the OEM software talks to the device and then figure out the important parts of those messages.

An often overlooked part of this process is knowing *how* the device is connected to the computer. For USB devices that's very easy to identify but for any daughter boards plugged into or anything on the motherboard this is not always obvious. As a rule of thumb though we're going to assume that it's a USB device that you're looking to support and therefore you'll want to read the [capturing with Wireshark](USB Captures Using Wireshark) page.

If you're not sure, or you know it's not a USB device then come chat [on Discord](https://discord.gg/AQwjJPY) or through the issue created in the previous step.

# Writing the wiki entry

It might seem like now that you know how to talk to the device the next step would be to replicate that by writing some code. Just before we get there it's best to write the wiki entry to document the analysis from the packet captures.

There's no hard and fast rule here as the variety of RGB devices don't allow for a simple template. It would be sensible to read the other entries on the wiki to get a sense of how and what to write. For an example of a simple entry look at the [Coolermaster MP750](https://gitlab.com/CalcProgrammer1/OpenRGB/-/wikis/Cooler-Master-MP750) mousepad or for a more complex controller there's the [AMD Wraith Prism](https://gitlab.com/CalcProgrammer1/OpenRGB/-/wikis/AMD-Wraith-Prism).

If you're not familiar with writing markdown there is a help page for [gitlab related markdown](https://gitlab.com/help/user/markdown) which is also worth your time.

# Writing the Code

If you're intending to write the C++ code yourself then you'll want to read the dedicated wiki page for [how OpenRGB is put together](https://gitlab.com/CalcProgrammer1/OpenRGB/-/wikis/The-RGBController-API). That page covers everything from setting up the build environment through to what is the minimum set of files to write a new device.

# Testing the Device

A critical part of the process is testing the device to ensure that it does everything you expect it to do and nothing you don't. A good example of that is a mouse controller was coded up but until a second person tested the code we didn't realise that it was also setting the DPI of the mouse.

The code is not likely to be a part of the mainline repository at this stage so if you're not the person writing the controller you should be able to get built binaries of the code from the develper. Any problems / thoughts / comments and feedback at this stage should go back into the relevant issue on gitlab.

# Closing the issue

Once the device owner and the developer agree that the device is supported [a merge request](https://gitlab.com/CalcProgrammer1/OpenRGB/-/merge_requests) should be submitted. This is the final step in the process. It may involve some discussion with the maintainers to satisfy any outstanding problems with the code they may have. Once the code is merged the maintainers the maintainers will also close the issue.