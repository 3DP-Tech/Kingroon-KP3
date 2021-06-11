# Marling Firmware for Kingroon-KP3 with Touch Screen Support
Contains **Marlin 2.0.8.2** configuration files to run on the Kingroon KP3 with the graphical touch interface.

![](https://github.com/3DP-Tech/Kingroon-KP3/raw/main/Images/marlin-info-screen-vsmall.png)

# Precompiled Firmware
You will find precompiled versions of the firmware ready for an OEM KP3. If you made any modifications to your printer, such as adding a auto bed leveler, you will need to compile the firmware.

The precompiled firmware is located in the **bin** folder.

# Building the Firmware
There are numerous videos available on how to compile the code using Visual Studio Code with the Platform IO and Marlin Autobuild extensions. This process is extremely easy.

Here is one that I like:

[https://www.youtube.com/watch?v=eq_ygvHF29I](https://www.youtube.com/watch?v=eq_ygvHF29I "https://www.youtube.com/watch?v=eq_ygvHF29I")

## Obtaining Marlin Files
The marlin firmware can be obtained from [marlingfw.org](https://marlingfw.org "marlingfw.org") or directly from GitHub at [https://github.com/MarlinFirmware/Marlin](/https://github.com/MarlinFirmware/Marlin "https://github.com/MarlinFirmware/Marlin").

The example Marlin configuration files can be obtained from GitHub at [https://github.com/MarlinFirmware/Configurations](https://github.com/MarlinFirmware/Configurations "https://github.com/MarlinFirmware/Configurations")

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
### Change to Platform.ini File
1. Open the **platform.ini** file and change **`default_envs = mega2560`** to **`default_envs = mks_robin_mini`**
### Changes to Configuration.h
1. Uncomment the line **`#define MKS_ROBIN_TFT24`**
2. Comment the line **`#define TFT_GENERIC`** (add // to the beginning of the line)
3. Comment the line **`#define TFT_CLASSIC_UI`**
4. Uncomment the line **`#define TFT_COLOR_UI`**
5. Uncomment the line **`#define SINGLE_TOUCH_NAVIGATION`**

### Changes to pins_MKS_ROBIN_MINI.h
The changes made to the configuration file will work but the screen will be blank when the printer is on. This is due to an issue with the board file. The following changes are necessary for the screen to be visible. The file can be found in the folder **src/pins/stm32f1**.

1. Rename `#define LCD_USE_DMA_FSM` to **`#define TFT_USE_DMA_FSM`**
2. Rename `#define LCD_RESET_PIN` to **`#define TFT_RESET_PIN`**
3. Rename `#define LCD_BACKLIGHT_PIN` to **`#define TFT_BACKLIGHT_PIN`**

### Changing Stepper Direction
It appears that on some KP3 machines, the stepper motor wiring has been reversed. If after flashing the firmware check the direction of the motors by choosing Motion from the menu and trying to move each axis independently. If the steppers move in the opposite direction, make the changes below to the **Configuration.h** file and reflash the firmware.

1. Change the value of `#define INVERT_X_DIR` from `false` to **`true`**
2. Change the value of `#define INVERT_Y_DIR` from `false` to **`true`**
3. Change the value of `#define INVERT_Z_DIR` from `true` to **`false`**
4. Change the value of `#define INVERT_E0_DIR` from `false` to **`true`**

I had this similar experience on my KP3 after flashing the original KP3 firmware. My steppers ran the wrong direction. I had to update the OEM KP3 firmware configuration to reverse the motors.

### Optional Changes

These are additional changes I made to **Configuration.h** out of personal preference.

1. Uncomment the line **`#define SPEAKER`**
2. Change the value in `#define Z_AFTER_HOMING` from `10` to **`5`**

These are additional changes I made to **Configuration_adv.h** out of personal preference.

1. Uncomment **`#define FAN_KICKSTART_TIME 100`**
