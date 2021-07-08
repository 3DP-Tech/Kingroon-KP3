# Marling Firmware for Kingroon-KP3 with Touch Screen Support
This repository contains **Marlin 2.0.9.0** configuration files to run on the Kingroon KP3 with the graphical touch interface as shown below.

![](https://github.com/3DP-Tech/Kingroon-KP3/raw/main/Images/screen-205.png)

### [Home](https://3dp-tech.github.io/Kingroon-KP3/)

# Building the Firmware with Configuration Files
There are numerous videos available on how to compile the code using Visual Studio Code with the Platform IO and Marlin Autobuild extensions. This process is extremely easy.

Here is one that I like:

[https://www.youtube.com/watch?v=eq_ygvHF29I](https://www.youtube.com/watch?v=eq_ygvHF29I "https://www.youtube.com/watch?v=eq_ygvHF29I")

## Obtaining Marlin Files
The marlin firmware can be obtained from [marlingfw.org](https://marlingfw.org "marlingfw.org") or directly from GitHub at [https://github.com/MarlinFirmware/Marlin/releases/tag/2.0.9](https://github.com/MarlinFirmware/Marlin/releases/tag/2.0.9).

The example Marlin configuration files can be obtained from GitHub at [https://github.com/MarlinFirmware/Configurations/tree/release-2.0.9/config/examples/Kingroon/KP3](https://github.com/MarlinFirmware/Configurations/tree/release-2.0.9/config/examples/Kingroon/KP3")

## Using these Configuration Files
The simplest way to update the firmware is to copy the configuration files from this repository into your Marlin firmware folder after downloading and unzipping the firmware.

Copy the files as follows:
1. Copy **platformio.ini** to the **Marlin** folder
2. Copy **Configuration.h** to the **Marlin/Marlin** folder.
3. Copy **Configuration_adv.h** to the **Marlin/Marlin** folder.
4. Copy **pins_MKS_ROBIN_MINI.h** to the **Marlin/Marlin/src/pins/stm32f1** folder.

## or, Make the Changes Directly
If you wish to make the changes yourself follow the instructions below.
### Getting Started
1. Download the latest Marlin firmware and unzip the files to a working folder.
2. Download the example configuration files and unzip them into a working folder.
3. Copy the the Kingroon KP3 configuration files provided by the Marlin firmware examples in **\Configurations\config\examples\Kingroon\KP3** to the Marlin folder in your working folder making sure to overwrite the existing files.
4. Edit the files listed below with each of the corresponding changes.

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

### <sup>1</sup> Changing Stepper Direction
It appears that on some KP3 machines, the stepper motor wiring has been reversed. After flashing the firmware, do not attempt homing until you check the stepper motor direction. This can be done by choosing Motion from the menu and trying to move each axis independently. If the steppers move in the opposite direction, change the values back to their original values and reflash the firmware.

