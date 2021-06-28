Wenn du keine Lust auf eine fliegende Verdrahtung im Gehäuse hast, [kannst du eine geeignete Platine in meinem Shop erwerben](https://blueforcer.de/shop/).

## Bestückungsplan

![B4J](../assets/pcb.jpg)

| Nr | Stück | Name | Teilenummer (reichelt.de) | Kommentar
| -  | - |:------------------------:| :------------------------------:| |
| **1**  | 2 | diode (1N4004) |1N 4004 |
| **2**  | 3 | resistor (1k Ohm)| VIS C1001FC100 | |
| **3**  | 1 | Capacitor (1000uF)| M-A 1000U 16 | **Liegend verbauen** |
| **4**  | 1 | Capacitor (100nF)| KERKO 100N |  |
| **5**  | 1 | pinheader male (1x3) |  MPE 087-1-036 | |
| **6**  | 4 | pinheader male (1x8)  |  MPE 087-1-036 | |

## Bilderanleitung zum Bestücken des Mainboards

### 1. Bauteile im Überblick
![B4J](../assets/manualPicture/mainboard/uebersicht.jpg)
- Die Touch Sensoren sowie der DFPlayer sind optionale Teile und sind nicht zwingend zum Betrieb erforderlich.
- Zum verlöten der Bauteile wird ein Lötkolben samt Lötzinn benötigt.
- Beim Bestücken arbeitet man sich von den kleinen zu den großen Bauteilen vor.

### 2. Widerstände (R1, R2, R3)
![B4J](../assets/manualPicture/mainboard/widerstaende.jpg)
- Alle drei Widerstände haben den gleichen Widerstandswert (1k Ohm).
- Widerstände besitzen keine Polarität, daher ist es egal wie rum man das Bauteil einlötet.
- Widerstände biegen und einstecken.
- Etwas drunter legen damit die Bauteile durchgesteckt werden können.
- Von oben auf einer Seite anlöten.
- Andere Seite des Widerstandes von unten festlöten.
- Die erste Seite von unten nochmal nachlöten.
- Beinchen der Widerstände kürzen.

### 3. Dioden (D1, D2)
![B4J](../assets/manualPicture/mainboard/dioden.jpg)
- Dioden haben eine Polarität, welche sehr wichtig ist und beachtet werden muss.
- Dioden biegen und einstecken.
- Etwas drunter legen damit die Bauteile durchgesteckt werden können.
- Von oben auf einer Seite anlöten.
- Andere Seite der Diode von unten festlöten.
- Die erste Seite von unten nochmal nachlöten.
- Beinchen der Dioden kürzen.

Richtig eingelötet sieht es wie folgt aus:
![B4J](../assets/manualPicture/mainboard/dioden2.jpg)

### 4. Kleiner Kondensator (C2)
![B4J](../assets/manualPicture/mainboard/kleinerKondensator.jpg)
- Dieser Kondensator besitzt keine Polarität, daher ist es egal wie rum er eingebaut wird.
- Kondensator biegen und einstecken.
- Von oben auf einer Seite anlöten.
- Andere Seite des Kondensators von unten festlöten.
- Die erste Seite von unten nochmal nachlöten.
- Beinchen des Kondensators kürzen.

### 5. Stiftleiste (1x 3-polig)
![B4J](../assets/manualPicture/mainboard/stiftleiste3pol.jpg)
- Einstecken, Platine umdrehen und so hinlegen das die Stiftleiste nicht heraus fällt.
- Ersten Pin von unten festlöten - Ausrichtung der Stiftleiste erfolgt anschließend.
- Mit dem Fingernagel den schwarzen Teil der Stiftleiste von oben nach unten drücken während mit der anderen Hand mittels Lötkolben die erste gelötete Stelle noch einmal heiß gemacht wird.
- Nun sollte die Stiftleiste gerade sein. Falls nicht vorgang wiederholen.
- Die anderen Pins der Stiftleiste festlöten.
- **Diese Stiftleiste ermöglicht es dir die Spannungsversorgung für deinen I2C-Bus variable zwischen 3,3V und 5V umzuschalten. Hierzu wird ein Jumper verwendet.**

### 6. Buchsenleisten (4x 8-polig)
![B4J](../assets/manualPicture/mainboard/buchsenleiste.jpg)
- Einstecken, Platine umdrehen und so hinlegen das die Buchsenleiste nicht heraus fällt.
- Ersten Pin von unten festlöten - Ausrichtung der Stiftleiste erfolgt anschließend.
- Mit dem Fingernagel den schwarzen Teil der Buchsenleiste von oben nach unten drücken während mit der anderen Hand mittels Lötkolben die erste gelötete Stelle noch einmal heiß gemacht wird.
- Nun sollte die Buchsenleiste gerade sein. Falls nicht vorgang wiederholen.
- Die anderen Pins der Buchsenleiste festlöten.
- Nach dem gleichen Prinzip die weiteren drei Buchsenleisten einlöten

### 7. Großer Kondensator (C1)
![B4J](../assets/manualPicture/mainboard/groesserKondensator.jpg)
- **Dieser Kondensator muss FLACH eingebaut werden. Ansonsten ist er zu hoch für das Awtrix Gehäuse.**
- Kondensator hat auf einer Seite einen weißen strich. Dieser kennzeichnet den Minus-Pol.
- Kondensator auf die Platine legen. Minuspol des Kondensators muss in den Pin der von einer schwarzen Fläche umrandet ist.
- Beinchen 90 Grad nach unten biegen.
- Kondensator einstecken und eine von oben eine Seite festlöten.
- Andere Seite des Kondensators von unten festlöten.
- Die erste Seite von unten nochmal nachlöten.
- Beinchen des Kondensators kürzen.

Richtig eingelötet sieht es wie folgt aus:
![B4J](../assets/manualPicture/mainboard/groesserKondensator2.jpg)

### 8. DFPlayer
![B4J](../assets/manualPicture/mainboard/dfPlayer.jpg)
- Stiftleiste an DFPlayer einstecken. (Falls diese nicht ohnehin schon dran gelötet ist)
- Zum Anlöten kann die Stiftleiste in die bereits eingelötete Buchsenleiste gesteckt werden.
- DFPlayer auf die Stiftleiste, welche in der Buchsenleiste steckt, setzen und anlöten.

### 9. Wemos D1 mini
![B4J](../assets/manualPicture/mainboard/wemos.jpg)
- Stiftleisten in den Wemos D1 mini stecken.
- Stiftleiste muss dabei nach unten schauen während der Microcontroller samt Antenne nach oben schauen muss.
- Zum Anlöten kann die Stiftleiste in die bereits eingelötete Buchsenleiste gesteckt werden.
- Wemos D1 mini auf die Stiftleiste, welche in der Buchsenleiste steckt, setzen und anlöten.

Richtig eingelötet sieht es wie folgt aus:
![B4J](../assets/manualPicture/mainboard/wemos2.jpg)

### 10. FERTIG
- Die Komponenten die an das Mainboard angeschlossen werden können sind unter Awtrix Pro Zusammenbau in einer weiteren Bilderanleitung aufgeführt.
