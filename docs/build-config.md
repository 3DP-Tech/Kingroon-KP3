### [Home](https://3dp-tech.github.io/Kingroon-KP3/)

# Building the Firmware with Configuration Files
![](https://github.com/3DP-Tech/Kingroon-KP3/raw/main/Images/screen-205.png)

|Step|Description|
|-|-|
|1|Download the Marlin 2.0.9.0 files from [https://github.com/MarlinFirmware/Marlin/archive/refs/tags/2.0.9.zip](https://github.com/MarlinFirmware/Marlin/archive/refs/tags/2.0.9.zip)|
|2|Unzip the Marlin files into a woking folder. Keep track of this folder's location.|
|3|Download the Marlin example configuration files from [https://github.com/MarlinFirmware/Configurations/archive/refs/tags/2.0.9.zip](https://github.com/MarlinFirmware/Configurations/archive/refs/tags/2.0.9.zip)|
|4|Unzip the example configuration files to a working folder. Keep track of this folder's location.|
|5|Download the files from this repository from [https://github.com/3DP-Tech/Kingroon-KP3/archive/refs/tags/M.2090.2.zip](https://github.com/3DP-Tech/Kingroon-KP3/archive/refs/tags/M.2090.2.zip)|
|6|Copy the **Configuration.h** file from **\Configurations\config\examples\Kingroon\KP3** to the **Marlin-2.0.9\Marlin** folder.|
|7|Copy the **Configuration_adv.h** file from **\Configurations\config\examples\Kingroon\KP3** to the **Marlin-2.0.9\Marlin** folder.|
|7|Unzip the repository files into a working folder. Keep track of this folder's location.|
|8|Copy the file **platformio.ini** from this repository to the **Marlin-2.0.9** folder.|
|9|Copy the file **Configuration.h** from this repository to the **Marlin-2.0.9\Marlin** folder.|
|10|Copy the file **Configuration_adv.h** from this repository to the **Marlin-2.0.9\Marlin** folder.|
|11|Copy the file **pins_MKS_ROBIN_MINI.h** from this repository to the **Marlin-2.0.9\Marlin\src\pins\stm32f1** folder.|
|12|Compile the firmware using Visual Studio Code. There are numerous videos available on how to compile the code using Visual Studio Code with the Platform IO and Marlin Autobuild extensions. This process is extremely easy. Here is one that I like: [https://www.youtube.com/watch?v=eq_ygvHF29I](https://www.youtube.com/watch?v=eq_ygvHF29I "https://www.youtube.com/watch?v=eq_ygvHF29I")|

### <sup>1</sup> Changing Stepper Direction
It appears that on some KP3 machines, the stepper motor wiring has been reversed. After flashing the firmware, do not attempt homing until you check the stepper motor direction. This can be done by choosing Motion from the menu and trying to move each axis independently. If the steppers move in the opposite direction, change the values back to their original values and reflash the firmware.

