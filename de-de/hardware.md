![](..\assets\awtrix.jpeg)

# Teileliste
## Allgemeiner Hinweis
Die Verfügbarkeit der Artikel ändert sich täglich. Daher kann es vorkommen, dass einige Artikel unter dem Link nicht mehr zu finden sind. Allerdings gibt es die Teile von vielen Händlern. Einfach auf Amazon, Ebay oder Aliexpress suchen.

In unserem Shop gibt es die Leiterplatten zu kaufen. Diese sind entweder einzeln, also ohne Bauteile, oder als Bausatz bestellbar. Mit dem Kauf dieser Hardware (diese ist nicht zwingend notwendig) unterstützt ihr uns bei der Weiterentwicklung von Awtrix & Awtrix Pro.

## Aufbau mit Leiterplatte als Bausatz
### Zwingend benötigte Bauteile
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | Awtrix Mainboard Bausatz | [click here](https://blueforcer.de/produkt/awtrix-mainboard-2-0-bausatz/) |
| 2  | 32x8 Matrix              | [click here](https://de.aliexpress.com/item/4000547842744.html) |
| 3  | Awtrix Gehäuse       | [click here](https://www.thingiverse.com/thing:2791276) |
| 4  | Wemos D1 mini            | [click here](https://de.aliexpress.com/item/32651747570.html) |
| 5  | Netzteil (>3A)           | [click here](https://goo.gl/QLydM3) |
| 6  | Strombuchse              | [click here](https://goo.gl/j4Xov7) |


### Optionale Bauteile
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | LDR GL5528               | [click here](https://de.aliexpress.com/item/32515315072.html) |
| 2  | DF Mini Player           | [click here](https://de.aliexpress.com/item/32992229288.html) |
| 3.1| Htui21d                  | [click here](https://de.aliexpress.com/item/32969854972.html) |
| 3.2| BME280                   | [click here](https://de.aliexpress.com/item/32849462236.html) |
| 4  | Lautsprecher             | [click here](https://de.aliexpress.com/item/32853811267.html) |

Die Touchsensoren sind hier nicht mit aufgeführt, weil sie Teil des Bausatzes sind und daher nicht gekauft werden müssen.


## Aufbau mit Leiterplatte ohne Bausatz
### Zwingend benötigte Bauteile
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | Awtrix Mainboard Bausatz | [click here](https://blueforcer.de/produkt/awtrix-mainboard-2-0-bausatz/) |
| 2  | Wemos D1 mini            | [click here](https://de.aliexpress.com/item/32651747570.html) |
| 3  | 32x8 Matrix               | [click here](https://de.aliexpress.com/item/4000547842744.html) |
| 4  | Netzteil (>3A)           | [click here](https://goo.gl/QLydM3) |
| 5  | Strombuchse              | [click here](https://goo.gl/j4Xov7) |
| 6  | Widerstände (3x 1k)      | [click here](https://www.conrad.de/de/p/yageo-mf0207fte52-1k-metallschicht-widerstand-1-k-axial-bedrahtet-0207-0-6-w-1-1-st-1417606.html) |
| 7  | Shottkydioden (2x 1N4004)| [click here](https://www.conrad.de/de/p/diotec-si-gleichrichterdiode-1n4001-do-204al-50-v-1-a-162213.html) |
| 8  | Jumper                   |  |
| 9 | 1000uF 10V Kondensator   | [click here](https://www.conrad.de/de/p/panasonic-eca-1ahg102-elektrolyt-kondensator-radial-bedrahtet-5-mm-1000-f-10-v-20-10-mm-1-st-1475892.html) |

### Optionale Bauteile
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | LDR GL5528               | [click here](https://de.aliexpress.com/item/32515315072.html) |
| 2  | DF Mini Player           | [click here](https://de.aliexpress.com/item/32992229288.html) |
| 3.1| Htui21d                  | [click here](https://de.aliexpress.com/item/32969854972.html) |
| 3.2| BME280                   | [click here](https://de.aliexpress.com/item/32849462236.html) |
| 4  | Lautsprecher             | [click here](https://de.aliexpress.com/item/32853811267.html) |
| 5  | Touch Taster (3x)        | [click here](https://de.aliexpress.com/item/4000032722881.html) |


# Elektronik
Die Elektronik kann entweder auf eine Lochrasterplatine gelötet ("frei verdrahtet") werden oder auf der extra für Awtrix entwickelten Leiterplatte.

## Basis Variante

![Basissetup](..\assets\pro\AWTRIX_Core_Steckplatine.jpg)

## Lichtsensor zur Helligkeitsregelung (optional)
Der Helligkeitssensor kann optinal eingebaut werden. Dieser sorgt dafür, dass beispielsweise in einem dunklen Raum, durch herunter dimmen der Helligkeit, die Matrix nicht blendet. Anders herum wird die Matrix bei einer hohen Helligkeit im Raum hoch gedimmt, damit man den Inhalt der Matrix noch lesen kann.

![ldr](..\assets\pro\AWTRIX_LDR_Steckplatine.jpg)

## DFPlayer Mini zur Soundausgabe (optional)
Der DFPlayer dient zur Ausgabe von Sounds und ist optional verwendbar. Es werden mp3 Dateien auf einer Speicherkarte gespeichert, welche in das Micro-SD Fach des Players eingesteckt wird. Dies ermöglicht es dir, dass deine Matrix beispielsweise mit dir spricht oder Töne bei Benachrichtigungen abspielt.  
  
Du musst einen Ordner “MP3” auf deiner DFplayer SD-Karte erstellen und deine mp3s in diesen Ordner verschieben. Die mp3 muss mit einer 4-stelligen Zahl beginnen, z.B. **0001.mp3** oder **0001 - Testfile.mp3**.  
AWTRIX verwendet den Bereich 0001-0100 für interne Zwecke. Beginne mit eigenen mp3s bei 0101.  
[Standardsounds herunterladen](https://blueforcer.de/awtrix/Soundfiles.zip)  
  

![](..\assets\pro\AWTRIX_DFMini_Steckplatine.jpg)

| Wemos | DFPlayer Mini | Funktion | Hinweis  |
| ----- | ------------- | -------- | -------- |
| 5V    | VCC           | Spannungsversorgung (+)    |          |
| G     | GND           | Spannungsversorgung (-)   |          |
| D7    | TX            | Transmit (senden) |          |
| D5    | RX            | Receive (empfangen)  | früher D8 |

## Temperatur- und Luftfeuchtigkeitssensor (optional)
Optinal kann Awtrix mit zwei verschiedenen Raumklimasensoren arbeiten. Hierbei kann frei gewählt werden ob der BME280 oder der Htu21d zum Einsatz kommen soll. Die gemessenen Werte werden dem Server geschickt und können zum Einen mittels App direkt auf der Matrix angezeigt werden und zum Anderen von einem Hausautomationsserver (ioBroker, FHEM, ...) mittels API vom Awtrix Server abgerufen werden.

![](..\assets\pro\AWTRIX_Temp_Steckplatine.jpg)

| Wemos | BME280 | Htu21d | Funktion | Hinweis  |
| --- | --- | --- | --- |--- |
| 3.3V | VCC |  VCC |Spannungsversorgung (+) | nicht 5V kompatibel! |
| GND | GND | GND |Spannungsversorgung (-) | |
| D3 | SDA | SDA |I2C Daten | |
| D1 | SCL | SCL |I2C Takt | |

Bei Verwendung von Temperatur- und Gestensensor werden die Pins D1 & D3 des Wemos D1 mini doppelt verwendet (I2C Bus).

## Touch-Taster zur Bedienung (optional)

![](..\assets\pro\AWTRIX_Touch_Steckplatine.jpg)

| Wemos | Taster links | Taster mitte | Taster rechts |Funktion | Hinweis  |
| ----- | ------------- | ------------- | ------------- | -------- | -------- |
| 3,3V    | VCC  | VCC           | VCC                    | Spannungsversorgung (+)    |          |
| G     | GND       | GND   | GND       | Spannungsversorgung (-)   |          |
| D0    | I/O   |  -  |     -        | Tastsignal |          |
| D4    | -  | I/O  | -            | Tastsignal  | **Brücke A zulöten** |
| D8    | -  | -  | I/O            | Tastsignal  |  |

!> Die Touch Sensoren haben auf der kleinen Leiterplatte zwei Brücken die mann mit Lötzinn verschließen kann. Dies wird beim mittleren Sensor zwingend benötigt, da der Wemos ansonsten nicht mehr startet. Um dies zu verhindern muss beim **mittleren Touch Taster die Brücke A geschlossen** werden. Dadurch wird der I/O Pin auf Active Low gestellt. Andere Touch Sensoren werden nicht empfohlen, da sie erstens nicht fürs Gehäuse vorgesehen sind (andere Maße) und zweitens keine Möglichkeit besitzen eine Brücke einzulöten.
  <div align=center>
  <img width="100" src="..\assets\touch.jpg"/>
  </div>

## Gestensensor zur Bedienung (optional)
Der Gestensensor kann optinal zur einfachen Bedienung der Matrix benutzt werden. Gesten wie mit der Hand von links nach rechts wischen oder anders herum sind hier möglich. Diese Funktion wird nicht weiterentwickelt.

![](..\assets\pro\AWTRIX_Gesture_Steckplatine.jpg)

| Wemos | APDS-9960 | Funktion | Hinweis  |
| --- | --- | --- | --- |
| 3.3V | VCC | Spannungsversorgung (+) | nicht 5V kompatibel! |
| GND | GND | Spannungsversorgung (-) | |
| D3 | SDA | I2C Daten | |
| D1 | SCL | I2C Takt | |
| D6 | INT | Interrupt |  |

Bei Verwendung von Temperatur- und Gestensensor werden die Pins D1 & D3 des Wemos D1 mini doppelt verwendet (Bus).

## Serielle Verbindung oder USB-Verbindung zur Matrix

Wenn es Probleme bei der WiFi-Übertragung zwischen Server und Controller gibt, gibt es die Möglichkeit den Server direkt per Serial an den Controller (Wemos D1 Mini) anzuschließen.

> Der Wemos weiterhin zwingend eine Verbindung zu einem Netzwerk.
Die WiFi Verbindung wird verwendet, um den Controller auch weiterhin updaten zu können und als Fallback falls keine Daten per Serial übertragen werden.

Es kann auch der **USB-Port** des Pi's verwendet werden (auch für jede andere Serverplattform). Dazu muss man einfach den Server per microUSB-Kabel an den Wemos D1 anschließen.

Bei Verwenudng der **GPIO's** wird der Pi wie folgt mit dem Wemos verbunden:

![](..\assets\pro\AWTRIX_raspi_V2_Steckplatine.jpg)

| Wemos | Raspberry Pin-No | Funktion |
| ----- | ---------------- | -------- |
| 5V    | 04 - 5V          | Spannungsversorgung (+) |
| GND   | 06 - GND         | Spannungsversorgung (-)   |
| RX    | 08 - TXD         | Transmit (senden) |
| TX    | 10 - RXD         | Receive (empfangen)  |

!> **Bitte zwingend auf die Raspberry Version achten. Hier kann es unterschiede geben!**

Standardmäßig muss beim Raspberry die serielle Schnittstelle freigeschaltet werden. Beim Raspberry 3 kann man das über folgende Befehle machen:
```
 sudo raspi-config nonint do_serial 1
 sudo raspi-config nonint set_config_var enable_uart 1 /boot/config.txt
 sudo reboot
```
