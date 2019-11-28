<center><H1>AWTRIX</H1></center>
<br>
<br>

![image alt text](../assets/label.jpg)

<center><small>Unveröffentlichter Protoyp der neusten Hardwaregeneration</small></center>
<br>
<br>

AWTRIX (**AW**esome ma**TRIX**) ist eine Vollfarb-Dot-Matrix, die Anwendungen von der simplen Darstellung der Uhrzeit bis zu Statistiken des Fortnite-Accounts zeigt.

Die Technik dahinter basiert auf wenigen Komponenten, sodass sie auch von Anwendern mit weniger technischem Geschick leicht nachgebaut werden kann. Das Projekt basiert auf einer Matrix mit 32×8 **WS2812B**-LEDs. Angetrieben wird die Matrix von dem WLAN-Mikrocontroller **ESP8266**, der mit einen **Java-basiertem Server** wie Windows, MacOS, Raspberry Pi, etc. kommuniziert. Als Server kann nahezu jedes bestehendes System auf Windows-, MacOS- oder Linux-Basis dienen.
Der Server übernimmt die komplette Logik, während der ESP die Befehle entgegennimmt und anzeigt.  
Dieses Gespann hat seine Gründe:

- Der ESP ist um ein vielfaches schneller um die Zeichenroutinen zu berechnen.
- Der ESP ist nicht Leistungsstark genug um alle Funktionen alleine abbilden zu können.
- Die Host Software kann fast überall ausgeführt werden (z.B bestehender Server, NAS, VPS, Raspberry usw.)

Natürlich schreit so ein Projekt danach, mit dem Einplatinenrechner **Raspberry Pi** zu laufen. Der Vorteil: der Server kann direkt mit in das Gehäuse eingebaut werden und es ergibt sich ein kleines aber nicht minder feines, autark funktionierendes System. Ein **druckbares Gehäuse** habe ich auf der 3D-Druckplattform Thingiverse bereitgestellt und viele kreative User haben eigene Entwürfe beigesteuert. Die Projekte der äußerst aktiven Community gibt es in unserem Forum zu sehen, darunter Installationen in Holzgehäusen, unter Glastischen und vieles mehr. Awtrix 2.0 ist der Nachfolger der Version 1.0 und mit viel Input aus der Community entstanden.

### Anzeige für alles

Die Hardware lässt sich auch erweitern und um zusätzliche Funktionen ergänzen. Helligkeitssensoren zur automatischen Anpassung der Leuchtkraft, ein Modul zur Tonausgabe sowie die Steuerung über Taster seien hier genannt. Nach Zusammenbau der Komponenten und Einrichtung der Software erfolgt die weitere Steuerung über den integrierten Webserver. Dieser kommuniziert entweder über WLAN oder über die serielle Schnittstelle (microUSB oder TX/RX) mit dem ESP8266. Eine eigene Platine ist ebenfalls bereits im Shop verfügbar.

Neben einfachen Funktionen wie Stoppuhr und Timer baut das Projekt hauptsächlich auf Apps auf, die es im integrierten App Store kostenlos zum Herunterladen gibt. Das können Wetterdaten, Facebook- oder Instagram-Likes oder auch Spiele wie Snake oder Pong sein. Letztere werden über das Webinterface auf dem Smartphone gesteuert. Auch die Einbindung in eine Heimautomatisierung wie FHEM, HomeAssistant oder ähnliches ist möglich. Fehlt eine App, kann man sie einfach selbst schreiben und zur Veröffentlichung einreichen. Dank der sehr gut dokumentierten API und Schnittstellen für die IoT-Protokolle REST und MQTT lassen sich beliebige Informationen an die Matrix senden. Ob Temperatur, Luftfeuchtigkeit, Stromverbrauch oder einfach nur der Song, der gerade auf Spotify läuft – alles kein Problem.

Bei der Anzeige hilft ein weiteres Feature: der Awtrixer. Mit diesem integrierten Programm lassen sich Icons für Awtrix herstellen, deren Größe individuell einstellbar ist. Von 8×8 bis zu 8×32 Pixeln ist man frei in der Gestaltung und kann alternativ vorhandene Bilder von 8×8 Pixeln automatisch umwandeln lassen. Auch animierte Icons sind kein Problem. Selbsterstellte Icons können mit der Community geteilt.

Und wem die lokale Ansteuerung aus dem Netzwerk noch nicht reicht, dem sei die Verbindung zur Awtrix-Cloud empfohlen, mit der unter anderem eine komplett anonyme Anbindung von externer Quelle wie z.B den Verknüpfungsienst IFTTT und seine unzähligen Receipts möglich ist.

**Zusammengefasste Funktionen**

- Plattformunabhängig
- Vollständige Konfiguration über Webinterface
- Apps können über den integrierten Appstore hinzugefügt werden.
- Flexibles App-Management
- Unterstützung für Community-Apps
- leistungsfähige API-Schnittstellen mit MQTT und REST
- volle Kontrolle über Smarthome oder Webinterface
- Automatische Helligkeitsregelung
- Timer- und Stoppuhrfunktion
- AWTRIX-Nodes, um ein eigenes kleines Smarthome aufzubauen.
- Unterstützt USB- oder Wifi-Verbindung zur Matrix

**Premium Funktionen**

- Cloud-Anbindung für externe Dienste wie IFTTT (https://awtrix.blueforcer.de/)
- SleepMode
- Fritz!Box Call Monitor
- PushOver client
- Wecker
