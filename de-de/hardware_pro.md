![](\assets\awtrix_pro.jpg)

## Awtrix PRO
Du möchtest dein bisheriges Awtrix-Erlebnis nochmal auf ein ganz anderes Level bringen? Dann ist die Awtrix Pro genau das richtige. Neben der integrierten Soundausgabe kannst du deine Matrix nun auch per Touchsensoren auf der Gehäuseoberseite steuern. Die deutlich kompaktere Bauform und die Verwendung eines professionellen SLA-Drucks lässt die Matrix um ein vielfaches edler aussehen.
Awtrix PRO ist eine Weiterentwicklung der bisherigen großen Awtrix und unterscheidet sich im wesentlichen nur in der Größe. Vom Funktionsumfang können beide Versionen das gleiche. Lediglich das Gehäuse der Pro ist bereits von uns für sämtliche externe Hardware vorbereitet.

Die Software sowie das neue (weiße) Mainboard ist bei beiden Geräten gleich, weshalb hierbei nicht weiter unterschieden werden muss. Die Matrix die hier zum Einsatz kommt ist eine komplette Eigenentwicklung, da diese so in der Form noch nicht auf dem Markt ist. 


## Was ist neu?
- Drei Taster auf der Gehäuseoberseite
- Helligkeitssensor im Gehäuse integriert
- Raspberry Pi (Pi 3, Pi 4) optional im Gehäuse integrierbar
- neues Mainboard im Gehäuse integriert
- 3W Full-Range Lautsprecher im Gehäuse integriert

![](\assets\pro\pro_inside.jpg)

# Teileliste
## Allgemeiner Hinweis
Die Verfügbarkeit der Artikel ändert sich täglich. Daher kann es vorkommen, dass einige Artikel unter dem Link nicht mehr zu finden sind. Allerdings gibt es die Teile von vielen Händlern. Einfach auf Amazon, Ebay oder Aliexpress suchen.

In unserem Shop gibt es die Leiterplatten zu kaufen. Diese sind entweder einzeln, also ohne Bauteile, oder als Bausatz bestellbar. Mit dem Kauf dieser Hardware (diese ist nicht zwingend notwendig) unterstützt ihr uns bei der Weiterentwicklung von Awtrix & Awtrix Pro.


### Bnötigte Bauteile
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | Awtrix Mainboard Bausatz | [click here](https://blueforcer.de/produkt/awtrix-mainboard-2-0-bausatz/) |
| 2  | Pro Matrix               | [click here](https://blueforcer.de/produkt/awtrix-pro-matrix/) |
| 3  | Awtrix Gehäuse           | [click here](https://www.thingiverse.com/thing:4155357) |
| 4  | Wemos D1 mini            | [click here](https://de.aliexpress.com/item/32651747570.html) |
| 5  | Netzteil (>3A)           | [click here](https://goo.gl/QLydM3) |
| 6  | Strombuchse              | [click here](https://goo.gl/j4Xov7) |


### Optionale Bauteile
| Nr | Name                     | Link                            |
| -  |:------------------------:| :------------------------------:|
| 1  | LDR GL5528               | [click here](https://de.aliexpress.com/item/32515315072.html) |
| 2  | DF Mini Player           | [click here](https://de.aliexpress.com/item/32992229288.html) |
| 4  | Lautsprecher             | [click here](https://de.aliexpress.com/item/32853811267.html) |

Die Touchsensoren sind hier nicht mit aufgeführt, weil sie Teil des Awtrix Mainboard Bausatz sind und daher nicht gekauft werden müssen.


# Elektronik

Das Mainboard ist bereits beschriftet und die Bauteile können direkt an die Pads gelötet oder per Stiftleisten verbunden/gesteckt werden.

![](\assets\pro\front.png)


Solltest du Stiftleisten verlötet haben, kannst du jetzt schon das Mainboard, Lautsprecher und den Raspberry in das Gehäuse einbauen. Andernfalls solltest du erst alles zusammenlöten bevor du es einbaust. Die DC-Buchse solltest du auf alle Fälle vor dem Verlöten einbauen um die Gegenmutter anbringen zu können.

!> Nutze für die Spannungsversorgung des Mainboards und der Matrix keine dünnen Kabel, da hier relativ hohe Ströme fließen und durch dünne kabel der Spannungsabfall zu hoch sein kann. Das kann zu Problemen führen.

## Touch-Taster 

Die Touch Sensoren haben auf der kleinen Leiterplatte zwei Brücken die mann mit Lötzinn verschließen kann. Dies wird beim mittleren Sensor zwingend benötigt, da der Wemos ansonsten nicht mehr startet. Um dies zu verhindern muss beim **mittleren Touch Taster die Brücke A geschlossen** werden. Dadurch wird der I/O Pin auf Active Low gestellt. 


## Serielle Verbindung oder USB-Verbindung zur Matrix

Da AWTRIX im Gehäuse verbaut wird, bietet es sich an den Raspberry direkt per Serial an das Mainboard anzuschließen. Hier wird der Raspberry auch vom Mainboard mit Strom versorgt.

> Der Wemos weiterhin zwingend eine Verbindung zu einem Netzwerk.
Die WiFi Verbindung wird verwendet, um den Controller auch weiterhin updaten zu können und als Fallback falls keine Daten per Serial übertragen werden.

Dazu wird der Pi wie folgt mit dem Mainboard verbunden:


| Raspberry Pin-No | Mainboard (Raspberry Serial header) |
| ---------------- | -------- |
| 04 - 5V          | +5V) |
| 06 - GND         | GND   |
| 08 - TXD         | Rx |
| 10 - RXD         | Tx  |

!> **Bitte zwingend auf die Raspberry Version achten. Hier kann es unterschiede geben!**

Standardmäßig muss beim Raspberry die serielle Schnittstelle freigeschaltet werden. Beim Raspberry 3 kann man das über folgende Befehle machen:
```
 sudo raspi-config nonint do_serial 1
 sudo raspi-config nonint set_config_var enable_uart 1 /boot/config.txt
 sudo reboot
```

# Zusammenbau

Für den Zusammenbau sind lediglich maximal 14 **M3x4** Schrauben notwendig. Diese fixieren die Matrix, Mainboard und den Raspberry.

- Die Matrix wird mit 6 Schrauben **handfest** in das Grid geschaubt. Hierbei ist unbedingt die Richtung zu beachten, da die Matrix nur in eine Richtung perfekt im Grid liegt (Äußere Kondensatoren müssen in die dementsprechenden Aussparungen)

- Den Lautsprecher kannst du einfach in die Aussparung stecken und muss daher auch nciht weiter fixiert werden.

- Den LDR steckst du von außen durch das Gehäuse bis er plan mit der Gehäuse Oberseite ist.

- Die Touchsensoren passen theoretisch perfekt in die 3 Aufnahmen. Aufgrund von Drucktoleranzen kann es aber eventuell nötig sein, diese mit doppelseitigen Klebeband zu fixieren oder die Platinen leicht mit Schleifpapier an den Seiten zu glätten.
