### [Home](https://3dp-tech.github.io/Kingroon-KP3/)

# Add Auto Bed Leveling
![](https://github.com/3DP-Tech/Kingroon-KP3/raw/main/Images/screen-205.png)

To add a proximity sensor for auto-bed leveling make the file changes outlined in the table below.

## File Changes

|File|Line Number|Reference|Comment|
|:-|:-:|:-|:-|
|Configuration.h|1036|Comment line #define PROBE_MANUALLY||
|Configuration.h|1042|Uncomment #define FIX_MOUNTED_PROBE||
|Configuration.h|1151|Change value of #define NOZZLE_TO_PROBE_OFFSET to { -45, -7, 0 }|Measured from mount.|
|Configuration.h|1161|Change value of #define Z_PROBE_FEEDRATE_FAST to (8*60)||
|Configuration.h|1202|Change the value of #define MULTIPLE_PROBING to 2||
|Configuration.h|1219|Change value of #define Z_CLEARANCE_DEPLOY_PROBE to 5||
|Configuration.h|1220|Change value of #define Z_CLEARANCE_BETWEEN_PROBES to 3||
|Configuration.h|1221|Change value of #define Z_CLEARANCE_MULTI_PROBE to 3||
|Configuration.h|1222|Uncomment #define Z_AFTER_PROBING, set value to 5|Already uncomment if using Marlin from this repository.|
|Configuration.h|1224|Change value of #define Z_PROBE_LOW_POINT to -3|Already set if using Marlin from this repository.|
|Configuration.h|1227|Change value if #define Z_PROBE_OFFSET_RANGE_MIN to -4||
|Configuration.h|1228|Change value of #define Z_PROBE_OFFSET_RANGE_MAX to 4||
|Configuration.h|1231|Uncomment #define Z_MIN_PROBE_REPEATABILITY_TEST||
|Configuration.h|1246|Uncomment #define PROBING_HEATERS_OFF||
|Configuration.h|1323|Uncomment #define Z_HOMING_HEIGHT|Already uncomment if using Marlin from this repository.|
|Configuration.h|1371|Comment the line #define MIN_SOFTWARE_ENDSTOP_Z||
|Configuration.h|1507|Uncomment #define AUTO_BED_LEVELING_BILINEAR||
|Configuration.h|1509|Comment the line #define MESH_BED_LEVELING||
|Configuration.h|1516|Comment the line #define RESTORE_LEVELING_AFTER_G28||
|Configuration.h|1546|Change the value of #define DEFAULT_LEVELING_FADE_HEIGHT to 4||
|Configuration.h|1574|Change the value of #define GRID_MAX_POINTS_X to 4||
|Configuration.h|1584|Uncomment #define EXTRAPOLATE_BEYOND_GRID||
|Configuration.h|1643|Uncomment #define MESH_EDIT_MENU||
|Configuration.h|1685|Uncomment and change the value of #define Z_PROBE_END_SCRIPT to “G1 X90 Y90 Z10 F12000"||
|Configuration.h|1707|Uncomment #define Z_SAFE_HOMING||
|Configuration.h|1715|Change the value of define HOMING_FEEDRATE_MM_M to { (50*60), (50*60), (8*60) }||
|Configuration_adv.h|1827|Uncomment BABYSTEPPING||
|Configuration_adv.h|1838|Uncomment  #define DOUBLECLICK_FOR_Z_BABYSTEPPING||
|Configuration_adv.h|1840|Change #define DOUBLECLICK_MAX_INTERVAL value to 2000||
|Configuration_adv.h|1850|Uncomment #define BABYSTEP_ZPROBE_OFFSET||
|Configuration_adv.h|1917|Uncomment #define PROBING_MARGIN_LEFT and change value to 15||
|Configuration_adv.h|1918|Uncomment #define PROBING_MARGIN_RIGHT and change value to 0||
|Configuration_adv.h|1919|Uncomment #define PROBING_MARGIN_FRONT and change value to 10||
|Configuration_adv.h|1920|Uncomment #define PROBING_MARGIN_BACK and change value to 10||
