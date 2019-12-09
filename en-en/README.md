[AWTRIX Pro](assets\awtrix_pro.jpg)

AWTRIX (AWsome maTRIX) is a full-color dot matrix that displays applications ranging from simple time display to Fortnite account statistics.

The technology behind it is based on a few components, so it can be easily replicated by users with less technical skill. The project is based on a matrix with 32 × 8 WS2812B LEDs. The matrix is driven by the WLAN microcontroller ESP8266, which communicates with a Java-based host. Almost any existing system based on Windows, MacOS or Linux can serve as a server.

Of course such a project screams to run with the single board computer Raspberry Pi. The advantage: the server can be built directly into the case and the result is a small but no less fine, self-sufficient system. I provided a printable case on the 3D printing platform Thingiverse and many creative users contributed their own designs. The projects of the very active community can be found [in my forum](https://forum.blueforcer.de/d/22-show-your-awtrix/), including installations in wooden cases, under glass tables and much more. Awtrix 2.0 is the successor of version 1.0 and was created with a lot of input from the community. The free manual for the replica with parts list and software is available online.
Display for everything

The hardware can also be expanded and additional functions added. Brightness sensors for the automatic adjustment of the luminosity, a module for sound output as well as a control via capacitive buttons are mentioned here. After assembling the components and setting up the software, further control takes place via the integrated web server. This communicates with the ESP8266 either via WLAN or via the serial interface (USB or TX/RX). You can also buy your own board in my shop.

Besides simple functions like stopwatch and timer, the project is mainly based on apps, which can be downloaded free of charge from the integrated App Store. These can be weather data, Facebook- or Instagram-Likes or games like Snake or Pong. The latter are controlled via the smartphone or the browser (optionally with connected gamebad). Also the integration into a home automation like FHEM, HassIO or similar is possible. If an app is missing, you can simply write it yourself and submit it for publication.
Thanks to the very well documented API and interfaces for the IoT protocols REST and MQTT any information can be sent to the matrix. Whether temperature, humidity, power consumption or just the song running on Spotify - no problem. And if the local control from the network is still not enough for you, we recommend the connection to the Awtrix cloud, which allows a completely anonymous connection to the IFTTT connection service and its countless receipts.

Another feature helps you to create your own notifications: the Awtrixer. With this powerful integrated tool you can create icons for the Awtrix and convert alternatively existing images of 8×8 pixels automatically. Even animated icons are no problem. Self-created icons are shared with the community. Awtrixer is available in the integrated web interface or as a slimmed-down version on Android and iOS from the store. 


Translated with www.DeepL.com/Translator (free version)