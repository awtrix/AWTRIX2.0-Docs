# AWTRIX 2.0



After a break of more than half a year the development of ***AWTRIX 2.0*** started.
The reason for a complete version jump is relatively simple:
The ESP8266 is very inflexible for such applications. This is partly due to the relatively low memory and RAM. It was simply not possible to add more functions and at the same time guarantee the stability or to keep features like OTA.

***AWTRIX 2.0*** is therefore built in 2 parts:
The ESP8266 as Matrix Driver (AWTRIXController)
And a Java capable host like Windows, MacOS, RaspberryPi, etc. The host takes over the complete logic while the ESP takes over the commands and displays them stubbornly.

***AWTRIX 2.0*** is based on Java 8 and has been trimmed for resource-saving functionality.
(5% CPU Load on a Rpi ZeroW).

Due to the inexhaustible resources I was able to make ***AWTRIX 2.0*** a great user experience. It starts with the simple setup and installation and ends with the intuitive operation. ***AWTRIX 2.0*** is the result of one month of hard work and very good feedback from the community.

Features of ***AWTRIX 2.0***:
- Platform independent
- Control via web interface with responsive Design
- Apps can be added through the integrated Appstore.
- Felxible App management
- Support for Community Apps
- API interfaces like MQTT and REST
