### [Home](https://3dp-tech.github.io/Kingroon-KP3/)

# Building the Firmware from Configuration Files
![](https://github.com/3DP-Tech/Kingroon-KP3/raw/main/Images/screen-205.png)

|Step|Description|
|:-:|-|
|1|Download the Marlin 2.0.9.0 files from [https://github.com/MarlinFirmware/Marlin/archive/refs/tags/2.0.9.zip](https://github.com/MarlinFirmware/Marlin/archive/refs/tags/2.0.9.zip)|
|2|Unzip the Marlin files into a woking folder. Keep track of this folder's location.|
|3|Download the files the repository from [https://github.com/3DP-Tech/Kingroon-KP3/archive/refs/tags/M.2090.2.zip](https://github.com/3DP-Tech/Kingroon-KP3/archive/refs/tags/M.2090.2.zip)|
|4|Unzip the repository files into a working folder. Keep track of this folder's location.|
|5|Copy the file **Kingroon-KP3-M.2090.2\Configuration\platformio.ini** to the folder **Marlin-2.0.9**.|
|6|Copy the file **Kingroon-KP3-M.2090.2\Configuration\Configuration.h** to the folder **Marlin-2.0.9\Marlin**.|
|7|Copy the file **Kingroon-KP3-M.2090.2\Configuration\Configuration_adv.h** to the folder **Marlin-2.0.9\Marlin**.|
|8|Copy the file **Kingroon-KP3-M.2090.2\Configuration\pins_MKS_ROBIN_MINI.h** to the folder **Marlin-2.0.9\Marlin\src\pins\stm32f1**.|
|9|Compile the firmware using Visual Studio Code. There are numerous videos available on how to compile the code using Visual Studio Code with the Platform IO and Marlin Autobuild extensions. This process is extremely easy. Here is one that I like: [https://www.youtube.com/watch?v=eq_ygvHF29I](https://www.youtube.com/watch?v=eq_ygvHF29I "https://www.youtube.com/watch?v=eq_ygvHF29I")|

### NOTE: Checking Stepper Direction
It appears that on some KP3 machines, the stepper motor wiring has been reversed. After flashing the firmware, do not attempt homing until you check the stepper motor direction. This can be done by choosing **Motion** from the menu and trying to move each axis independently. When moving the axis, only make small changes. If the steppers move in the opposite direction, repeat steps 6 and 9 using the file **Kingroon-KP3-M.2090.2\Configuration\Configuration.h.REVERSED**. Rename this file by removing the **.REVERSED** extension.

