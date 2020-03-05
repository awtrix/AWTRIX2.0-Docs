![](\assets\awtrix_pro.jpg)

## Awtrix PRO
Would you like to take your previous Awtrix experience to a whole new level? Then the Awtrix Pro is exactly what you need. In addition to the integrated sound output, you can now control your matrix via touch sensors on the top of the case. The much more compact design and the use of a professional SLA print makes the matrix look much more elegant.
Awtrix PRO is a further development of the previous large Awtrix and differs essentially only in size. Both versions have the same range of functions. Only the case of the Pro is already prepared by us for all external hardware.

The software and the new (white) mainboard are the same for both devices, so there is no need to differentiate further. The matrix that is used here is a complete in-house development, as it is not yet available on the market in this form. 


## What is new?
- Three buttons on the top of the case
- Brightness sensor integrated in housing
- Raspberry Pi (Pi 3, Pi 4) can be optionally integrated into the housing
- new mainboard integrated in the housing
- 3W full-range loudspeaker integrated in housing

![](\assets\pro\pro_inside.jpg)

# Parts list
## General note
The availability of the articles changes daily. Therefore it may happen that some articles are no longer available under the link. However, the parts are available from many dealers. Just search on Amazon, Ebay or Aliexpress.

In our shop you can buy the PCBs. You can order them either individually, i.e. without parts, or as a kit. With the purchase of this hardware (this is not mandatory) you support us in the further development of Awtrix & Awtrix Pro.


### Required components
| No | Name | Link |
| - |:------------------------:| :------------------------------:|
| 1 | Awtrix Mainboard Kit | [Click here](https://blueforcer.de/produkt/awtrix-mainboard-2-0-bausatz/) |
| 2 | Per Matrix | [Click here](https://blueforcer.de/produkt/awtrix-pro-matrix/) |
| 3 | Awtrix housing | [Click here](https://www.thingiverse.com/thing:4155357) |
| 4 | Wemos D1 mini | [Click here](https://de.aliexpress.com/item/32651747570.html) |
| 5 | Power supply (>3A) | [Click here](https://goo.gl/QLydM3) |
| 6 | power jack | [click here](https://goo.gl/j4Xov7) |


### Optional components
| No | Name | Link |
| - |:------------------------:| :------------------------------:|
| 1 | LDR GL5528 | [Click here](https://de.aliexpress.com/item/32515315072.html) |
| 2 | DF Mini Player | [Click here](https://de.aliexpress.com/item/32992229288.html) |
| 4 | loudspeakers | [Click here](https://de.aliexpress.com/item/32853811267.html) |

The touch sensors are not listed here because they are part of the Awtrix mainboard kit and therefore do not need to be purchased.


# Electronics

The mainboard is already labeled and the components can be soldered directly to the pads or connected/plugged via pin headers.

![](\assets\pro\front.png)


If you have soldered pin headers, you can already mount the mainboard, speakers and the Raspberry into the case. Otherwise you should solder everything together before you install it. The DC jack should be installed before soldering to be able to mount the locknut.

!> Do not use thin cables for the power supply of the mainboard and the matrix, because relatively high currents flow here and the voltage drop can be too high due to thin cables. This can lead to problems.

## AWTRIX Pro Matrix

This matrix was developed primarily for AWTRIX. In order to save production costs, an aluminium core has been omitted from the circuit board.
Instead, the rear side was generously provided with ground planes to dissipate the heat. However, the matrix is not designed for full LED power.

!> Never drive all 256 LEDs at once for a long time at high brightness. This can cause damage to the matrix due to the heat development.

The large ground plane acts like a bi-metal, which causes a slight deformation of the board in the reflow oven (Soldering process). This has no effect on the functionality of the LED and is straightened by the screw connection in the housing.


## Touch sensors 

!> The touch sensors have two bridges on the small circuit board which can be closed with solder. This is absolutely necessary for the middle sensor, otherwise the Wemos will not start. To prevent this from happening the bridge A of the **middle touch sensors must be closed**. This will set the I/O pin to active low. 


## Serial connection or USB connection to the matrix

Since AWTRIX is built into the case, it is possible to connect the Raspberry directly to the motherboard via serial. Here the Raspberry is also powered by the mainboard.

> The Wemos still requires a connection to a network.
The WiFi connection is used to continue to update the controller and as a fallback if no data is transferred via serial.

For this purpose the Pi is connected to the mainboard as follows:


| Raspberry Pin-No | Mainboard (Raspberry Serial header) |
| ---------------- | -------- |
| 04 - 5V | +5V) |
| 06 - GND | GND |
| 08 - TXD | Rx
| 10 - RXD | Tx |

!> **Please pay attention to the Raspberry version. Here there can be differences! **

By default, the serial interface must be enabled for the Raspberry. With the Raspberry 3 you can do this with the following commands:
```
 sudo raspi-config nonint do_serial 1
 sudo raspi-config nonint set_config_var enable_uart 1 /boot/config.txt
 sudo reboot
```

## DFPlayer

The DFPlayer is used for the output of sounds and can be used optionally. It stores mp3 files on a memory card, which is inserted into the micro SD slot of the player. This allows you to have your matrix speak to you or play sounds when you are notified.  
  
You need to create a folder "MP3" on your DFplayer SD card and move your mp3s to this folder. The mp3 must start with a 4-digit number, e.g. **0001.mp3** or **0001 - Testfile.mp3**.  
AWTRIX uses the range 0001-0100 for internal purposes. Start with own mp3s at 0101.  
[Download default sounds](https://blueforcer.de/awtrix/beta/Soundfiles.zip)

# Assembly

Only a maximum of 14x **M3x4** screws are required for assembly. These fix the matrix, mainboard and the Raspberry.

- The matrix is screwed **handtight** into the grid with 6 screws. It is important to pay attention to the direction, because the matrix is only perfect in one direction (external capacitors have to be placed in the corresponding notches).

- You can simply insert the loudspeaker into the recess and therefore it does not need to be fixed any further.

- Insert the LDR from the outside through the cabinet until it is flush with the top of the cabinet.

- The touch sensors theoretically fit perfectly into the 3 slots. Due to pressure tolerances it might be necessary to fix them with double-sided adhesive tape or to smooth the boards slightly with sandpaper on the sides.
