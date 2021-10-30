### [Home](https://3dp-tech.github.io/Kingroon-KP3/)

# Add Auto Bed Leveling Support
![](https://github.com/3DP-Tech/Kingroon-KP3/raw/main/Images/screen-205.png)

To add a proximity sensor for auto-bed leveling make the file changes outlined in the table below.

## File Changes

|File|Reference|Comment|
|:-|:-|:-|
|Configuration.h|`#define PROBE_MANUALLY`|Comment this line|
|Configuration.h|`#define FIX_MOUNTED_PROBE`| Uncomment this line|
|Configuration.h|`#define NOZZLE_TO_PROBE_OFFSET`|Change the value to **{ -45, -7, 0 }**. You should measure your mount to determine the correct numbers to use here.|
|Configuration.h|`#define Z_PROBE_FEEDRATE_FAST`|Change the value to **(8\*60)**|
|Configuration.h|`#define MULTIPLE_PROBING`|Change the value to **2**|
|Configuration.h|`#define Z_AFTER_PROBING`Uncomment and change the value and set the value to **5**|
|Configuration.h|`#define Z_PROBE_LOW_POINT`|Change the value to **-1**|
|Configuration.h|`#define Z_PROBE_OFFSET_RANGE_MIN`|Change the value to **-4**|
|Configuration.h|`#define Z_PROBE_OFFSET_RANGE_MAX`|Change the value to **4**|
|Configuration.h|`#define Z_MIN_PROBE_REPEATABILITY_TEST`|Uncomment this line|
|Configuration.h|`#define PROBING_HEATERS_OFF`|Uncomment this line|
|Configuration.h|`#define MIN_SOFTWARE_ENDSTOP_Z`|Comment this ine|
|Configuration.h|`#define AUTO_BED_LEVELING_BILINEAR`|Uncomment this line|
|Configuration.h|`#define MESH_BED_LEVELING`|Comment this ine|
|Configuration.h|`#define RESTORE_LEVELING_AFTER_G28`|Comment this ine|
|Configuration.h|`#define ENABLE_LEVELING_AFTER_G28`|Uncomment this line|
|Configuration.h|`#define GRID_MAX_POINTS_X`|Change the value to **4**|
|Configuration.h|`#define EXTRAPOLATE_BEYOND_GRID`|Uncomment this line|
|Configuration.h|`#define Z_PROBE_END_SCRIPT`|Uncomment this line and change the value to **“G1 X90 Y90 Z10 F12000"**|
|Configuration.h|`#define Z_SAFE_HOMING`|Uncomment this line|
|Configuration.h|`#define HOMING_FEEDRATE_MM_M`|Change the value to **{ (20\*60), (20\*60), (8\*60) }**|
|Configuration_adv.h|`#BABYSTEPPING`|Uncomment this line|
|Configuration_adv.h|`#define BABYSTEP_ALWAYS_AVAILABLE `|Uncomment this line|
|Configuration_adv.h|`#define DOUBLECLICK_FOR_Z_BABYSTEPPING`|Uncomment this line|
|Configuration_adv.h|`#define BABYSTEP_ZPROBE_OFFSET`|Uncomment this line|
|Configuration_adv.h|`#define PROBING_MARGIN_LEFT`|Uncomment this line and change value to **15**|
|Configuration_adv.h|`#define PROBING_MARGIN_RIGHT`|Uncomment this line and change value to **5**|
|Configuration_adv.h|`#define PROBING_MARGIN_FRONT`|Uncomment this line and change value to **20**|
|Configuration_adv.h|`#define PROBING_MARGIN_BACK`|Uncomment this line and change value to **20**|
|Configuration_adv.h|`#define ASSISTED_TRAMMING`|Uncomment this line|
|Configuration_adv.h|`#define TRAMMING_POINT_XY`|Change value to **{ { 50, 50 }, { 130,  50 }, { 130, 130 }, { 50, 130 } }**|
