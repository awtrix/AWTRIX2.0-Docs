![image alt text](\assets\awtrix.jpeg)

## **_Awtrix PRO_**
Awtrix PRO ist eine Weiterentwicklung bisherigen großen Awtrix. Software ist bei beiden Geräten gleich, weshalb hierbei nicht weiter unterschieden werden muss. Die Hardware hingegen ist deutlich kleiner geworden. Die Matrix die hier zum Einsatz kommt ist eine komplette Eigenentwicklung, da diese so in der Form noch nicht auf dem Markt ist. 

## **_Warum Awtrix PRO?_**
Du möchtest dein bisheriges Awtrix-Erlebnis nochmal auf ein ganz anderes Level bringen? Dann ist die Awtrix Pro genau das richtige. Neben der integrierten Soundausgabe kannst du deine Matrix nun auch per Touchsensoren auf der Gehäuseoberseite steuern. Die deutlich kompaktere Bauform und die Verwendung eines professionellen SLA-Drucks lässt die Matrix um ein vielfaches edler aussehen.
## **_Was ist neu?_**
- drei Taster auf der Gehäuseoberseite
- Helligkeitssensor im Gehäuse integriert
- Raspberry Pi (Pi 3, Zero W) optional im Gehäuse integrierbar
- neues Mainboard im Gehäuse integriert
- Lautsprecher im Gehäuse integriert

# Teileliste
## **_Allgemeiner Hinweis_**
Die Verfügbarkeit der Artikel ändert sich täglich. Daher kann es vorkommen, dass einige Artikel unter dem Link nicht mehr zu finden sind. Allerdings gibt es die Teile von vielen Händlern. Einfach auf Amazon, Ebay oder Aliexpress suchen.

In unserem Shop gibt es die Leiterplatten zu kaufen. Diese sind entweder einzeln, also ohne Bauteile, oder als Bausatz bestellbar. Mit dem Kauf dieser Hardware (diese ist nicht zwingend notwendig) unterstützt ihr uns bei der Weiterentwicklung von Awtrix & Awtrix Pro.

