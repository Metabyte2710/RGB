# Using OpenRGB

OpenRGB automatically tries to detect your RGB hardware when you start the application.  It may take some time to complete detection before the main window shows up.  If the main window is empty, it means OpenRGB could not detect your devices.  Follow the instructions in the README for setting up access to your devices.  On Windows, this usually means you need to run as administrator.  On Linux, it means you probably need to install the udev rules or install the kernel patch.

# Changing Modes

OpenRGB devices have one or more modes.  Modes represent different effects built into the RGB device's hardware.  Most devices have at least one mode that allows direct control of individual LEDs from software and one or more built-in effect modes (rainbows, spectrum cycles, etc).  Modes can have four different color configurations:

  * Per-LED Color - This color configuration allows you to set a specific color for each LED on the device independently
  * Mode-Specific Color - This color configuration allows you to set one or more colors, but the colors do not apply to individual LEDs.  An example would be a breathing mode that cycle between one or more preset colors.
  * Random Color - This color configuration does not have user-set colors.  An example would be a breathing mode that cycles through the spectrum or random colors each cycle.
  * None - This is usually the same as Random Color, but the mode doesn't have any other available color configurations.

The mode controls are shown in the screenshot below:

![bitmap](uploads/8fbe6053a6fd45c366a9d66181576399/bitmap.png)

To change modes, click on the Mode selection box and select a different mode from the list.

![image](uploads/1ecd831d339094ec97bdb82f9e42065f/image.png)

You can change the color configuration using the three buttons in the Colors: group.  Only the available color configurations for the selected mode will be clickable.

![image](uploads/2ed2b2b14e64d98e206a78e75d30a394/image.png)

If the mode supports it, you can adjust the speed slider to change the speed of the mode's effect.

![image](uploads/1a34806625ba9cf6a64c53365fc2ba84/image.png)

If the mode supports it, you can adjust the direction of the mode by selecting a direction from the Direction selection box.

![image](uploads/938578968a8a65338187d47453b7e4ae/image.png)