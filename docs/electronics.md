---
id: electronic
title: Elektronik
---

Die Elektronik kann entweder auf eine Lochrasterplatine gelötet ("frei verdrahtet") werden oder auf der extra für Awtrix entwickelten Leiterplatte. Die genauen Details zu den benötigten Bauteilen bitte der [Teileliste](../AWTRIXpro/partlistPro) entnehmen.

## Basis Variante

![Basissetup](..\assets\pro\AWTRIX_Core_Steckplatine.jpg)

## Lichtsensor zur Helligkeitsregelung (optional)
Der Helligkeitssensor kann optinal eingebaut werden. Dieser sorgt dafür, dass beispielsweise in einem dunklen Raum, durch herunter dimmen der Helligkeit, die Matrix nicht blendet . Anders herum wird die Matrix bei einer hohen Helligkeit im Raum hoch gedimmt, damit man den Inhalt der Matrix noch lesen kann.

![ldr](..\assets\pro\AWTRIX_LDR_Steckplatine.jpg)

## DFPlayer Mini zur Soundausgabe (optional)
Der DFPlayer dient zur Ausgabe von Sounds und ist optinal verwendbar. Es werden mp3 Dateien auf einer Speicherkarte gespeichert, welche in das Micro-SD Fach des Players eingesteckt wird. Dies ermöglicht es dir, dass deine Matrix beispielsweise mit dir spricht. Das hinzufügen von mp3 Dateien kann leider nur über die SD Karte am PC erfolgen. Ein hochladen vom Server oder ähnliches ist technisch leider nicht möglich.

![image alt text](..\assets\pro\AWTRIX_DFMini_Steckplatine.jpg)

| Wemos | DFPlayer Mini | Funktion | Hinweis  |
| ----- | ------------- | -------- | -------- |
| 5V    | VCC           | Spannungsversorgung (+)    |          |
| G     | GND           | Spannungsversorgung (-)   |          |
| D7    | TX            | Transmit (senden) |          |
| D5    | RX            | Receive (empfangen)  | früher D8 |

## Temperatur- und Luftfeuchtigkeitssensor (optional)
Optinal kann Awtrix mit zwei verschiedenen Raumklimasensoren arbeiten. Hierbei kann frei gewählt werden ob der BME280 oder der Htu21d zum Einsatz kommen soll. Die gemessenen Werte werden dem Server geschickt und können zum Einen mittels App direkt auf der Matrix angezeigt werden und zum Anderen von einem Hausautomationsserver (ioBroker, FHEM, ...) mittels API vom Awtrix Server abgerufen werden.

![image alt text](..\assets\pro\AWTRIX_Temp_Steckplatine.jpg)

| Wemos | BME280 | Htu21d | Funktion | Hinweis  |
| --- | --- | --- | --- |--- |
| 3.3V | VCC |  VCC |Spannungsversorgung (+) | nicht 5V kompatibel! |
| GND | GND | GND |Spannungsversorgung (-) | |
| D3 | SDA | SDA |I2C Daten | |
| D1 | SCL | SCL |I2C Takt | |

Bei Verwendung von Temperatur- und Gestensensor werden die Pins D1 & D3 des Wemos D1 mini doppelt verwendet (I2C Bus).

## Touch-Taster zur Bedienung (optional)

![image alt text](..\assets\pro\AWTRIX_Touch_Steckplatine.jpg)

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

![image alt text](..\assets\pro\AWTRIX_Gesture_Steckplatine.jpg)

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

![image alt text](..\assets\pro\AWTRIX_raspi_V2_Steckplatine.jpg)

| Wemos | Raspberry Pin-No | Funktion |
| ----- | ---------------- | -------- |
| 5V    | 04 - 5V          | Spannungsversorgung (+) |
| GND   | 06 - GND         | Spannungsversorgung (-)   |
| RX    | 08 - TXD         | Transmit (senden) |
| TX    | 10 - RXD         | Receive (empfangen)  |

**Bitte zwingend auf die Raspberry Version achten. Hier kann es unterschiede geben!**

Standartmäßig muss beim Raspberry die serielle Schnittstelle freigeschaltet werden, dazu folgende Zeile in der /boot/config.txt eingetragen werden  
`enable_uart=1`
