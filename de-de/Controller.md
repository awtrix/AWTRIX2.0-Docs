

!> **Bei der aktuellen Controller Firmware ist es nicht notwendig eine Config Datei zu verändern**. Alle Einstellungen können nun ganz bequem per Hotspot eingestellt werden.
Hier in dieser Anleitung ist beschrieben, wie eine fertige .bin Datei auf den ESP8266 geflasht werden kann. Das Kompilieren des Quellcodes (wie früher notwendig) wird hier nicht weiter beschrieben.

## Flashen

### Flashen unter Windwos
![image alt text](\assets\firmware\flashingTool.PNG)

1. Lade dir das Flashing Tool [hier](https://www.espressif.com/sites/default/files/tools/flash_download_tools_v3.6.7_1.zip) herunter.
2. Entpacke das heruntergeladene Programm und starte es.
3. Lade dir die aktuelle Firmware.bin Datei von [hier](https://blueforcer.de/downloads/firmware.bin) herunter.
4. Selle den richtigen Com-Port im unteren Bereich des Programms ein.
5. Lösche deinen Controller durch betätigen des ERASE Buttons. Nach kurzer Zeit sollte im unteren grünen Feld FINISH stehen. (Wenn bereits vorher eine andere Version von Awtrix auf dem Controller war und der Controller nicht gelöscht wurde, behält der Conotroller seine Einstellungen. Dies führt zu Problemen.)
6. Hinterlege den Pfad zu der heruntergladenen firmware.bin Datei im oberen Bereich des Programms. Rechts neben dem Pfad muss noch die Adresse "0x000000" eingetragen werden.
7. Firmware flashen durch betätigen des START Buttons.
8. Resette deinen Controller.

### Flashen unter Linux

### Flashen unter MacOS

## Erster Start
![image alt text](\assets\firmware\wifiSearch.gif)

Für ein paar Sekunden such der Controller nun nach einem bekannten WiFi Netzwerk. Da der Controller jedoch neu/gelöscht wurde, sind ihm keine Netzwerke bekannt.
<br>
<br>

![image alt text](\assets\firmware\hotspot.gif)

Nach erfolgloser Suche nach einem Netzwerk kommt nun der Text "Hotspot" auf der Matrix. Wie der Name schon sagt, macht der Controller nun einen WLAN Hotspot auf. Mit einem beliebigen WLAN gerät kann der Controller nun über den Hotspot konfiguriert werden.
1. Verbinde dich mit dem WLAN mit der SSID "**AWTRIX Controller**".
2. Das WLAN Passwort lautet "**awtrixxx**"
3. Wenn sich nicht automatisch eine Webseite öffnet, kann unter der IP "**172.217.28.1**  über einen belibiegen Browser auf die Einstellungsseite navigiert werden. Diese Seite sieht wie folgt aus:

![image alt text](\assets\firmware\hotspotConfig1.jpg)
![image alt text](\assets\firmware\hotspotConfig2.jpg)


4. Durch klicken auf "Conigure WiFi" (linkes Bild) gelangt man auf die eingentliche Einstellungsseite (rechtes Bild).
5. **SSID** und **Passwort** eures WLANs muss in die dafür vorgeshenen felder eingetragen werden. **Der Controller braucht zwingend ein WLAN - ansonsten startet er nicht**

<br>
<br>