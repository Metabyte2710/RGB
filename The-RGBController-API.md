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