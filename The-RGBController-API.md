OpenRGB uses an internal API called RGBController to standardize the interface to RGB devices from multiple vendors and classes.  This API uses vectors to describe each device.

Devices contain modes, zones, and LEDs.

Modes represent internal effects and have a name field that describes the effect.  The mode's index in the vector is its ID.

Zones describe a group of LEDs.  Zones have one of three types - single, linear, and matrix.  Single zones are zones which only have one controllable LED channel and are thus all one color.  Linear zones represent rows or strips of LEDs where each LED can be its own color.  Matrix zones represent grids of LEDs.  Each zone contains a zone map which is a vector of vectors.  This represents rows and columns, with the data points in the vector being LED indices.

LEDs each have a name and their index in the LEDs vector matches with the index used in the zone map.