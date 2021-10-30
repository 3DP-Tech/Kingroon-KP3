### [Home](https://3dp-tech.github.io/Kingroon-KP3/)

# Building the Firmware from Vanilla Marlin
![](https://github.com/3DP-Tech/Kingroon-KP3/raw/main/Images/screen-205.png)

## Steps

|Step|Description|
|:-:|-|
|1|Download the Marlin 2.0.9.2 files from [https://github.com/MarlinFirmware/Marlin/archive/refs/tags/2.0.9.2.zip](https://github.com/MarlinFirmware/Marlin/archive/refs/tags/2.0.9.2.zip)|
|2|Unzip the Marlin files into a woking folder. Keep track of this folder's location.|
|3|Download the Marlin example configuration files from [https://github.com/MarlinFirmware/Configurations/archive/refs/tags/2.0.9.2.zip](https://github.com/MarlinFirmware/Configurations/archive/refs/tags/2.0.9.2.zip)|
|4|Unzip the example configuration files to a working folder. Keep track of this folder's location.|
|5|Copy the files from **Marlin-Configurations/Config/Examples/Kingroon/KP3** to **Marlin-2.0.9.2/Marlin**.|
|6|Make the changes described in the table below for each of he files.|
|7|Compile the firmware using Visual Studio Code. There are numerous videos available on how to compile the code using Visual Studio Code with the Platform IO and Marlin Autobuild extensions. This process is extremely easy. Here is one that I like: [https://www.youtube.com/watch?v=eq_ygvHF29I](https://www.youtube.com/watch?v=eq_ygvHF29I "https://www.youtube.com/watch?v=eq_ygvHF29I")|
|8|Flash the firmware using the binary file produced as a result of step 7.|

## File Changes

|File|Reference|Comment|
|:-|:-|:-|
|Platform.ini|default_envs = mega2560|Change **mega2560** to **mks_robin_mini**|
|Configuration.h|`#define SPEAKER`|Uncomment this line|
|Configuration.h|`#define MKS_ROBIN_TFT24`|Uncomment this line|
|Configuration.h|`#define TFT_GENERIC`|Comment this line|
|Configuration.h|`#define TFT_CLASSIC_UI`|Comment this line|
|Configuration.h|`#define TFT_COLOR_UI`|Uncomment this line|
|Configuration.h|`#define SINGLE_TOUCH_NAVIGATION`|Uncomment this line|
|Configuration.h|`#define PID_EDIT_MENU1`|Uncomment this line|
|Configuration.h|`#define PID_AUTOTUNE_MENU`|Uncomment this line|
|Configuration.h|`#define MESH_EDIT_MENU`|Uncomment this line|
|Configuration.h|`#define PREHEAT_1_TEMP_HOTEND 200`|Change value from `200` to `207`|
|Configuration.h|`#define INDIVIDUAL_AXIS_HOMING_SUBMENU`|Uncomment this line|
|pins_MKS_ROBIN_MINI.h|`#define LCD_USE_DMA_FSM`|Change the text **LCD** to **TFT** so the line now reads `#define TFT_USE_DMA_FSM`|
|pins_MKS_ROBIN_MINI.h|`#define LCD_RESET_PIN`|Change the text **LCD** to **TFT** so the line now reads `#define TFT_RESET_PIN`. Optionally this can be changed in the comment found on line 147.|
|pins_MKS_ROBIN_MINI.h|`#define LCD_BACKLIGHT_PIN`|Change the text **LCD** to **TFT** so the line now reads `#define TFT_BACKLIGHT_PIN`|
|Configuration_adv.h|`#define FAN_KICKSTART_TIME`|Uncomment this line|
|Configuration_adv.h|`#define ASSISTED_TRAMMING_WIZARD`|Uncomment this line|
|Configuration_adv.h|`#define LONG_FILENAME_HOST_SUPPORT`|Uncomment this line|


### NOTE: Changing Stepper Direction
It appears that on some KP3 machines, the stepper motor wiring has been reversed. After flashing the firmware, do not attempt homing until you check the stepper motor direction. This can be done by choosing **Motion** from the menu and trying to move each axis independently. When moving the axis, only make small changes. If any of the steppers move in the opposite direction, change the value of `INVERT_?_DIR` from the current value to the opposite value (change to **true** if currently **false**).

|File|Reference|Comment|
|:-|:-|:-|
|Configuration.h|`#define INVERT_X_DIR`|Change the value from **false** to **true**. If the X stepper motor moves in the opposite direction leave this value the same.|
|Configuration.h|`#define INVERT_Y_DIR`|Change the value from **false** to **true**. If the Y stepper motor moves in the opposite direction leave this value the same.|
|Configuration.h|`#define INVERT_Z_DIR`|Change the value from **true** to **false**. If the Z stepper motor moves in the opposite direction leave this value the same.|
|Configuration.h|`#define INVERT_E0_DIR`|Change the value from **false** to **true**. If the E stepper motor moves in the opposite direction leave this value the same.|