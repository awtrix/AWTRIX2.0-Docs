![](..\assets\awtrix_pro.jpg)

## Awtrix PRO
Du möchtest dein bisheriges Awtrix-Erlebnis nochmal auf ein ganz anderes Level bringen? Dann ist die Awtrix Pro genau das richtige. Neben der integrierten Soundausgabe kannst du deine Matrix nun auch per Touchsensoren auf der Gehäuseoberseite steuern. Die deutlich kompaktere Bauform und die Verwendung eines professionellen SLA-Drucks lässt die Matrix um ein vielfaches edler aussehen.
Awtrix PRO ist eine Weiterentwicklung der bisherigen großen Awtrix und unterscheidet sich im wesentlichen nur in der Größe. Vom Funktionsumfang können beide Versionen das gleiche. Lediglich das Gehäuse der Pro ist bereits von uns für sämtliche externe Hardware vorbereitet.

Die Software sowie das neue (weiße) Mainboard ist bei beiden Geräten gleich, weshalb hierbei nicht weiter unterschieden werden muss. Die Matrix die hier zum Einsatz kommt ist eine komplette Eigenentwicklung, da diese so in der Form noch nicht auf dem Markt ist. 


## Was ist neu?
- Kleinere Matrix (190 x 55 mm)
- Drei Taster auf der Gehäuseoberseite
- Helligkeitssensor im Gehäuse integriert
- Raspberry Pi (Pi 3, Pi 4) optional im Gehäuse integrierbar
- neues Mainboard im Gehäuse integriert
- 3W Full-Range Lautsprecher im Gehäuse integriert

![](..\assets\pro\pro_inside.jpg)

# Gehäuse

