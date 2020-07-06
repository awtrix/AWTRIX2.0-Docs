Various settings for the host and matrix can be made via the "Settings" sidebar. In the following all possibilities are explained:

## Host

### Basic Settings

**Boot animation**  
Displays a boot animation when the matrix is first connected.
This uses the Draw API. The bootanimation.json is located in the folder "config" and can be changed as desired.

**Color Switch**  
Another form of alternate animation. Here a colored bar deletes the active app from the matrix.

**Uppercase Letters**  
This function converts all texts to upper case.
  
**Rainbow Text**  
This will fade every text in rainbow colors. Custom settings will be ignored. You can change the speed via the rainbowdivider
  
**Remove Accents**  
Some languages use accents that the matrix cannot display. This function replaces them with readable characters.

**Verbose Log**  
This function extends the Log. This is especially useful for bug reports.

**Analytics**  
This function allows the IP address to be transferred to the AWTRIX cloud server. No further settings or information is sent.
Using this IP address, I can see which country AWTRIX is running in and how many in total. This information is not passed on to third parties and is not stored.
The information is temporarily stored during the runtime of my server, and is completely deleted as soon as an AWTRIX host is offline for more than 10 minutes.  
P.S. Every normal web page request, e-mail transmission and icon downloads always leave the IP address on the respective server. With AWTRIX, however, you can decide whether I may use this for evaluation purposes. This helps me to see how widespread my project is, so I can adapt AWTRIX to specific countries and it motivates me to offer you more and more functions.

**Textcolor**  
Here you can set the global text color.

**Switch Animation**  
This changes the switch animation between the apps.

**Language**
Here you can change the language of the webinterface. This will not affect apps or API

**Brightness**  
Here the brightness of the matrix is defined (0-100%). Please note: The brighter the matrix, the more power is consumed and the warmer it becomes.

!> The matrix can consume up to 75 watts at highest brightness level and completely white pixels! To avoid excessive heat development, a **maximum** brightness of 75% is recommended.

**App Duration**  
Defines the time how long an app is displayed before switching to the next one.

**Scroll speed**  
This value indicates after how many milliseconds the text will be moved by one Y-position. A lower value lets the text scroll faster, but also increases CPU usage.

**Update interval**  
This value specifies after how many seconds all apps update their data.

**Volume**  
Adjusts the volume of the connected DFPlayer.

**Timezone Offset (UTC)**  
This sets the difference to the UTC time zone. Enter 0 to use the local time from your running operating system.

### Communication

#### Web server

**port**  
changes the port via which the AWTRIX web interface is called

**Enable Login**  
Activates the login mask of the AWTRIX web interface

**Login Password**  
The password for the login screen (default: **awtrix**)

#### MQTT

Activates the MQTT Client. Further settings are self-explanatory.

### Matrix connection

You can operate the Matrix either via WiFi or USB. If you have a weak or overloaded WiFi, please try to connect the Matrix via USB to avoid jerking.

!> Selecting ttyAMA0 can cause problems with RaspberryPi 3 and higher because this port is occupied by Bluetooth. Use ttyS0 instead!

### Premium

[See here](de-en/premium.md)

## Matrix

### LED Settings

**Color Correction**  
It may happen that the matrices show a slight colour cast in white light. This is due to differences in quality and the calibration of the LEDs.
With the colour correction you can adjust the colours of the LEDs to produce a clear white. **OvercastSky** works best with a red cast and produces a bright white

**Auto Brightness**  
If you have connected an LDR (Light Dependent Resistor) to the matrix, you can set the automatic brightness control here. If you have installed the recommended components, you do not need to change the values.

- **Resistor**
  Indicates the series resistor used (1000ohm is standard here)
- **Minimum Lux**
  The minimum brightness value that can be measured by the LDR
- **maximum lux**
  The maximum brightness value that can be measured by the LDR
- **Minimum Brightness**
  The minimum brightness that is possible after the calculation (0-100%)
- **Maximum Brightness**
  The maximum brightness that is possible after the calculation (0-100%)
