This folder contains the configuration files for my Kingroon KP3 configuration:

1. Proximity sensor added for auto bed leveling
2. Swapped the TR8x8 Z axis lead screw with a TR8x2
3. Swapped out the Z axis aluminum extrusion wtih a 400 mm version resulting in a maximum Z height of 240 mm

### Changes for Z
|File|Line Number|Reference|Comment|
|:-|:-:|:-|:-|
|Configuration.h|899|Changed 400 to 1600 in `#define DEFAULT_AXIS_STEPS_PER_UNIT`||
|Configuration.h|906|Changed 5 to 10 in `#define DEFAULT_MAX_FEEDRATE`||
|Configuration.h|919|Changed 100 to 400 in `#define DEFAULT_MAX_ACCELERATION`||
|Configuration.h|950|Changed 0.3 to 1.2 in `#define DEFAULT_ZJERK`||
|Configuration.h|1349|Set value `#define Z_MAX_POS` to 240||