## **_Aufbau mit Leiterplatte als Bausatz_**
### **_Zwingend benötigte Bauteile_**
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | Awtrix Mainboard Bausatz | [click here](https://google.de) |
| 2  | 32x8 Matrix              | [click here](https://blueforcer.de/shop/) |
| 3  | Awtrix Gehäuse       | [click here](https://blueforcer.de/shop/) |
| 4  | Wemos D1 mini            | [click here](https://goo.gl/TVk7h7) |
| 5  | Netzteil (>3A)           | [click here](https://goo.gl/QLydM3) |
| 6  | Strombuchse              | [click here](https://goo.gl/j4Xov7) |


### **_Optionale Bauteile_**
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | LDR GL5528               | [click here](https://www.amazon.de/Qualit%C3%A4t-GL5516-Lichtabh%C3%A4ngige-Widerstand-Fotowiderstand/dp/B00NXW9WZ6/) |
| 2  | DF Mini Player           | [click here](https://www.banggood.com/Geekcreit-DFPlayer-Mini-MP3-Player-Module-MP3-Voice-Audio-Decoder-Board-For-Arduino-Supporting-TF-Card-U-Disk-IOSerial-PortAD-p-969191.html?akmClientCountry=DE&&cur_warehouse=UK) |
| 3.1| Htui21d                  | [click here](https://google.de) |
| 3.2| BME280                   | [click here](https://google.de) |
| 4  | Lautsprecher             | [click here](https://de.aliexpress.com/item/32853811267.html) |

Die Touchsensoren sind hier nicht mit aufgeführt, weil sie Teil des Bausatzes sind und daher nicht gekauft werden müssen.


## **_Aufbau mit Leiterplatte ohne Bausatz_**
### **_Zwingend benötigte Bauteile_**
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | Awtrix Mainboard Bausatz | [click here](https://google.de) |
| 2  | Wemos D1 mini            | [click here](https://goo.gl/TVk7h7) |
| 3  | 32x8 Matrix               | [click here](https://blueforcer.de/shop/) |
| 4  | Netzteil (>3A)           | [click here](https://goo.gl/QLydM3) |
| 5  | Strombuchse              | [click here](https://goo.gl/j4Xov7) |
| 6  | Widerstände (3x 1k)      | [click here](https://google.de) |
| 7  | Shottkydioden (2x 1N4004)| [click here](https://google.de) |
| 8  | Stiftleiste              | [click here](https://google.de) |
| 9  | Jumper                   | [click here](https://google.de) |
| 10 | 1000uF 10V Kondensator   | [click here](https://google.de) |

### **_Optionale Bauteile_**
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | LDR GL5528               | [click here](https://www.amazon.de/Qualit%C3%A4t-GL5516-Lichtabh%C3%A4ngige-Widerstand-Fotowiderstand/dp/B00NXW9WZ6/) |
| 2  | DF Mini Player           | [click here](https://www.banggood.com/Geekcreit-DFPlayer-Mini-MP3-Player-Module-MP3-Voice-Audio-Decoder-Board-For-Arduino-Supporting-TF-Card-U-Disk-IOSerial-PortAD-p-969191.html?akmClientCountry=DE&&cur_warehouse=UK) |
| 3.1| Htui21d                  | [click here](https://google.de) |
| 3.2| BME280                   | [click here](https://google.de) |
| 4  | Touch Taster (3x)        | [click here](https://google.de) |
| 5  | Lautsprecher             | [click here](https://de.aliexpress.com/item/32853811267.html) |


# Elektronik
Die Elektronik kann entweder auf eine Lochrasterplatine gelötet ("frei verdrahtet") werden oder auf der extra für Awtrix entwickelten Leiterplatte. Die genauen Details zu den benötigten Bauteilen bitte der [Teileliste](../AWTRIXpro/partlistPro) entnehmen.

## Basis Variante

![Basissetup](\assets\pro\AWTRIX_Core_Steckplatine.jpg)

## Lichtsensor zur Helligkeitsregelung (optional)
Der Helligkeitssensor kann optinal eingebaut werden. Dieser sorgt dafür, dass beispielsweise in einem dunklen Raum, durch herunter dimmen der Helligkeit, die Matrix nicht blendet . Anders herum wird die Matrix bei einer hohen Helligkeit im Raum hoch gedimmt, damit man den Inhalt der Matrix noch lesen kann.

![ldr](\assets\pro\AWTRIX_LDR_Steckplatine.jpg)

## DFPlayer Mini zur Soundausgabe (optional)
Der DFPlayer dient zur Ausgabe von Sounds und ist optinal verwendbar. Es werden mp3 Dateien auf einer Speicherkarte gespeichert, welche in das Micro-SD Fach des Players eingesteckt wird. Dies ermöglicht es dir, dass deine Matrix beispielsweise mit dir spricht. Das hinzufügen von mp3 Dateien kann leider nur über die SD Karte am PC erfolgen. Ein hochladen vom Server oder ähnliches ist technisch leider nicht möglich.

![image alt text](\assets\pro\AWTRIX_DFMini_Steckplatine.jpg)

| Wemos | DFPlayer Mini | Funktion | Hinweis  |
| ----- | ------------- | -------- | -------- |
| 5V    | VCC           | Spannungsversorgung (+)    |          |
| G     | GND           | Spannungsversorgung (-)   |          |
| D7    | TX            | Transmit (senden) |          |
| D5    | RX            | Receive (empfangen)  | früher D8 |

## Temperatur- und Luftfeuchtigkeitssensor (optional)
Optinal kann Awtrix mit zwei verschiedenen Raumklimasensoren arbeiten. Hierbei kann frei gewählt werden ob der BME280 oder der Htu21d zum Einsatz kommen soll. Die gemessenen Werte werden dem Server geschickt und können zum Einen mittels App direkt auf der Matrix angezeigt werden und zum Anderen von einem Hausautomationsserver (ioBroker, FHEM, ...) mittels API vom Awtrix Server abgerufen werden.

![image alt text](\assets\pro\AWTRIX_Temp_Steckplatine.jpg)

| Wemos | BME280 | Htu21d | Funktion | Hinweis  |
| --- | --- | --- | --- |--- |
| 3.3V | VCC |  VCC |Spannungsversorgung (+) | nicht 5V kompatibel! |
| GND | GND | GND |Spannungsversorgung (-) | |
| D3 | SDA | SDA |I2C Daten | |
| D1 | SCL | SCL |I2C Takt | |

Bei Verwendung von Temperatur- und Gestensensor werden die Pins D1 & D3 des Wemos D1 mini doppelt verwendet (I2C Bus).

## Touch-Taster zur Bedienung (optional)

![image alt text](\assets\pro\AWTRIX_Touch_Steckplatine.jpg)

| Wemos | Taster links | Taster mitte | Taster rechts |Funktion | Hinweis  |
| ----- | ------------- | ------------- | ------------- | -------- | -------- |
| 3,3V    | VCC  | VCC           | VCC                    | Spannungsversorgung (+)    |          |
| G     | GND       | GND   | GND       | Spannungsversorgung (-)   |          |
| D0    | I/O   |  -  |     -        | Tastsignal |          |
| D4    | -  | I/O  | -            | Tastsignal  | Brücke A zulöten |
| D5    | -  | -  | I/O            | Tastsignal  |  |

Die Touch Sensoren haben auf der kleinen Leiterplatte zwei Brücken die mann mit Lötzinn verschließen kann. Dies wird beim mittleren Sensor zwingend benötigt, da der Wemos anssonsten nicht mehr startet. Um dies zu verhindern muss beim **mittleren Touch Taster die Brücke A geschlossen** werden. Dadurch wird der I/O Pin auf Active Low gestellt. Andere Touch Sensoren werden nicht empfohlen, da sie erstens nicht fürs Gehäuse vorgesehen sind (andere Maße) und zweitens keine Möglichkeit besitzen eine Brücke einzulöten.

## Gestensensor zur Bedienung (optional)
Der Gestensensor kann optinal zur einfachen Bedienung der Matrix benutzt werden. Gesten wie mit der Hand von links nach rechts wischen oder anders herum sind hier möglich.

![image alt text](\assets\pro\AWTRIX_Gesture_Steckplatine.jpg)

| Wemos | APDS-9960 | Funktion | Hinweis  |
| --- | --- | --- | --- |
| 3.3V | VCC | Spannungsversorgung (+) | nicht 5V kompatibel! |
| GND | GND | Spannungsversorgung (-) | |
| D3 | SDA | I2C Daten | |
| D1 | SCL | I2C Takt | |
| D6 | INT | Interrupt |  |

Bei Verwendung von Temperatur- und Gestensensor werden die Pins D1 & D3 des Wemos D1 mini doppelt verwendet (Bus).

## Serielle Verbindung oder USB-Verbindung zur Matrix

Wenn es probleme bei der WiFi-Übertragung zwischen Server und Controller gibt, gibt es die Möglichkeit den Server direkt per Serial an den Controller (Wemos D1 Mini) anzuschließen.

Auf Controller-Seite muss hierfür im Hotspot Menü der Haken bei Serial gesetzt werden. Außerdem braucht der Wemos weiterhin zwingend eine Verbindung zu einem Netzwerk. Ansonsten öffnet er immer wieder den Hotspot und zeigt damit auch nichts anderes an.
Die WiFi Verbindung wird verwendet, um den Controller auch weiterhin updaten zu können.

Es kann auch der **USB-Port** des Pi's verwendet werden (auch für jede andere Serverplattform). Dazu muss man einfach den Server per microUSB-Kabel an den Wemos D1 anschließen.

Bei Verwenudng der **GPIO's** wird der Pi wie folgt mit dem Wemos verbunden:

![image alt text](\assets\pro\AWTRIX_raspi_V2_Steckplatine.jpg)

| Wemos | Raspberry Pin-No | Funktion |
| ----- | ---------------- | -------- |
| 5V    | 04 - 5V          | Spannungsversorgung (+) |
| GND   | 06 - GND         | Spannungsversorgung (-)   |
| RX    | 08 - TXD         | Transmit (senden) |
| TX    | 10 - RXD         | Receive (empfangen)  |

**Bitte zwingend auf die Raspberry Version achten. Hier kann es unterschiede geben!**

Standartmäßig muss beim Raspberry die serielle Schnittstelle freigeschaltet werden, dazu folgende Zeile in der /boot/config.txt eingetragen werden  
`enable_uart=1`


# Gehäuse

## **3D Druck**

Das Gehäuse kann mit einem 3D-Drucker erstellt werden. Die notwendigen Dateien können von [Thingiverse](https://www.thingiverse.com/thing:2791276) heruntergeladen werden.

Die 3D-Objekte sind bereits so ausgerichtet, das möglichst wenig Hilfsmaterial benötigt wird. Das LED-Raster sollte in **Schwarz** gedruckt werden, da sonst die "Pixel" nicht klar getrennt sind, und durch das Material leuchten.

**Empfohlene Druckeinstellungen:**

- 0.2 mm Layerhöhe

- 20% infill

- Support vom Druckbett

- 45-55 mm/s

## **Zusammenbau**

Kleben Sie zunächst die beiden Teile für das LED-Gitter auf der Innenseite zusammen.
Als Diffusor habe ich hochwertiges und dickeres Papier verwendet - es ist wichtig, dass man die Fasern nicht sieht, wenn man sie gegen helles Licht hält wie normales Druckerpapier.
Schmieren Sie dann die flache Seite des LED-Rasters mit Klebestift und kleben Sie das Papier darauf.
Dies ist am besten dort zu tun, wo Awtrix landen wird. Aufgrund hoher Temperatur- und Feuchtigkeitsschwankungen kann sich das Papier leicht verziehen.
Dann die beiden Gehäuseteile zusammensetzen und ggf. mit etwas Kleber fixieren. Löten Sie 2 Kabel an die Buchse und schrauben Sie sie an das Gehäuse. Sie können dann direkt mit der restlichen Verkabelung fortfahren. Der LDR kann durch eine der oberen 5mm Lüftungsöffnungen gesteckt werden. Wenn alles fertig ist, legen Sie den Diffusor nach unten und legen Sie die LED-Matrix darauf, die perfekt in die Nut passen sollte, und drücken Sie das Gehäuse auf das LED-Raster. Dann drehen Sie alles auf der Rückseite um und befestigen Sie den Vorderrahmen.
