# Marling Firmware for Kingroon-KP3 with Touch Screen Support
Contains Marlin 2.x configuration files to run on the Kingroon KP3 with the graphical touch interface.

![](https://github.com/3DP-Tech/Kingroon-KP3/raw/main/Images/marlin-info-screen-vsmall.png)

# Obtaining Marlin Files
The marlin firmware can be obtained from [marlingfw.org](https://marlingfw.org "marlingfw.org") or directly from GitHub at [https://github.com/MarlinFirmware/Marlin](/https://github.com/MarlinFirmware/Marlin "https://github.com/MarlinFirmware/Marlin").

The example marlin configuration files can be obtained from GitHub at [https://github.com/MarlinFirmware/Configurations](https://github.com/MarlinFirmware/Configurations "https://github.com/MarlinFirmware/Configurations")

# Building the Firmware
There are numerous videos available on how to compile the code using Visual Studio Code with the Platform IO and Marlin Autobuild extensions. This process is extremely easy.

Here is one that I like:

[https://www.youtube.com/watch?v=eq_ygvHF29I](https://www.youtube.com/watch?v=eq_ygvHF29I "https://www.youtube.com/watch?v=eq_ygvHF29I")

## Using the Configuration Files
The simplest way to update the firmware is to copy the configuration files from this repository into your Marlin firmware folder after downloading and unzipping the firmware.

Copy the files as follows:
1. Copy **platformio.ini** to the **Marlin** folder
2. Copy **Configuration.h** to the **Marlin/Marlin** folder.
3. Copy **pins_MKS_ROBIN_MINI.h** to the **Marlin/Marlin/src/pins/stm32f1** folder.

## Manual Changes
If you wish to make the changes yourself follow the instructions below.

### Change to Platform.ini File
In the platformio.ini file change the value in the `line default_envs` from `mega2560` to **`mks_robin_mini`**.

### Changes to Configuration.h
1. Download the latest Marlin firmware and unzip the files to a working folder.
2. Copy the the Kingroon KP3 configuration files provided by the Marlin firmware examples in **\Configurations\config\examples\Kingroon\KP3** to the Marlin folder in your working folder making sure to overwrite the existing files.
3. Open the platform.ini file and change **`default_envs = mega2560`** to **`default_envs = mks_robin_mini`**
4. Make the following changes in the **Configuration.h** file
5. Uncomment the line **`#define MKS_ROBIN_TFT24`**
6. Comment the line **`#define TFT_GENERIC`** (add // to the beginning of the line)
7. Comment the line **`#define TFT_CLASSIC_UI`**
8. Uncomment the line **`#define TFT_COLOR_UI`**
9. Uncomment the line **`#define SINGLE_TOUCH_NAVIGATION`**

### Chages to pins_MKS_ROBIN_MINI.h
The changes made to the configuration file will work but the screen will be blank when the printer is on. This is due to an issue with the board file. The following changes are necessary for the screen to be visible. The file can be found in the folder **src/pins/stm32f1**.

1. Rename `#define LCD_USE_DMA_FSM` to **`#define TFT_USE_DMA_FSM`**
2. Rename `#define LCD_RESET_PIN` to **`#define TFT_RESET_PIN`**
3. Rename `#define LCD_BACKLIGHT_PIN` to **`#define TFT_BACKLIGHT_PIN`**

### Changing Stepper Direction
It appears that on some KP3 machines, the stepper motor wiring has been reversed. If after flashing the firmware check the direction of the motors by choosing Motion from the menu and trying to move each axis independently. If the steppers move in the opposite direction, make the changes below to the Configuration.h file and reflash the firmware.

1. Change the value of `#define INVERT_X_DIR` from `false` to **`true`**
2. Change the value of `#define INVERT_Y_DIR` from `false` to **`true`**
3. Change the value of `#define INVERT_Z_DIR` from `true` to **`false`**
4. Change the value of `#define INVERT_E0_DIR` from `false` to **`true`**

I had this experience on my KP3. Even after flashing the original KP3 firmware my steppers ran the wrong direction. I had to update the KP3 firmware configuration.

### Optional Changes

These are additional changes I made to Configuration.h out of personal preference.

1. Uncomment the line **`#define SPEAKER`**
2. Change the value in `#define Z_AFTER_HOMING` from `10` to **`5`**