Die nötigen Dateien zum 3D-Druck des Gehäuses findest du auf [Thingiverse](https://www.thingiverse.com/thing:4155357)

Als Frontpanel ist eine 2mm dicke Plexiglasscheibe vorgesehen. Die passende DXF zum Fräsen findest du ebenfalls auf Thingiverse. Diese steht momentan noch nicht zum offiziellen Verkauf. Zwischen der Scheibe und dem Matrixgrid wird ein Stück Papier als Diffusor geklemmt.
  
  <div align=center>
  <img width="400" src="..\assets\pro\plexi.jpg"/>
  </div>

Solltest du nicht dier Möglichkeit haben, dir solche ine platte zu fräsen. Gibt es ebenfalls auf Thiniverse einen Adapter Rahmen mit dem du ein Stück Papier als Diffusor einspannen kannst.
  <div align=center>
  <img width="400" src="..\assets\pro\adapter.jpg"/>
  </div>

# Elektronik
## Teileliste

!> **Allgemeiner Hinweis**
Die Verfügbarkeit der Artikel ändert sich täglich. Daher kann es vorkommen, dass einige Artikel unter dem Link nicht mehr zu finden sind. Allerdings gibt es die Teile von vielen Händlern. Einfach auf Amazon, Ebay oder Aliexpress suchen.

In unserem Shop gibt es die Leiterplatten zu kaufen. Diese sind entweder einzeln, also ohne Bauteile, oder als Bausatz bestellbar. Mit dem Kauf dieser Hardware (diese ist nicht zwingend notwendig) unterstützt ihr uns bei der Weiterentwicklung von Awtrix & Awtrix Pro.


### Bnötigte Bauteile
| Nr  |           Name           |                                    Link                                    |
| --- | :----------------------: | :------------------------------------------------------------------------: |
| 1   | Awtrix Mainboard Bausatz | [Klicke hier](https://blueforcer.de/produkt/awtrix-mainboard-2-0-bausatz/) |
| 2   |        Pro Matrix        |      [Klicke hier](https://blueforcer.de/produkt/awtrix-pro-matrix/)       |
| 3   |      Awtrix Gehäuse      |          [Klicke hier](https://www.thingiverse.com/thing:4155357)          |
| 4   |      Wemos D1 mini       |       [Klicke hier](https://de.aliexpress.com/item/32651747570.html)       |
| 5   |      Netzteil (>3A)      |                    [Klicke hier](https://goo.gl/QLydM3)                    |
| 6   |       Strombuchse        |                    [Klicke hier](https://goo.gl/j4Xov7)                    |


### Optionale Bauteile
| Nr  |      Name      |                              Link                              |
| --- | :------------: | :------------------------------------------------------------: |
| 1   |   LDR GL5528   | [Klicke hier](https://de.aliexpress.com/item/32515315072.html) |
| 2   | DF Mini Player | [Klicke hier](https://de.aliexpress.com/item/32992229288.html) |
| 4   |  Lautsprecher  | [Klicke hier](https://de.aliexpress.com/item/32853811267.html) |

Die Touchsensoren sind hier nicht mit aufgeführt, weil sie Teil des Awtrix Mainboard Bausatz sind und daher nicht gekauft werden müssen.


# Mainboard

Das Mainboard ist bereits beschriftet und die Bauteile können direkt an die Pads gelötet oder per Stiftleisten verbunden/gesteckt werden.


  <div align=center>
  <img width="400" src="..\assets\pro\front.png"/>
  </div>

**Eine Ausführliche Anleitung zum Bestücken des Mainboards [findest du hier](/de-de/pcb.md)**

Solltest du Stiftleisten verlötet haben, kannst du jetzt schon das Mainboard, Lautsprecher und den Raspberry in das Gehäuse einbauen. Andernfalls solltest du erst alles zusammenlöten bevor du es einbaust. Die DC-Buchse solltest du auf alle Fälle vor dem Verlöten einbauen um die Gegenmutter anbringen zu können.

!> Nutze für die Spannungsversorgung des Mainboards und der Matrix keine dünnen Kabel, da hier relativ hohe Ströme fließen und durch dünne kabel der Spannungsabfall zu hoch sein kann. Das kann zu Problemen führen.

## AWTRIX Pro Matrix

Diese Matrix ist vorrangig für AWTRIX entwickelt worden. Um Kosten bei der Produktion zu sparen wurde bei der Platine auf einen Aluminium Kern verzichtet.
Stattdessen wurde die Rückseite großzügig mit Masseflächen versehen um die Wärme abzutransportieren. Dennoch ist die Matrix nicht für die volle LED Leistung ausgelegt.

!> Steuere niemals für einen längeren Zeitraum und hoher Helligkeit alle 256 LEDs auf einmal an. Dies kann aufgrund der Hitzeentwicklung zu Schäden der Matrix führen.

Die große Masseflächen wirken wie ein Bi-Metall, daruch kommt es im Reflow Ofen (Lötvorgang) zu einer leichten Verformung der Platine. Dies wirkt sich jedeoch nicht auf die Funktionsweise aus, und wird durch die Verschraubung im Gehäuse wieder begradigt.

## Touch-Taster 

!> Die Touch Sensoren haben auf der kleinen Leiterplatte zwei Brücken die mann mit Lötzinn verschließen kann. Dies wird beim mittleren Sensor zwingend benötigt, da der Wemos ansonsten nicht mehr startet. Um dies zu verhindern muss beim **mittleren Touch Taster die Brücke A geschlossen** werden. Dadurch wird der I/O Pin auf Active Low gestellt. 

  <div align=center>
  <img width="100" src="..\assets\touch.jpg"/>
  </div>

## Serielle Verbindung oder USB-Verbindung zur Matrix

Da AWTRIX im Gehäuse verbaut wird, bietet es sich an den Raspberry direkt per Serial an das Mainboard anzuschließen. Hier wird der Raspberry auch vom Mainboard mit Strom versorgt.

> Der Wemos weiterhin zwingend eine Verbindung zu einem Netzwerk.
Die WiFi Verbindung wird verwendet, um den Controller auch weiterhin updaten zu können und als Fallback falls keine Daten per Serial übertragen werden.

Dazu wird der Pi wie folgt mit dem Mainboard verbunden:


| Raspberry Pin-No | Mainboard (Raspberry Serial header) |
| ---------------- | ----------------------------------- |
| 04 - 5V          | +5V)                                |
| 06 - GND         | GND                                 |
| 08 - TXD         | Rx                                  |
| 10 - RXD         | Tx                                  |

!> **Bitte zwingend auf die Raspberry Version achten. Hier kann es unterschiede geben!**

Standardmäßig muss beim Raspberry die serielle Schnittstelle freigeschaltet werden. Beim Raspberry 3 kann man das über folgende Befehle machen:
```
 sudo raspi-config nonint do_serial 1
 sudo raspi-config nonint set_config_var enable_uart 1 /boot/config.txt
 sudo reboot
```

## DFPlayer

Der DFPlayer dient zur Ausgabe von Sounds und ist optional verwendbar. Es werden mp3 Dateien auf einer Speicherkarte gespeichert, welche in das Micro-SD Fach des Players eingesteckt wird. Dies ermöglicht es dir, dass deine Matrix beispielsweise mit dir spricht oder Töne bei Benachrichtigungen abspielt.  
  
Du musst einen Ordner “MP3” auf deiner DFplayer SD-Karte erstellen und deine mp3s in diesen Ordner verschieben. Die mp3 muss mit einer 4-stelligen Zahl beginnen, z.B. **0001.mp3** oder **0001 - Testfile.mp3**.  
AWTRIX verwendet den Bereich 0001-0100 für interne Zwecke. Beginne mit eigenen mp3s bei 0101.  
[Standardsounds herunterladen](https://blueforcer.de/awtrix/Soundfiles.zip)



# Zusammenbau

Diese Anleitung bezieht sich nicht auf den Einbau eines Raspberry Pis. Die korrekte Verkabelung entnimmst du bitte weiter oben.

## 1. Touch Sensoren
- Der Widerstand der LED auf dem Touch Taster kann optional ausgelötet werden.
- Bei hellem Gehäuse kann das Licht der LED sonst von außen gesehen werden.
- Beim mittleren Taster leuchtet die LED, bei nicht entfernen des Widerstandes, dauerhaft.
- Die Touchsensoren passen theoretisch perfekt in die 3 Aufnahmen. Aufgrund von Drucktoleranzen kann es aber eventuell nötig sein, diese mit doppelseitigen Klebeband zu fixieren oder die Platinen leicht mit Schleifpapier an den Seiten zu glätten.

### 1.1 Linker Touch Sensor (btn_left)
- 3 Kabel auf ca. 14cm Ablängen. Falls vorhanden, drei verschiedene Farben. 
- Kabelenden auf beiden seiten ca. 2mm abisolieren, verdrillen und verzinnen.
- Kabel NICHT durch die Löcher des Touch Sensors stecken sondern nur von oben auflegen und anlöten. (schwarz = GND ; rot = 3,3V/VCC ; grün = Data/IO)
- Beim Durchstecken tragen die Kabelenden auf der anderen Seite zu weit auf und verhindern ein optimales platzieren des Sensors im Gehäuse
- Die anderen Enden an das Mainboard anlöten. Hier die Kabel durch die dafür vorgesehenen Löcher stecken - gibt mehr stabilität.
 <div align=center>
  <img width="400" src="../assets/manualPicture/case/btnLeft.jpg"/>
    <img width="400" src="../assets/manualPicture/case/btnLeft2.jpg"/>
      <img width="400" src="../assets/manualPicture/case/btnLeft3.jpg"/>
  </div>


### 1.2 Mittlerer Touch Sensor (btn_middle)
- 3 Kabel auf ca. 14cm Ablängen. Falls vorhanden, drei verschiedene Farben. 
- Kabelenden auf beiden seiten ca. 2mm abisolieren, verdrillen und verzinnen.
- Kabel NICHT durch die Löcher des Touch Sensors stecken sondern nur von oben auflegen und anlöten. (schwarz = GND ; rot = 3,3V/VCC ; grün = Data/IO)
- Beim Durchstecken tragen die Kabelenden auf der anderen Seite zu weit auf und verhindern ein optimales platzieren des Sensors im Gehäuse
- BRÜCKE A SCHLIEßEN! Ansonsten startet der Wemos D1 mini nicht mehr.
- Die anderen Enden an das Mainboard anlöten. Hier die Kabel durch die dafür vorgesehenen Löcher stecken - gibt mehr stabilität.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/btnMiddle.jpg"/>
    <img width="400" src="../assets/manualPicture/case/btnMiddle2.jpg"/>
  </div>


### 1.3 Rechter Touch Sensor (btn_right)
- 3 Kabel auf ca. 14cm Ablängen. Falls vorhanden, drei verschiedene Farben. 
- Kabelenden auf beiden seiten ca. 2mm abisolieren, verdrillen und verzinnen.
- Kabel NICHT durch die Löcher des Touch Sensors stecken sondern nur von oben auflegen und anlöten. (schwarz = GND ; rot = 3,3V/VCC ; grün = Data/IO)
- Beim Durchstecken tragen die Kabelenden auf der anderen Seite zu weit auf und verhindern ein optimales platzieren des Sensors im Gehäuse
- Die anderen Enden an das Mainboard anlöten. Hier die Kabel durch die dafür vorgesehenen Löcher stecken - gibt mehr stabilität.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/btnRight.jpg"/>
  <img width="400" src="../assets/manualPicture/case/btnRight2.jpg"/>
  </div>

## 2. LDR / Lichtsensor
- 2 Kabel auf ca. 7cm Ablängen. Kann zwei mal die gleiche Farbe verwendet werden, da keine Polarität.
- Kabelenden auf beiden seiten ca. 2mm abisolieren, verdrillen und verzinnen.
- Die Beinchen des LDR´s auf ca. 3-4mm kürzen und an die Kabel anlöten.
- Die anderen Enden an das Mainboard anlöten. Hier die Kabel durch die dafür vorgesehenen Löcher stecken - gibt mehr stabilität.
- Wie bereits erwähnt ist die Polarität des LDR´s nicht relevant. 

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/ldr.jpg"/>
    <img width="400" src="../assets/manualPicture/case/ldr2.jpg"/>
  </div>


## 3. Lautsprecher
- Der von uns verwendete Lautpsrecher hat eine Polarität. Diese gilt es zu beachten.
- rotes Kabel auf ca. 11cm ablängen, schwarzes Kabel auf ca. 13cm ablängen. Kabellängen stimmt hier nur wenn der Lautsprecher exakt wie in dieser Anleitung eingebaut wird!
- rotes Kabel am Plus des Lautsprechers anlöten
- schwarzes Kabel am Minus des Lautsprechers anlöten
- Die Kabel werden auf dem Mainboard unter "Speaker" angelötet. Rotes Kabel an den rechteckigen Pin, schwarzes Kabel an den ovalen Pin. 
- Den Lautsprecher kannst du einfach in die Aussparung stecken und muss daher auch nicht weiter fixiert werden.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/speaker.jpg"/>
    <img width="400" src="../assets/manualPicture/case/speaker2.jpg"/>
      <img width="400" src="../assets/manualPicture/case/speaker3.jpg"/>
  </div>

## 4. DC-Buchse
- Bei der DC-Buchse ist es besonders wichtig die Polarität zu beachten.
- 2 Kabel auf ca. 8cm Ablängen. Zwei unterschiedliche Farben benutzen. (schwarz = GND ; rot = +5V)
- Kabel an die DC-Buchse anlöten. Rot wird an den Mittelkontakt (+5V) gelötet, schwarz an den äußeren Kontakt (GND).
- Anschließend die Buchse ins Gehäuse schrauben.
- Nun können die anderen Enden an das Mainboard angeschlossen werden. (schwarz = GND ; rot = +5V)
- Anschluss erneut überprüfen weil sonst die Matrix Schaden nehmen wird.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/socket.jpg"/>
    <img width="400" src="../assets/manualPicture/case/socket2.jpg"/>
      <img width="400" src="../assets/manualPicture/case/socket3.jpg"/>
  </div>

## 5. Matrix in Grid schrauben
- Die Matrix wird mit 6 Schrauben (M3x4) mit dem Grid verschraubt.
- Die Schrauben nur sehr leicht anziehen. Anderfalls kann die Matrix Schaden nehmen und die Plastikgewinde im Grid gehen kaputt.
- Beim Einsetzen der Matrix in das Grid auf die Richtung achten. Für jeden Kondensator gibt es eine Aussparung im Grid. Hat man die Matrix richtig herum vor sich, sieht man links am Rand keine Kondensatoren während rechts am Rand Kondensatoren sitzen. Im Grid gibt es eine Seite wo außen keine Aussparungen sind. Diese müssen mit der Matrix übereinstimmen!

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/matrix2.jpg"/>
  <img width="400" src="../assets/manualPicture/case/matrix3.jpg"/>
  <img width="400" src="../assets/manualPicture/case/matrix4.jpg"/>
  </div>

## 6. Matrix
- 3 Kabel auf ca. 12cm Ablängen. Falls vorhanden, drei verschiedene Farben. (schwarz = GND ; rot = +5V ; grün = Data/data_in)
- Kabel an die Matrix löten. Es ist besonders wichtig, dass die drei Kontakte zum anschließen gewählt werden in denen "data_in" vorkommt. (schwarz = GND ; rot = +5V ; grün = data_in)
- Anschließend die Kabel auf dem Mainboard bei der Bezeichnung "Matrix" anlöten. (schwarz = GND ; rot = +5V ; grün = Data)
- Anschluss erneut überprüfen weil sonst die Matrix Schaden nehmen wird.

  <div align=center>
  <img width="400" src="../assets/manualPicture/case/matrix.jpg"/>
  </div>

## 7. Mainboard
- Das Mainboard wird mit vier Schrauben (M3x4) im Gehäuse befestigt.
- Die Schrauben nur sehr leicht anziehen. Anderfalls kann das Plastikgewinde im Grid kaputt gehen.

  <div align=center>
  <img width="400" src=".../assets/manualPicture/case/mainboard.jpg"/>
  </div>

## 8. Grid ins Gehäuse einsetzen
- Nun ist es Zeit das Gehäuse zu schließen und die Matrix in Betrieb zu nehmen.
- Sollte dein Wemos D1 mini an dieser Stelle noch nicht mit der Controller Software bespielt worden sein, dann tue dies bevor du das Gehäuse schließt!
- Leg dir das Gehäuse so hin, dass die Touch Taster und der LDR nach oben/von dir weg schauen.
- Beim Einlegen des Grids in das Gehäuse müssen die Anschlusskabel der Matrix nun auf der linken Seite sein.

  <div align=center>
  <img width="400" src="./assets/manualPicture/case/timeToFinish.jpg"/>
  <img width="400" src="../assets/manualPicture/case/finish.jpg"/>
  </div>

## 9. FERTIG
- Hast du Fragen? Dann stelle diese bitte im Forum. Durch öffentliche Fragen profitieren ggf. noch weitere Nutzer.
- Zeige uns deine fertige Matrix auf Facebook oder im Forum.
- Viel Spaß mit deiner Matrix!


  <div align=center>
  <img width="400" src="../assets/manualPicture/case/finish2.jpg"/>
  </div>
















