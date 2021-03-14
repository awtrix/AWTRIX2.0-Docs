![](..\assets\awtrix.jpeg)

# Parts list
## General note
The availability of the articles changes daily. Therefore it may happen that some articles are no longer available under the link. However, the parts are available from many dealers. Just search on Amazon, Ebay or Aliexpress.

In our shop you can buy the PCBs. You can order them either individually, i.e. without parts, or as a kit. With the purchase of this hardware (this is not mandatory) you support us in the further development of Awtrix & Awtrix Pro.

## Assembly with PCB as kit
### Mandatory components
| No | Name | Link |
| - |:------------------------:| :------------------------------:|
| 1 | Awtrix Mainboard Kit | [click here](https://blueforcer.de/produkt/awtrix-mainboard-2-0-bausatz/) |
| 2 | 32x8 Matrix | [click here](https://de.aliexpress.com/item/4000547842744.html) |
| 3 | Awtrix housing | [click here](https://www.thingiverse.com/thing:4749750) |
| 4 | Wemos D1 mini | [click here](https://blueforcer.de/produkt/wemos-d1-mini/) |
| 5 | Power supply (>3A) | [click here](https://goo.gl/QLydM3) |
| 6 | power jack | [click here](https://goo.gl/j4Xov7) |


### Optional components
| No | Name | Link |
| - |:------------------------:| :------------------------------:|
| 1 | LDR GL5528 | [click here](https://blueforcer.de/produkt/ldr-5mm-helligkeitssensor/) |
| 2 | DF Mini Player | [click here](https://blueforcer.de/produkt/dfplayer-mini-mp3-player-modul/) |
| 3.1| Htui21d |[click here](https://de.aliexpress.com/item/32969854972.html) |
| 3.2| BME280 | [click here](https://de.aliexpress.com/item/32849462236.html) |
| 4  | Speaker             | [click here](https://blueforcer.de/produkt/awtrix-pro-lautsprecher) |

The touch sensors are not listed here because they are part of the kit and therefore do not need to be purchased.


## Assembly with PCB without kit
### Mandatory components
| No | Name | Link |
| - |:------------------------:| :------------------------------:|
| 1 | Awtrix Mainboard | [click here](https://blueforcer.de/produkt/awtrix-mainboard-2-0) |
| 2 | Wemos D1 mini | [click here](https://blueforcer.de/produkt/wemos-d1-mini/) |
| 3 | 32x8 Matrix | [click here](https://de.aliexpress.com/item/4000547842744.html) |
| 4 | Power supply (>3A) | [click here](https://goo.gl/QLydM3) |
| 5 | power jack              | [click here](https://goo.gl/j4Xov7) |
| 6 | resistors (3x 1k) | [click here](https://www.conrad.de/de/p/yageo-mf0207fte52-1k-metallschicht-widerstand-1-k-axial-bedrahtet-0207-0-6-w-1-1-st-1417606.html) |
| 7 | Shottky diodes (2x 1N4004)| [click here](https://www.conrad.de/de/p/diotec-si-gleichrichterdiode-1n4001-do-204al-50-v-1-a-162213.html) |
| 8 | jumper | |
| 9 | 1000uF 10V capacitor | [click here](https://www.conrad.de/de/p/panasonic-eca-1ahg102-elektrolyt-kondensator-radial-bedrahtet-5-mm-1000-f-10-v-20-10-mm-1-st-1475892.html) |

### Optional components
| No | Name | Link |
| - |:------------------------:| :------------------------------:|
| 1 | LDR GL5528 | [click here](https://blueforcer.de/produkt/ldr-5mm-helligkeitssensor/) |
| 2 | DF Mini Player | [click here](https://blueforcer.de/produkt/dfplayer-mini-mp3-player-modul/) |
| 3.1| Htui21d                  | [click here](https://de.aliexpress.com/item/32969854972.html) |
| 3.2| BME280                   | [click here](https://de.aliexpress.com/item/32849462236.html) |
| 4  | Speaker             | [click here](https://blueforcer.de/produkt/awtrix-pro-lautsprecher) |
| 5  | Touch sensors (3x)        | [click here](https://de.aliexpress.com/item/4000032722881.html) |


# Electronics
The electronics can either be soldered ("freely wired") on a breadboard or on a circuit board specially developed for Awtrix.

## Basic version

![Basissetup](..\assets\pro\AWTRIX_Core_Steckplatine.jpg)

## Light sensor for brightness control (optional)
The brightness sensor can be installed optionally. This ensures that, for example in a dark room, the matrix is not dazzled by dimming the brightness. On the other hand, if the room is very bright, the matrix is dimmed up so that the contents of the matrix can still be read.

![ldr](..\assets\pro\AWTRIX_LDR_Steckplatine.jpg)

## DFPlayer Mini for sound output (optional)
The DFPlayer is used for the output of sounds and can be used optionally. It stores mp3 files on a memory card, which is inserted into the micro SD slot of the player. This allows you to have your matrix speak to you or play sounds when you receive notifications, for example.  
  
You need to create a folder "MP3" on your DFplayer SD card and move your mp3s to this folder. The mp3 must start with a 4-digit number, e.g. **0001.mp3** or **0001 - Testfile.mp3**.  
AWTRIX uses the range 0001-0100 for internal purposes. Start with own mp3s at 0101.  
[Download default sounds](https://blueforcer.de/awtrix/Soundpack.zip)  
  

![](..\assets\pro\AWTRIX_DFMini_Steckplatine.jpg)

| Wemos | DFPlayer Mini | Function | Note |
| ----- | ------------- | -------- | -------- |
| 5V | VCC | Power supply (+) | |
| G | GND | Power supply (-) | |
| D7 | TX | Transmit |
| D5 | RX | Receive | former D8 |

## Temperature and humidity sensor (optional)
Optinally, Awtrix can work with two different indoor climate sensors. You can freely choose whether the BME280 or the Htu21d should be used. The measured values are sent to the server and can be displayed directly on the matrix using an app and can also be retrieved from a home automation server (ioBroker, FHEM, ...) via API from the Awtrix server.

![](..\assets\pro\AWTRIX_Temp_Steckplatine.jpg)

| Wemos | BME280 | Htu21d | Function | Note |
| --- | --- | --- | --- |--- |
| 3.3V | VCC | VCC | power supply (+) | not 5V compatible! |
| GND | GND | GND | Power supply (-) | |
| D3 | SDA | SDA |I2C Data | |
| D1 | SCL | SCL |I2C Takt | |

When using temperature and gesture sensors, the pins D1 & D3 of the Wemos D1 mini are used twice (I2C Bus).

## Touch sensors for operation (optional)

![](..\assets\pro\AWTRIX_Touch_Steckplatine.jpg)

| Wemos | Button left | Button middle | Button right | Function | Note |
| ----- | ------------- | ------------- | ------------- | -------- | -------- |
| 3.3V | VCC | VCC | VCC | Power supply (+) | |
| G | GND | GND | GND | Power supply (-) | |
| D0 | I/O | - | - | Touch signal | |
| D4 | - | I/O | - | Touch signal | **Solder bridge A** |
| D8 | - | - | I/O | Touch signal | |

!> The touch sensors have two bridges on the small circuit board which can be closed with solder. This is absolutely necessary for the middle sensor, otherwise the Wemos will not start. To prevent this from happening, the bridge A of the **middle touch sensor must be closed**. This will set the I/O pin to active low. Other touch sensors are not recommended, because they are not designed for the housing (different dimensions) and have no possibility to solder a bridge.

  <div align=center>
  <img width="100" src="..\assets\touch.jpg"/>
  </div>


## Gesture sensor for operation (optional)
The gesture sensor can be used optionally for easy operation of the matrix. Gestures like wiping with the hand from left to right or the other way around are possible. This function is no longer being developed.

![](..\assets\pro\AWTRIX_Gesture_Steckplatine.jpg)

| Wemos | APDS-9960 | Function | Note |
| --- | --- | --- | --- |
| 3.3V | VCC | power supply (+) | not 5V compatible! |
| GND | GND | Power supply (-) | |
| D3 | SDA | I2C Data | |
| D1 | SCL | I2C Takt | |
| D6 | INT | Interrupt |

When using temperature and gesture sensor, the pins D1 & D3 of the Wemos D1 mini are used twice (bus).

## Serial connection or USB connection to the matrix

If there are problems with the WiFi transfer between host and controller, there is the possibility to connect the host directly to the controller (Wemos D1 Mini) via serial.

> The Wemos still requires a connection to a wifi network.
The WiFi connection is used to update the controller and as a fallback if no data is transferred via serial.

The **USB port** of the Pi can also be used (also for any other host platform). Simply connect the server to the Wemos D1 via microUSB cable.

When using the **GPIO's** the Pi is connected to the Wemos as follows:


![](..\assets\pro\AWTRIX_raspi_V2_Steckplatine.jpg)

| Wemos | Raspberry Pin-No | Function |
| ----- | ---------------- | -------- |
| 5V | 04 - 5V | Power supply (+) |
| GND | 06 - GND | Power supply (-) |
| RX | 08 - TXD | Transmit |
| TX | 10 - RXD | Receive

!>Please pay attention to the Raspberry version. There can be differences here!

By default, the serial interface must be enabled for the Raspberry. On the Raspberry 3 this can be done with the following commands:
```
 sudo raspi-config nonint do_serial 1
 sudo raspi-config nonint set_config_var enable_uart 1 /boot/config.txt
 sudo reboot
```
