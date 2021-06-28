![AWTRIX Pro](../assets/family.jpg)

### AWTRIX
(**AW**some ma**TRIX**) ist eine Vollfarb-Dot-Matrix, die Anwendungen von der simplen Darstellung der Uhrzeit bis zu Statistiken des Fortnite-Accounts anzeigt.

Die Technik dahinter basiert auf wenigen Komponenten, sodass sie auch von Anwendern mit weniger technischem Geschick leicht nachgebaut werden kann. Das Projekt. Angetrieben wird die Matrix (32 × 8 WS2812B-LEDs) von dem WLAN-Mikrocontroller ESP8266, der mit einen Java-basiertem Host kommuniziert. Als Host kann nahezu jedes bestehendes System auf Windows-, MacOS- oder Linux-Basis dienen.

Natürlich schreit so ein Projekt danach, mit dem Einplatinenrechner Raspberry Pi zu laufen. Der Vorteil: der Server kann direkt mit in das Gehäuse eingebaut werden und es ergibt sich ein kleines aber nicht minder feines, autark funktionierendes System. Ein druckbares Gehäuse habe ich auf der 3D-Druckplattform Thingiverse bereitgestellt und viele kreative User haben eigene Entwürfe beigesteuert. Die Projekte der äußerst aktiven Community gibt es [**auf Discord zu sehen**](https://discord.com/invite/EhzeZDyspzs), darunter Installationen in Holzgehäusen, unter Glastischen und vieles mehr. Awtrix 2.0 ist der Nachfolger der Version 1.0 und mit viel Input aus der Community entstanden.

### Anzeige für alles
Die Hardware lässt sich auch erweitern und um zusätzliche Funktionen ergänzen. Helligkeitssensoren zur automatischen Anpassung der Leuchtkraft, ein Modul zur Tonausgabe sowie eine Steuerung über kapazitive Taster seien hier genannt. Nach Zusammenbau der Komponenten und Einrichtung der Software erfolgt die weitere Steuerung über den integrierten Webserver. Dieser kommuniziert entweder über WLAN oder über die serielle Schnittstelle (USB oder TX/RX) mit dem ESP8266. Eine eigene Platine ist ebenfalls im [**Shop**](https://blueforcer.de/shop/) zu erwerben.

Neben einfachen Funktionen wie Stoppuhr und Timer baut das Projekt hauptsächlich auf Apps auf, die es im integrierten App Store kostenlos zum Herunterladen gibt. Das können Wetterdaten, Facebook- oder Instagram-Likes oder auch Spiele wie Snake oder Pong sein. Letztere werden über die das Smartphone oder am Browser (optional mit angeschlossenem Gamepad) gesteuert. Auch die Einbindung in eine Heimautomatisierung wie FHEM, Home Assistant oder ähnliches ist möglich. Fehlt eine App, kann man sie einfach selbst schreiben und zur Veröffentlichung einreichen werden.
Dank der sehr gut dokumentierten API und Schnittstellen für die Protokolle HTTP und MQTT lassen sich beliebige Informationen an die Matrix senden. Ob Temperatur, Luftfeuchtigkeit, Stromverbrauch oder einfach nur der Song, der gerade auf Spotify läuft – alles kein Problem. Und wem die lokale Ansteuerung aus dem Netzwerk noch nicht reicht, dem sei die Verbindung zur Awtrix-Cloud empfohlen, mit der **unter anderem** eine komplett anonyme Anbindung an den Verknüpfungsdienst IFTTT und seine unzähligen Receipts möglich ist.

Bei der Erstellung eigener Notifications hilft ein weiteres Feature: der Awtrixer. Mit diesem mächtigen integrierten Tool lassen sich Icons für die Awtrix herstellen und kann alternativ vorhandene Bilder von 8×8 Pixeln automatisch umwandeln lassen. Auch animierte Icons sind kein Problem. Selbsterstellte Icons werden mit der Community geteilt. Awtrixer ist im Host Webinterface erreichbar

**Die wichtigsten Funktionen von AWTRIX kurz und knapp**

- Plattformunabhängig
- API Schnittstellen für MQTT und HTTP
- Anzeige von Notifications aus dem Smarthome oder andere externe Services
- Zugriff auf die Icon Datenbank
- Integrierter Appstore
- Anpassung der Appschleife
- Anpassung der Farbkorrektur für die Matrix
- AWTRIX Arcade für kleinere Spiele auf der Matrix
- Update des Controllers und Hosts über das Webinterface
- Stoppuhr
- Timer

**Premium Funktionen**
- Fritz!Box CallMonitor
- Steuerung deiner AWTRIX über die AWTRIX Cloud
- Pushover Client
- Wecker
- Schlafmodus
