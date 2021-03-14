## AWTRIX Family

  <div align=center>
  <img width="400" src="..\assets\family.JPG"/>
  </div>

Here you will find all the information you need to build an AWTRIX.
You can build AWTRIX in 3 different sizes. Except for the matrix, the electronics is the same for all of them.
- AWTRIX Big (~329x98x43mm)
- AWTRIX Midi (~270x74x43mm)
- AWTRIX Mini, formerly "Pro" (~202x69x40mm)

You can find the housings on https://www.thingiverse.com/thing:4749750 or in the store for a fair price if you don't own a 3D printer.


# Parts list

All parts can be found elsewhere (except AWTRIX Mini Matrix and possibly acrylic glass). You don't have to buy anything in my store to build your own AWTRIX. However, this supports me in the further development of AWTRIX.
If you want to build your own style you can find the basic electronics [here](en-en/hardware.md)

### Matrix
|      Name      |                              Link                              |
| :------------: | :------------------------------------------------------------: |
|    Big   | [Click here](https://blueforcer.de/produkt/flexmatrix-8x32/) |
|   Midi | [Click here](https://blueforcer.de/produkt/awtrix-midi-matrix/) |
|  Mini  | [Click here](https://blueforcer.de/produkt/awtrix-mini-matrix/) |

### Acrylic
|      Name      |                              Link                              |
| :------------: | :------------------------------------------------------------: |
|   Big   | [Click here](https://blueforcer.de/produkt/7980/) |
|   Midi | [Click here](https://blueforcer.de/produkt/awtrix-midi-acrylglas/) |
|   Mini  | [Click here](https://blueforcer.de/produkt/awtrix-pro-acrylglas/) |

### Benötigte Bauteile
|           Name           |                                    Link                                    |
| :----------------------: | :------------------------------------------------------------------------: |
| Awtrix Mainboard Bausatz | [Click here](https://blueforcer.de/produkt/awtrix-mainboard-2-0-bausatz/)  |
|      Wemos D1 mini       |       [Click here](https://blueforcer.de/produkt/wemos-d1-mini/)          |
|      Power Supply (>3A)      |                    [Click here](https://goo.gl/QLydM3)                    |
|       Strombuchse        |                    [Click here](https://blueforcer.de/produkt/dc-einbaubuchse-55mm-x-25mm/)                    |
|         M3x4             |               Maximum 12 pieces depending on expansion stage                    |

### Optionale Bauteile
|      Name      |                              Link                              |
| :------------: | :------------------------------------------------------------: |
|   LDR GL5528   | [Click here](https://blueforcer.de/produkt/ldr-5mm-helligkeitssensor/) |
| DF Mini Player | [Click here](https://blueforcer.de/produkt/dfplayer-mini-mp3-player-modul/) |
|  Speaker  | [Click here](https://blueforcer.de/produkt/awtrix-pro-lautsprecher) |



# AWTRIX Big
1. mount the power jack into the housing. You can mount it on the side as well as on the back, the other, open grommet you close from the inside with the blind plug. Screw the mainboard (Wemos on the right side) and possibly the Raspberry into the case and insert the LDR and speaker. Solder all components together and push the touchbuttons into the recesses. Make sure that the parts on the buttons are facing inwards and the printed side is facing outwards.

2. ScrewPlace the flexible matrix in the groove, making sure that the corners are bent straight and do not stick out of the groove.

3. Insert the Plexiglas into the frame, then the grid. Now press the frame with acrylic and grid onto the case. By pressing on all 4 corners, the frame will snap onto the housing. Make sure that the small notches on the frame point downwards. These are there to lift the frame off the case with a screwdriver.


# AWTRIX Midi
1. mount the power jack into the case. You can mount it on the side as well as on the back, the other, open grommet you close from the inside with the blind plug. Screw the mainboard (Wemos on the right side) and possibly the Raspberry into the case and insert the LDR and speaker. Solder all components together and push the touchbuttons into the recesses. Make sure that the parts on the buttons are facing inwards and the printed side is facing outwards. 

2. Solder the 4 8x8 Matrix Panels together using the AWTRIX Midi Connectors. The matrix is mounted upside down. This means that the font is upside down. The D-IN connector of the first matrix is on the left side.
At this point there is a recess in the housing to make room for cables or pin header. Place the matrix array in the groove provided. 

3. Insert the plexiglass into the frame, then the grid. Pay attention to the correct orientation of the grid. The smooth side faces outwards, the inside has some recesses in the grid for the pin strips that come from the matrix connections. Now press the frame with acrylic and grid onto the case. By pressing on all 4 corners the frame will snap onto the case. Make sure that the small notches on the frame point downwards. These are there to lift the frame off the case with a screwdriver.

# AWTRIX Mini
1. mount the power jack into the case. Screw the mainboard (Wemos on the right side) and possibly the Raspberry into the case and insert the LDR and speaker. Solder all components together and push the touchbuttons into the recesses. Make sure that the parts on the buttons are facing inwards and the printed side is facing outwards.

2. Screw the matrix into the grid and pay attention to the orientation. You can see this by the "TOP" lettering in the grid. Put the matrix with the grid into the case. 

3. Now insert the plexiglass into the housing. This snaps in at 4 points in the housing, use if necessary a narrow screwdriver to push the housing slightly away to let the acrylic glass snap into the recesses. After that only the frame has to be inserted. This also snaps into place.


# Detailed assembly

These instructions refer to the AWTRIX mini, but apart from the cable length, this can be applied to any variant.

## 1. Touch Sensors
- The resistor of the LED on the touch button can be optionally soldered out.
- If the housing is bright, the light of the LED can otherwise be seen from outside.
- The LED on the middle button lights up permanently if the resistor is not removed.
- The touch sensors theoretically fit perfectly into the 3 receptacles. However, due to pressure tolerances it may be necessary to fix them with double-sided adhesive tape or to smooth the boards slightly with sandpaper on the sides.

### 1.1 Left Touch Sensor (btn_left)
- Cut 3 cables to approx. 14cm length. If available, three different colours. 
- Strip, twist and tin the cable ends on both sides for approx. 2mm.
- DO NOT insert the cable through the holes of the Touch Sensor, but only from above and solder it on. (black = GND ; red = 3.3V/VCC ; green = Data/IO)
- When plugging through, the cable ends on the other side are too wide and prevent an optimal placement of the sensor in the housing
- Solder the other ends to the mainboard. Put the cables through the holes provided for this - gives more stability.

 <div align=center>
  <img width="400" src="../assets/manualPicture/case/btnLeft.jpg"/>
    <img width="400" src="../assets/manualPicture/case/btnLeft2.jpg"/>
      <img width="400" src="../assets/manualPicture/case/btnLeft3.jpg"/>
  </div>

### 1.2 Middle Touch Sensor (btn_middle)
- Cut 3 cables to approx. 14cm length. If available, three different colours. 
- Strip, twist and tin the cable ends on both sides for approx. 2mm.
- DO NOT insert the cable through the holes of the Touch Sensor, but only from above and solder it on. (black = GND ; red = 3.3V/VCC ; green = Data/IO)
- When plugging through, the cable ends on the other side are too wide and prevent an optimal positioning of the sensor in the housing
- close the bridge! Otherwise the Wemos D1 mini will not start.
- Solder the other ends to the mainboard. Put the cables through the holes provided here - gives more stability.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/btnMiddle.jpg"/>
    <img width="400" src="../assets/manualPicture/case/btnMiddle2.jpg"/>
  </div>


### 1.3 Right Touch Sensor (btn_right)
- Cut 3 cables to approx. 14cm length. If available, three different colours. 
- Strip, twist and tin the cable ends on both sides for approx. 2mm.
- DO NOT insert the cable through the holes of the Touch Sensor, but only from above and solder it on. (black = GND ; red = 3.3V/VCC ; green = Data/IO)
- When plugging through, the cable ends on the other side are too wide and prevent an optimal placement of the sensor in the housing
- Solder the other ends to the mainboard. Put the cables through the holes provided for this - gives more stability.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/btnRight.jpg"/>
  <img width="400" src="../assets/manualPicture/case/btnRight2.jpg"/>
  </div>

## 2. LDR / light sensor
- Cut 2 cables to approx. 7cm length. Can be used two times the same color, as there is no polarity.
- Strip, twist and tin both ends of the cable for approx. 2mm.
- Shorten the legs of the LDR to about 3-4mm and solder them to the cables.
- Solder the other ends to the mainboard. Here put the cables through the holes provided for it - gives more stability.
- As already mentioned the polarity of the LDR is not relevant. 

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/ldr.jpg"/>
    <img width="400" src="../assets/manualPicture/case/ldr2.jpg"/>
  </div>

## 3. Speaker
- The speaker we use has a polarity. This must be observed.
- Cut the red cable to about 11cm, cut the black cable to about 13cm. Cable lengths are only correct here if the speaker is installed exactly as described in this manual!
- solder the red cable to the plus of the speaker
- solder the black wire to the minus of the speaker
- The cables are soldered on the mainboard under "Speaker". Red cable to the rectangular pin, black cable to the oval pin. 
- You can simply put the speaker into the recess and therefore you don't have to fix it further.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/speaker.jpg"/>
    <img width="400" src="../assets/manualPicture/case/speaker2.jpg"/>
      <img width="400" src="../assets/manualPicture/case/speaker3.jpg"/>
  </div>

## 4. DC jack
- With the DC jack it is especially important to observe the polarity.
- Cut 2 cables to approx. 8cm length. Use two different colours. (black = GND ; red = +5V)
- Solder the cable to the DC socket. Solder red to the middle contact (+5V), black to the outer contact (GND).
- Then screw the socket into the housing.
- Now the other ends can be connected to the mainboard. (black = GND ; red = +5V)
- Check the connection again because otherwise the matrix will be damaged.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/socket.jpg"/>
    <img width="400" src="../assets/manualPicture/case/socket2.jpg"/>
      <img width="400" src="../assets/manualPicture/case/socket3.jpg"/>
  </div>


## 5. Mounting Matrix
- The matrix is screwed to the grid with 6 screws (M3x4).
- Tighten the screws only very slightly. Otherwise the matrix can be damaged and the plastic threads in the grid can be broken.
- Pay attention to the direction when inserting the matrix into the grid. For each capacitor there is a recess in the grid. If you have the matrix in front of you in the right direction, you will see no capacitors on the left side of the grid, while capacitors are on the right side. In the grid there is a side where there are no cutouts on the outside. These must correspond with the matrix!
  <div align=center>
  <img width="400" src="../assets/manualPicture/case/matrix2.jpg"/>
  <img width="400" src="../assets/manualPicture/case/matrix3.jpg"/>
  </div>

## 6. Matrix
- Cut 3 cables to approx. 12cm length. If available, three different colours. (black = GND ; red = +5V ; green = Data/data_in)
- Solder cables to the matrix. It is especially important that the three contacts for connection are selected in which "data_in" occurs. (black = GND ; red = +5V ; green = data_in)
- Then solder the cables on the mainboard at the label "Matrix". (black = GND ; red = +5V ; green = Data)
- Check the connection again because otherwise the matrix will be damaged.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/matrix.jpg"/>
  </div>



## 7. Motherboard
- The mainboard is fixed in the case with four screws (M3x4).
- Tighten the screws only very slightly. Otherwise the plastic thread in the case can break.
  
  <div align=center>
  <img width="400" src="../assets/manualPicture/case/mainboard.jpg"/>
  </div>


## 8. Serial connection or USB connection to the matrix

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

## 9. Insert grid into the housing
- Now it's time to close the case and put the matrix into operation.
- If your Wemos D1 mini has not been recorded with the controller software at this point, do so before closing the case!
- Place the case so that the touch buttons and the LDR are looking up/away from you.
- When inserting the grid into the case, the connection cables of the matrix must be on the left side.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/timeToFinish.jpg"/>
  <img width="400" src="../assets/manualPicture/case/finish.jpg"/>
  </div>
- Now insert the acrylic glass at a slight angle, if necessary use a narrow slotted screwdriver to push the housing away a little to let the acrylic glass snap into the recesses.
- Now just insert the frame and snap it into place.

## 10. FINISHED
- Do you have any questions? Then please ask them in the forum. Other users may benefit from public questions.
- Show us your finished matrix on Facebook or in the forum.
- Have fun with your matrix!

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/finish2.jpg"/>
  </div>