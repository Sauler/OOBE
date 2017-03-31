## Out of Box Experience Script
---
### Usage
``` .\OOBE.ps1 ```

### Driver repository
Directory on network share (not necessary) that contains all drivers for this script. 
Directory structure:
- Root
  * HP EliteBook 8460p
    * Driver1
      * OOBE_Install.ini 
    * Driver2
      * OOBE_Install.ini 
    * Driver3
      * OOBE_Install.ini 
  * HP ProBook 6460b
    * Driver1
      * OOBE_Install.ini 
    * Driver2
      * OOBE_Install.ini
    * Driver3
      * OOBE_Install.ini 
  * etc
 
### OOBE_Install.ini
Config file that describes how to install specified driver. File structure:
```
[Installation]
; File to execute
Exec=pnputil.exe
; Parameters
Args=-i -a accelerometer.inf
```

### Supported computers and drivers
* **Computers:**
These are all folders in the main directory
* **Drivers:**
These are all folders in the computer directory that contain the OOBE_Install.ini file

### Notes
* **ComputerName** parameter is only for debugging purposes. Script can be started on local computer.
* Change **$DriversRepositoryPath** variable before start.
* At this point BIOS updates is not supported
* The directory name of the computer must be the same as the model given at the beginning of the script
