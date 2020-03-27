!> **With the current controller firmware it is not necessary to change a config file**.  
All settings can now be easily adjusted via hotspot.
This manual describes how to flash a finished .bin file to the ESP8266. Compiling the source code (as previously required) is not described here.

## Flashing

### Flashing with Windows


**1.** Download the Flashing Tool [here](https://blueforcer.de/downloads/ESP8266Flasher.exe)
   
**2.** Download the latest firmware [here](https://blueforcer.de/awtrix/stable/firmware.bin).

**3.** Start the **ESP8266Flasher.exe** and open the firmware in the tab "Config" (click gear wheel to select the firmware)

**4** Go back to the tab "Operation" and set the correct Com-Port if it was not detected automatically.
   
**5** Click on "Flash" and wait until the process is finished and a green check mark appears in the lower left corner.
   
**6.** Restart the controller.

  <div align=center>
  <img width="400" src="..\assets\firmware\flashingTool.jpg"/>
    <img width="400" src="..\assets\firmware\flashingTool2.jpg"/>
  </div>

### Flashing under Linux & MacOS

The ESPTool can be used for this purpose
``` BASH
 git clone https://github.com/themadinventor/esptool.git
``` 
If you do not have git, you can download it with the appropriate command:  
[Installing git on different distributions](http://git-scm.com/download/linux)

We also need Python on our system to run this script with the serial package (it should already be installed, but just in case)

In the terminal, we change the current folder to the path of the esptool folder and enter this command to download the firmware:

``` BASH
sudo wget -h https://blueforcer.de/awtrix/stable/firmware.bin
```
The flash process is then started

``` BASH
sudo python esptool.py --port /dev/ttyUSB0 write_flash 0x00000 firmware.bin
``` 
Note that **/dev/ttyUSB0** may change depending on the UART you use and the Linux distribution you choose.

If after a few seconds similar outputs are read
``` BASH
Connecting....
Erasing flash..... 
Writing at 0x0000000000... (0 %)
``` 
Then everything is fine...
If it does not appear after a few seconds, you may have a problem connecting ESP8266 to the UART.


## First Start
  <div align=center>
  <img width="400" src="..\assets\firmware\wifiSearch.gif"/>
  </div>

For a few seconds the controller will now search for a known WiFi network. 
<br>
<br>

  <div align=center>
  <img width="400" src="..\assets\firmware\hotspot.gif"/>
  </div>

If no Wifi connection is configured yet, the text "Hotspot" will appear on the matrix. As the name says, the controller will now open a WLAN hotspot. With any WLAN device the controller can now be configured via the hotspot.
1. connect to the WLAN with the SSID "**AWTRIX Controller**".
2. the WLAN password is "**awtrixxx**".
3. if a web page does not open automatically, the settings page can be navigated to under the IP "**172.217.28.1** using any browser. This page looks like the following:

<div align=center>
<img width="200" src="..\assets\firmware\hotspotConfig1.jpg"/>
<img width="200" src="..\assets\firmware\hotspotConfig2.jpg"/>
</div>


4. by clicking on "Conigure WiFi" (left picture) you will be taken to the actual settings page (right picture).
   
5. **SSID** and **password** of your WLAN must be entered in the fields provided. 
   
!> **The controller needs a WLAN - otherwise it will not start. This is used as fallback connection method and automatic update via the host**

6. enter the **host IP** This is the IP address of the instrument on which the host software is running e.g. a Raspberry
   
7. if your matrix only shows strange pixels, the arrangement of the LEDs on the matrix is different. You can fix this by adjusting the control with **MatrixType2
<br>
<br>


## Known problems

- If other problems occur you can try to reset your Wemos. This will delete all your saved information and you can set it up again via the hotspot.
  Proceed as follows:
  - Reset the ESP.
  - Wait 3-4s
  - Reset the ESP again
  - The matrix now shows **RESET** in red  

<br>
  <div align=center>
  <img width="400" src="..\assets\firmware\reset.jpg"/>
  </div>