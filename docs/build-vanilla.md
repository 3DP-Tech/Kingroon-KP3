### [Home](https://3dp-tech.github.io/Kingroon-KP3/)

# Building the Firmware from Vanilla Marlin
![](https://github.com/3DP-Tech/Kingroon-KP3/raw/main/Images/screen-205.png)

## Steps
|Step|Description|
|-|-|
|1|Download the Marlin 2.0.9.0 files from [https://github.com/MarlinFirmware/Marlin/archive/refs/tags/2.0.9.zip](https://github.com/MarlinFirmware/Marlin/archive/refs/tags/2.0.9.zip)|
|2|Unzip the Marlin files into a woking folder. Keep track of this folder's location.|
|3|Download the Marlin example configuration files from [https://github.com/MarlinFirmware/Configurations/archive/refs/tags/2.0.9.zip](https://github.com/MarlinFirmware/Configurations/archive/refs/tags/2.0.9.zip)|
|4|Unzip the example configuration files to a working folder. Keep track of this folder's location.|
|5|Download the files from this repository from [https://github.com/3DP-Tech/Kingroon-KP3/archive/refs/tags/M.2090.2.zip](https://github.com/3DP-Tech/Kingroon-KP3/archive/refs/tags/M.2090.2.zip)|
|6|Copy the file **\Configurations\config\examples\Kingroon\KP3\Configuration.h** to the folder **Marlin-2.0.9\Marlin**.|
|7|Copy the file **\Configurations\config\examples\Kingroon\KP3\Configuration_adv.h** to them folder **Marlin-2.0.9\Marlin**.|
|7|Unzip the repository files into a working folder. Keep track of this folder's location.|
|8|Make the changes described in the table below for each of he files.|
|9|Compile the firmware using Visual Studio Code. There are numerous videos available on how to compile the code using Visual Studio Code with the Platform IO and Marlin Autobuild extensions. This process is extremely easy. Here is one that I like: [https://www.youtube.com/watch?v=eq_ygvHF29I](https://www.youtube.com/watch?v=eq_ygvHF29I "https://www.youtube.com/watch?v=eq_ygvHF29I")|
|10|Flash the firmware using the binary file produced as a result of step 9.|

## File Changes

|File|Line Number|Reference|Comment|
|:-|:-:|:-|:-|
|Platform.ini|16|default_envs = mega2560|Change **mega2560** to **mks_robin_mini**|
|Configuration.h|1292|#define INVERT_X_DIR|<sup>1</sup> Change the value from **false** to **true**. If the X stepper motor moves in the opposite direction leave this value the same.|
|Configuration.h|1293|#define INVERT_Y_DIR|<sup>1</sup> Change the value from **false** to **true**. If the Y stepper motor moves in the opposite direction leave this value the same.|
|Configuration.h|1294|#define INVERT_Z_DIR|<sup>1</sup> Change the value from **true** to **false**. If the Z stepper motor moves in the opposite direction leave this value the same.|
|Configuration.h|1302|#define INVERT_E0_DIR|<sup>1</sup> Change the value from **false** to **true**. If the E stepper motor moves in the opposite direction leave this value the same.|
|Configuration.h|2184|#define SPEAKER|Uncomment this line|
|Configuration.h|2184|#define Z_AFTER_HOMING|Change the value from **10** to **5**.|
|Configuration.h|2584|#define MKS_ROBIN_TFT24|Uncomment this line|
|Configuration.h|2648|#define TFT_GENERIC|Comment this line|
|Configuration.h|2673|#define TFT_CLASSIC_UI|Comment this line|
|Configuration.h|2674|#define TFT_COLOR_UI|Uncomment this line|
|Configuration.h|2728|#define SINGLE_TOUCH_NAVIGATION|Uncomment this line|
|pins_MKS_ROBIN_MINI.h|154|#define LCD_USE_DMA_FSM|Change the text **LCD** to **TFT** so the line now reads #define TFT_USE_DMA_FSM|
|pins_MKS_ROBIN_MINI.h|158|#define LCD_RESET_PIN|Change the text **LCD** to **TFT** so the line now reads #define TFT_RESET_PIN. Optionally this can be changed in the comment found on line 147.|
|pins_MKS_ROBIN_MINI.h|159|#define LCD_BACKLIGHT_PIN|Change the text **LCD** to **TFT** so the line now reads #define TFT_BACKLIGHT_PIN|
|Configuration_adv.h|490|#define FAN_KICKSTART_TIME|Uncomment this line|

### NOTE: Changing Stepper Direction
It appears that on some KP3 machines, the stepper motor wiring has been reversed. After flashing the firmware, do not attempt homing until you check the stepper motor direction. This can be done by choosing **Motion** from the menu and trying to move each axis independently. When moving the axis, only make small changes. If any of the steppers move in the opposite direction, change the value of `*INVERT_?_DIR*` from the current value to the opposite value (change to **true** if currently **false**). For example, if the X stepper is running in the opposite direction, change the value of **INVERT_X_DIR** from **true** to **false**. After making the changes, repeat steps 9 and 10. 

