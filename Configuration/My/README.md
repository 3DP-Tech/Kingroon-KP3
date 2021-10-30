This folder contains the configuration files for my Kingroon KP3 configuration:

1. Proximity sensor added for auto bed leveling
2. Swapped the TR8x8 Z axis lead screw with a TR8x2
3. Swapped out the Z axis aluminum extrusion wtih a 400 mm version resulting in a maximum Z height of 235 mm

## My Configuratio Changes
### Auto Bed Leveling
My KP3 has auto bed leveling with a proximiy sensor.
[See ABL Changes](https://github.com/3DP-Tech/Kingroon-KP3/blob/main/docs/abl.md)

### Changes for Z
|File|Reference|Comment|
|:-|:-|:-|
|Configuration.h|`#define DEFAULT_AXIS_STEPS_PER_UNIT`|Changed **400** to **1600**|
|Configuration.h|`#define DEFAULT_MAX_FEEDRATE`|Changed **5** to **10**|
|Configuration.h|`#define DEFAULT_MAX_ACCELERATION`|Changed **100** to **400**|
|Configuration.h|`#define DEFAULT_ZJERK`|Changed **0.3** to **1.2**|
|Configuration.h|`#define Z_MAX_POS`|Set value to **235**|