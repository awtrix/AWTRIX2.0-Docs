AWTRIX bietet eine breite Palette an Befehlen um von extern gesteuert werden zu können.

### MQTT
Für MQTT kannst du AWTRIX mit einen bestehenden MQTT Broker verbinden.
Das Basis-Topic (Prefix) ist hierbei standardmäßig **awtrix**.

### REST
Für die REST-API ist der Basis-Endpunkt  
**http://[AWTRIX-SERVER_IP]:7000/api/v3**  

z.B. für einen einfachen Test unter Linux kann curl kann verwendet werden, um eine http-Anfrage zu stellen:  
``` BASH
curl -X POST --header 'Content-Type: application/json' -d '{"force":true,"text":"Awesome","icon":1,"color":[0,255,255],"count":2}' 'http://[HOST_IP]:7000/api/v3/notify'
```



## Basic Controls

> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/basics  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/basics


___

### power
Schaltet AWTRIX ein (true) oder aus (false).

``` JSON
{"power": true}
```
___

### switchTo

Wechsel zu einer definierten App


``` JSON
{"switchTo":"Facebook"}
```
___

### Appstate

Deaktiviert oder aktiviert eine App


``` JSON
{"disable":"Facebook"}
{"enable":"Facebook"}
```
___

### Apploop

Steuert die Apploop

#### **Parameter**  
- app
  - "next" : nächste App
  - "back" : vorherige App
  - "pause" : Apploop pausieren (toggle)
  - "hold" : die aktuelle App ohne Umschalten halten (toggle)

``` JSON
{"app":"next"}
```
___

### showAnimation

Zeigt eine zufällige Animation, die aus der AWTRIX-Cloud heruntergeladen wird.


``` JSON
{"showAnimation":"random"}
```
___

### Soundfile

Spielt eine Audiodatei ab, die auf die SD-Karte des DF-Players geladen wurde. 

