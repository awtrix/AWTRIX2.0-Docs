![AWTRIX Pro](../assets/family.jpg)

### AWTRIX
(**AW**some ma**TRIX**) is a full color dot matrix that displays applications from simple time display to Fortnite account statistics.

The technology behind it is based on few components, so it can be easily replicated by users with less technical skills. The project. The matrix (32 × 8 WS2812B LEDs) is driven by the ESP8266 WLAN microcontroller, which communicates with a Java-based host. Almost any existing system based on Windows, MacOS or Linux can serve as a host.

Of course, such a project screams to run with the single-board computer Raspberry Pi. The advantage: the server can be built directly into the case and the result is a small but no less fine, self-sufficient system. I provided a printable case on the 3D printing platform Thingiverse and many creative users contributed their own designs. The projects of this very active community can be seen [**on discrod**](https://discord.com/invite/EhzeZDyspzs), including installations in wooden cabinets, under glass tables and much more. Awtrix 2.0 is the successor of version 1.0 and was created with a lot of input from the community.

### Display for everything
The hardware can also be expanded and additional functions added. Brightness sensors for automatic adjustment of the luminosity, a module for sound output and control via capacitive buttons are just a few examples. After assembling the components and setting up the software, further control is carried out via the integrated web server. This communicates with the ESP8266 either via WLAN or via the serial interface (USB or TX/RX). A separate board can also be purchased in the [**Shop**](https://blueforcer.de/shop/).

In addition to simple functions such as stopwatch and timer, the project is mainly based on apps that are available for free download in the integrated App Store. These can be weather data, Facebook or Instagram Likes or even games like Snake or Pong. The latter are controlled via the smartphone or the browser (optionally with a connected gamepad). It is also possible to integrate them into a home automation system like FHEM, Home Assistant or similar. If an app is missing, you can simply write it yourself and submit it for publication.
Thanks to the very well documented API and interfaces for the HTTP and MQTT protocols, any information can be sent to the matrix. Whether temperature, humidity, power consumption or just the song currently running on Spotify - no problem. And if local control from the network is not enough, we recommend connecting to the Awtrix Cloud, which **among other things** allows a completely anonymous connection to the IFTTT link service and its countless receipts.

For the creation of own notifications, another feature helps: the Awtrixer. With this powerful integrated tool you can create icons for the Awtrix and can alternatively convert existing 8×8 pixel images automatically. Even animated icons are no problem. Self-created icons are shared with the community. Awtrixer is available in the host web interface

**The most important functions of AWTRIX in brief**

- Platform independent
- API interfaces for MQTT and HTTP
- Display notifications from the Smarthome or other external services
- Access to the icon database
- Integrated Appstore
- Adaptation of the app loop
- Adjusting the color correction for the matrix
- AWTRIX Arcade for smaller games on the matrix
- Update of the controller and host via the web interface
- Stopwatch
- Timer

**Premium functions**
- Fritz!Box CallMonitor
- Control your AWTRIX via the AWTRIX Cloud
- Pushover Client
- Alarm clock
- Sleep mode
