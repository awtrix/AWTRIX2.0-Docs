!> **Bei der aktuellen Controller Firmware ist es nicht notwendig eine Config Datei zu verändern**.  
Alle Einstellungen können nun ganz bequem per Hotspot eingestellt werden.
Hier in dieser Anleitung ist beschrieben, wie eine fertige .bin Datei auf den ESP8266 geflasht werden kann. Das Kompilieren des Quellcodes (wie früher notwendig) wird hier nicht weiter beschrieben.

## Flashen

### Flashen unter Windwos
![](\assets\firmware\flashingTool.PNG)

1. Lade dir das Flashing Tool [hier](https://www.espressif.com/sites/default/files/tools/flash_download_tools_v3.6.7_1.zip) herunter.
2. Entpacke das heruntergeladene Programm und starte es.
3. Lade dir die aktuelle Firmware.bin Datei von [hier](https://blueforcer.de/awtrix/beta/firmware.bin) herunter.
4. Selle den richtigen Com-Port im unteren Bereich des Programms ein.
5. Lösche deinen Controller durch betätigen des ERASE Buttons. Nach kurzer Zeit sollte im unteren grünen Feld FINISH stehen. (Wenn bereits vorher eine andere Version von Awtrix auf dem Controller war und der Controller nicht gelöscht wurde, behält der Conotroller seine Einstellungen. Dies führt zu Problemen.)
6. Hinterlege den Pfad zu der heruntergladenen firmware.bin Datei im oberen Bereich des Programms. Rechts neben dem Pfad muss noch die Adresse "0x000000" eingetragen werden.
7. Firmware flashen durch betätigen des START Buttons.
8. Resette deinen Controller.

### Flashen unter Linux & MacOS

Hierfür kann das ESPTool verwendet werden
``` BASH
 git clone https://github.com/themadinventor/esptool.git
``` 
Wenn du kein git hast, kannst du es mit dem entsprechenden Befehl herunterladen:  
[Installation von git auf verschiedenen Distributionen](http://git-scm.com/download/linux)

Wir benötigen auch Python auf unserem System, um dieses Skript mit dem seriellen Paket auszuführen (es sollte bereits installiert sein, aber nur für alle Fälle).

Im Terminal ändern wir den aktuellen Ordner in den Pfad des esptool-Ordners und geben diesen Befehl ein, um die Firmware herunterzuladen:

``` BASH
sudo wget -h https://blueforcer.de/awtrix/beta/firmware.bin
```
Anschließend wird der Flashprozess gestartet

``` BASH
sudo python esptool.py --port /dev/ttyUSB0 write_flash 0x00000 firmware.bin
``` 
Beachte, dass sich **/dev/ttyUSB0** je nach dem von Ihnen verwendeten UART und der von Ihnen gewählten Linux-Distribution ändern kann.

Wenn nach einigen Sekunden ähnliche Outputs zu lesen sind:
``` BASH
Connecting.....
Erasing flash..... 
Writing at 0x00000000... (0 %)
``` 
Dann ist alles in Ordnung....
Wenn es nach ein paar Sekunden nicht ankommt.... hast möglicherweise ein Problem mit dem Anschluss des ESP8266 an den UART.


## Erster Start
![](\assets\firmware\wifiSearch.gif)

Für ein paar Sekunden sucht der Controller nun nach einem bekannten WiFi Netzwerk. 
<br>
<br>

![](\assets\firmware\hotspot.gif)

Wenn noch keine Wifi.Verbindung konfiguriert ist kommt nun der Text "Hotspot" auf der Matrix. Wie der Name schon sagt, macht der Controller nun einen WLAN Hotspot auf. Mit einem beliebigen WLAN Gerät kann der Controller nun über den Hotspot konfiguriert werden.
1. Verbinde dich mit dem WLAN mit der SSID "**AWTRIX Controller**".
2. Das WLAN Passwort lautet "**awtrixxx**"
3. Wenn sich nicht automatisch eine Webseite öffnet, kann unter der IP "**172.217.28.1**  über einen beliebigen Browser auf die Einstellungsseite navigiert werden. Diese Seite sieht wie folgt aus:

<div align=center>
<img width="200" src="de-de\assets\firmware\hotspotConfig1.jpg"/>
<img width="200" src="de-de\assets\firmware\hotspotConfig2.jpg"/>
</div>


4. Durch klicken auf "Conigure WiFi" (linkes Bild) gelangt man auf die eingentliche Einstellungsseite (rechtes Bild).
5. **SSID** und **Passwort** eures WLANs muss in die dafür vorgeshenen Felder eingetragen werden. **Der Controller braucht zwingend ein WLAN - ansonsten startet er nicht**

<br>
<br>