Du musst einen Ordner "MP3" auf deiner DFplayer SD-Karte erstellen und deine mp3s in diesen Ordner verschieben.
Die mp3 muss mit einer 4-stelligen Zahl beginnen, z.B. 0001.mp3 oder 0001 - Testfile.mp3.  
AWTRIX verwendet den Bereich 0001-0100 für interne Zwecke. Beginne  mit  eigenen mp3s bei 0101.  
[Standartsounds herunterladen](https://blueforcer.de/awtrix/beta/Soundfiles.zip)

#### **Parameter** 
- soundfile: Nummer der gewünschten MP3 

``` JSON
{"soundfile": 101}
```

___

### Timer

Startet einen Timer für die angegebene Zeitspanne und zeigt einen Alarm an, wenn die Zeit abgelaufen ist.

#### **Parameter** 
- timer: Zeitspanne in ```"stunden:minuten:sekunden"``` 
- color: Array von Ganzzahlen [R,G,B] (optional)
- count: Wie oft soll der Timer blinken? (optional)
- text: Text, der angezeigt wird (statisch, bis zu 8 Zeichen) (optional)

``` JSON
{"timer":"00:00:10","color":[255,0,0],"count":10,"text":"AWTRIX"}
```

``` JSON
{"timer":"stop"} //löscht den Timer wieder
```
___
### stopwatch

Startet eine Stoppuhr mit vordefiniertem Icon. Während der Ausführung ist AWTRIX blockiert.
Wenn die Stoppuhr 1 Stunde erreicht, wird das Icon für mehr Platz entfernt.

#### **Parameter** 
- stopwatch: Starten/Stoppen der Stoppuhr
- icon: IconID

``` JSON
{"stopwatch":true, "icon":423}
```
``` JSON
{"stopwatch":false} // Stoppt den Timer
```
___

### AppList

Mit dieser API kannst du die Reihenfolge der Apps (AppLoop) anpassen.

#### **Parameter** 
- AppList: eine Liste der benutzerdefinierten Apploop (Array of String)
- icon: iconID

``` JSON
{"AppList":["Time","Facebook","Time","Instagram"]}
```

``` JSON
{"AppList":"reset"} //setzt die Apploop zurück
```
___

## Grundlegende Informationen erhalten
> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/basics  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/basics
> MQTT anwortet auf dem Topic "[prefix]/response"

#### **Parameter** 
- get

#### Mögliche Informationen
- **installedApps**
  - gibt alle installierten Apps zurück
- **AppList**  
  - gibt die komplette App-Loop zurück
- **settings**     
  - gibt alle Einstellungen zurück
- **version**       
  - gibt die AWTRIX-Version zurück
- **uptime**         
  - gibt die Betriebszeit von AWTRIX zurück
- **powerState**
  - gibt an ob AWTRIX an (true) oder ausgeschaltet (false) ist zurück
- **log**
  - gibt das Protokoll zurück
- **matrixInfo**     
  - gibt alle Informationen der verbundenen Matrix zurück.

``` JSON
{"get":"activeApps"}
``` 


___


## Einstellungen ändern

Hiermit können alle Einstellungen geändert werden
Die passenden Keys der Einstellungen sind in der Datei "datastore" im order "config" zu finden.
Außerdem können die Einstellungen im selben format ausgelesen werden [Siehe hier](http://localhost:3000/#/de-de/api?id=grundlegende-informationen-erhalten)
> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/settings  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/settings
___

Eine oder mehrere Einstellungen vornehmen

``` JSON
{"Brightness":100}
```

___


## Benachrichtigungen

> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/notify  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/notify
 

Zeigt eine idividuelle Benachrichtigung an 

### **Parameter**  
- **force (optional)**
  - Legt fest, bb die angegebenen Benachrichtigung sofort oder nach der aktuellen App angezeigt werden soll (true/false).
  Wenn auf false gesetzt, wird die Benachrichtigung in eine Warteschlange einsortiert. Nach der aktuellen App zeigt AWTRIX nacheinander alle Benachrichtigungen an und löscht diese anschließend. Somit können mehrere Benachrichtigungen auf einmal gesendet werden. Wenn sich keine weiteren Benachrichtigungen in der Warteschlange befinden, wird AWTRIX wieder native Apps anzeigen.
- **name (optional)**
  - Kennung der Benachrichtigung
- **text**
  - Anzuzeigender Text (String)
- **icon (optional)**
  - iconID aus der Online Datenbank
- **color (optional)**
  - benutzerdefinierte Textfarbe (Array von Ganzzahlen [R,G,B])
- **moveIcon (optional)**
  - Verschiebt das Icon mit dem Text aus dem Bildschirm (wahr/falsch).
- **duration (optional)**
  - Definiert wie lange (in Sekunden) die Benachrichtiung angezeigt werden soll (Ganzzahl) (Wird von **count** überschrieben)
- **repeat (optional)**
  - wie oft der Text gescrollt werden soll, bevor zur nächsten App gewechselt wird. Wenn der Text aufgeund der Textlänge nicht gescrollt werden muss, wird die globale App Laufzeit verwendet, um zu wechseln. (Ganzzahl)
- **soundfile (optional) (Nummer der gewünschten MP3)**
  - spielt beim Start der App eine bestimmte Datei auf dem DFPlayer ab.

  
```JSON
{
   "name":"TestNotification",
   "force":true,
   "icon":6,
   "moveIcon":true, 
   "repeat":2,
   "soundfile":1,
   "text":"Totally Awesome",
   "color":[
      0,
      255,
      0
   ]
}
	
```
  
Eine Benachrichtigung kann aus der Warteschlange entfernt werden
```JSON
{"remove":"TestNotification"}
```

___

## Zeichnung

> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/draw  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/draw
___

Du kannst verschiedene Zeichenbefehle an AWTRIX senden, um einen individuelle Bildschirm zu erstellen. Dazu können in einem JSON-String mehrere Befehle definiert werden, die AWTRIX dann nacheinander verarbeitet. Dadurch sind  kleinere Animationen möglich.
Alle Methoden sind statisch, ein automatisches scrollen des Textes ist nicht möglich.
Der Zeichenmodus beginnt mit dem ersten Befehl.

Jeder Befehl füllt nur den Framebuffer. Du musst **show** ausführen, um schließlich die Daten auf der Matrix anzuzeigen. 


Das folgende Beispiel ist wie folgt aufgebaut:
 - Fülle den gesamten Bildschirm mit grauem Hintergrund.
 - Schreib  "Hello".
 - Zeigt die letzten beiden Befehle auf der Matrix an.
 - Warten 3 Sekunden vor dem nächsten Befehl.
 - Zeichne einen Kreis neben dem Text.
 - Und zeige es an
 - Weitere 3 Sekunden warten
 - Den gesamten Inhalt löschen
 - Zeichne eine Linie von der linken oberen Ecke zur unteren rechten Ecke.
 - Zeig die Linie auf der Matrix an.
 - 3 Sekunden warten
 - Alles zweimal wiederholen
 - Verlasse des Zeichenmodus

!> **Bitte beachten Sie:** Du musst **exit** aufrufen, um den Zeichenmodus zu verlassen und in den Normalzustand zurückzukehren. Wenn du Wiederholung einstellst, wird der Exit-Befehl ignoriert und beendet automatisch den Zeichenmodus, wenn alle Wiederholungen abgeschlossen sind.  

``` JSON
{
  "repeat":2,
  "draw": [
    {
      "type": "fill",
      "color": [100,100,100]
    },
    {
      "type": "text",
      "string": "Hello",
      "position": [0,0],
      "color": [255,0,0]
    },
    {
      "type": "show"
    },
    {
      "type": "wait",
      "ms": 3000
    },
    {
      "type": "circle",
      "radius": 3,
      "position": [24,3],
      "color": [255,0,255]
    },
    {
      "type": "show"
    },
    {
      "type": "wait",
      "ms": 3000
    },
    {
      "type": "clear"
    },
    {
      "type": "line",
      "start": [0,0],
      "end": [31,7],
      "color": [255,255,255]
    },
    {
      "type": "show"
    },
    {
      "type": "wait",
      "ms": 3000
    },
    {
      "type": "exit"
    }
  ]
}
```


 #### **Possible commands**

?> Das erste Pixel (linke obere Ecke) hat die Koordinate[0,0], während das letzte (rechte untere Ecke)[31,7] hat.  

**<span style="color:blue">loop</span>** Wie oft die Zeichenroutinen wiederholt werden sollen (optional)

- **<span style="color:blue">text</span>** Zeichnet einen Text an.
  - string 
  - position 
    - Array of Integer [X,Y]
  - color
    - Array of Integer [R,G,B]
- **<span style="color:blue">rect</span>** Zeichnet ein Rechteck.
  - position
    - Array of Integer [X,Y]
  - size
    - Array of Integer [Width,Height]
  - color
    - Array of Integer [R,G,B]
- **<span style="color:blue">line</span>** Zeichnet eine Linie.
  - start
    - Array of Integer [X0,Y0]
  - end
    - Array of Integer [X1,Y1]
  - color
    - Array of Integer [R,G,B]
- **<span style="color:blue">circle</span>** Zeichnet einen Kreis.
  - position
    - Array of Integer [X,Y]
  - radius
    - Integer r
  - color
    - Array of Integer [R,G,B]
- **<span style="color:blue">pixel</span>** Zeichnet einen einzelnen Pixel.
  - position
    - Array of Integer [X,Y]
  - color
    - Array of Integer [R,G,B]
- **<span style="color:blue">bmp</span>**  Zeichnet ein Bitmap.
  - position
    - Array of Integer [X,Y]
  - size
    - Array of Integer [Width,Height]
  - data
    - Array of RGB565 Integer [p0,p1,p2,p3,...]
- **<span style="color:blue">fill</span>**  Füllt die gesamte Matrix mit einer Farbe.
  - color
    - Array of Integer [R,G,B]
- **<span style="color:blue">wait</span>** Warte  X Millisekunden vor dem nächsten Befehl.
  - ms
    - Integer ms
- **<span style="color:blue">show</span>**  Zeigt alle vorherigen Befehle an.
- **<span style="color:blue">clear</span>** Löscht den Inhalt der Matrix.
- **<span style="color:blue">exit</span>**  Den Zeichenmodus verlassen und zum Normalzustand zurückkehren.
