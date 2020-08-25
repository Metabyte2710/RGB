## ![OpenRGB](uploads/5b7e633ac9f63b00c8a4c72686206c3f/OpenRGB.png)

One of the biggest complaints about RGB is the software ecosystem surrounding it.  Every manufacturer has their own app, their own brand, their own style.  If you want to mix and match devices, you end up with a ton of conflicting, functionally identical apps competing for your background resources.  On top of that, these apps are proprietary and Windows-only.  Some even require online accounts.  What if there was a way to control all of your RGB devices from a single app, on both Windows and Linux, without any nonsense?  That is what OpenRGB sets out to achieve.  One app to rule them all.

## Features

* Set colors and select effect modes for a wide variety of RGB hardware
* Save and load profiles
* Control lighting from third party software using the OpenRGB SDK
* Command line interface
* Connect multiple instances of OpenRGB to synchronize lighting across multiple PCs
* Can operate standalone or in a client/headless server configuration
* View device information
* No official/manufacturer software required

## Supported Devices

* The supported devices list was getting long and has moved to its own page: [Supported Devices](Supported-Devices)

## WARNING!

This project interacts directly with hardware using reverse engineered protocols. While we do our best to make sure we're sending the right data, there is always some risk in sending data to hardware when we don't understand exactly how that hardware works.

There have been two instances of hardware damage in OpenRGB's development and we've taken precautions to prevent it from happening again.

* The MSI Mystic Light code reportedly bricked the RGB on certain MSI boards when sending certain modes. This code has been disabled and MSI Mystic Light motherboards will not work with OpenRGB at this time.
* There were reports of bricked Gigabyte Aorus Z390 motherboards caused by dumping SMBus address 0x68 in an attempt to reverse engineer the RGB. Due to this, the SMBus Tools page on OpenRGB is hidden by default now as it has no real use to non-developers. Additionally, the RGB Fusion 2 SMBus code is disabled by default because, although it works on boards it is meant for, probing this address (0x68) could damage Gigabyte Z390 boards.
* To enable the MSI Mystic Light or Gigabyte RGB Fusion 2 SMBus code, you must uncomment the functions in main.cpp and recompile.

## Screenshots

![OpenRGB_0.31_Device_View](uploads/e1d8d4603ecdd04f1acbcf6b2314fc66/OpenRGB_0.31_Device_View.PNG)

## Join Our Discord

* https://discord.gg/AQwjJPY

## How-Tos and FAQs

* [Windows Setup and Usage](OpenRGB-Windows-Setup-and-Usage)
* [Frequently Asked Questions](Frequently-Asked-Questions)

## Support OpenRGB

* OpenRGB is a project I created to solve a problem I had with the RGB ecosystem.  My goal isn't to make money off of this project.  That said, people have requested to donate, and donations allow me to buy more RGB stuff to reverse engineer.
* [Donate via PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=4VPTFMD3G4QVG&item_name=OpenRGB+Development&currency_code=USD&source=url)
* [Become a Patron](https://www.patreon.com/CalcProgrammer1) (I'm not doing any Patreon-exclusive content, it's purely for donation)
* Donate via Bitcoin: 1N83YPu7btXYadPS1neB9zX7X1QTdpyZQ

## History of OpenRGB

* OpenRGB is a continuation of OpenAuraSDK, which itself was created out of reverse engineering work done on the Keyboard Visualizer project.  For a complete history of the RGB projects that led to OpenRGB's creation, see the [History page](History-of-OpenRGB).

## Contributing

* Want to contribute support for a new device?  Check out the [RGBController API](The-RGBController-API) page for documentation of how OpenRGB implements device control.