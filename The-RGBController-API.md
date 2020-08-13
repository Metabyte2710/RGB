Device support in OpenRGB can be broken down into three major components.
  * Controller
  * Detector
  * RGBController

# Controller

A device's Controller class is a free-form class that provides whatever functionality is necessary to communicate with a device.  This class should implement functions to send control packets to a device and receive information packets from a device.  It should provide the capability to set device colors and modes.  The Controller header file should provide defined constants for mode, speed, and other control values specific to the device's protocol.  If possible, this class should provide the capability to retrieve firmware version and serial number information from the device.  This class can also provide additional device protocol functionality even if it goes unused in OpenRGB currently.  For instance, you may provide functions for controlling mouse DPI, polling rate, fan speed, or any other device-specific capability you want.  If OpenRGB ever implements these extra functions in the future, having them implemented already in the Controller will make that easier.

# Detector

A device's Detector function scans the attached devices to see if a particular device (Controller/RGBController) exists.  At the moment, two types of detectors exist - I2C and non-I2C.  Detectors for I2C devices are passed a vector of I2C bus pointers to scan while non-I2C detectors are not passed anything extra, usually relying on hidapi to detect USB devices.  The REGISTER_DETECTOR macro is used to register a detector function with the OpenRGB Resource Manager which is responsible for calling detector functions at detection time.

# RGBController

OpenRGB uses an internal API called RGBController to standardize the interface to RGB devices from multiple vendors and classes.  This API uses vectors to describe each device.

Devices contain modes, zones, and LEDs.  Devices also have a name and a type.  The type is an enum value which indicates whether the device is a motherboard, DRAM, keyboard, mouse, or one of several other types of common RGB devices.  The RGBController class also contains a vector called `colors` which contains 32-bit color values (0x00BBGGRR) for each LED on the device.

Modes represent internal effects and have a name field that describes the effect.  The mode's index in the vector is its ID.

Zones describe a group of LEDs.  Zones have one of three types - single, linear, and matrix.  Single zones are zones which only have one controllable LED channel and are thus all one color.  Linear zones represent rows or strips of LEDs where each LED can be its own color.  Matrix zones represent grids of LEDs.  Each zone contains a zone map which is a vector of vectors.  This represents rows and columns, with the data points in the vector being LED indices.

LEDs each have a name and their index in the LEDs vector matches with the index used in the zone map.

# Functions

## `int GetMode()`
Returns the currently enabled mode of the device.  The returned int should line up with the Modes vector.

## `void SetMode(int mode)`
Sets the mode of the device.  The mode should be the index in the Modes vector of the mode you wish to set.

## `void SetCustomMode()`
When called, the device should be put into its software-controlled mode.  This differs between devices, but generally devices have a direct control or static effect mode.  Ideally, this mode should not save to the device's internal Flash.  This function sets up a device for software effect control.

## `void UpdateLEDs()`
Update all LEDs based on the device's `colors` vector.

## `void UpdateZoneLEDs(int zone)`
Update all LEDs in the given zone based on the device's `colors` vector.

## `void UpdateSingleLED(int led)`
Update a single LED based on the device's `colors` vector.