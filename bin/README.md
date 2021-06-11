This folder contains the Marlin 2.x compiled firmware for an OEM Kingroon KP3.

To update your firmware, turn off your printer, copy the **`ROBIN_MINI.BIN`** file to a MicroSD card, insert the card into the printer and then turn it on.

If the Micro SD card that came with your printer contains a file named **`ROBIN_MINI.CUR`**, this file contains the OEM firmware and can be restored to the printer at any time. It is a good idea to make a backup of this file. To restore the original firmware, rename the file to **`ROBIN_MINI.BIN`** and copy it to your Micro SD card. Insert the card into the printer while it is turned off, and then turn the printer on. The firmware will update and when done, be restored to the original firmware.

If after applying the firmware you find your motors run in reverse, use **`ROBIN_MINI.BIN.reversed`**instead of **`ROBIN_MINI.BIN`** and remove the `.REVERSED` extension.