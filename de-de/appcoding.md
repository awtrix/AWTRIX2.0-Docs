
  
![B4J](assets/coding/code.png)

## Programmiersprache  
AWTRIX und seine Apps sind in B4X geschrieben. 
B4X verwendet einen proprietären Dialekt von Visual Basic (im Folgenden "B4X" genannt).

## IDE (Entwicklungsumgebung)
B4J ist ein modernes "VB6-ähnliches" und 100% kostenloses Entwicklungswerkzeug für plattformübergreifende Desktop-, Server- und IoT-Lösungen.
Die kompilierten Apps können auf Windows-, Mac-, Linux- und ARM-Boards (z.B. Raspberry Pi) ausgeführt werden. Die kompilierten Apps sind native Java-Anwendungen.  
  
[Download B4J](https://www.b4x.com/b4j.html)


## Apps definition
AWTRIX Apps sind Java-Bibliotheken, die zur Laufzeit geladen werden können.
Definierte Funktionen, die von AWTRIX aufgerufen werden, übertragen die Informationen auf die Matrix.

# Erste Schritte
Für die erste App ist es besser, mit dem Template zu beginnen [Download](https://github.com/awtrix/AWTRIX2.0-Apps/tree/master/templateApp)  
Nachdem du die Template.b4j mit B4J geöffnet hast, sollte das ganze so aussehen:  
  
![B4J](assets/coding/start.png)

Zuerst solltest du deiner App einen eindeutigen namen geben.  
Vorraussetzungen der Namensgebung:
- Keine Umlaute
- Keine Leerzeichen
- Keine Sonderzeichen
- Dieser Name ist noch nicht von einer anderen App vergeben

Der Appname muss als erstes an **4 Punkten** eingetragen werden:
- In der Main-klasse ```#LibraryName:Template```
- Wechsel in die Template-Klasse und drage dort in der Funktion ```Public Sub Initialize() As String``` deinen Appnamen in ```App.name = "Template"``` ein
- Gehe auf Projekt-Modul umbennenen und gib dieser Klasse deinen Appnamen
- Speichere das Projekt an einem neuen Ort mit dem selben Appnamen ab

## App Konfiguration
Nun geht es an die **Konfiguration** deiner App. Dies geschiet alles in der Initialize() Funktion. Hier gibt es mehrere parameter die gesetzt werden können bzw müssen.

### Notwendig

**App.name**    
 Der Name der App. Dieser wird im Appstore, MyApps und als Dateinamen verwendet

**App.version**      
Die Verison der App. Die Version muss nummerisch sein und kann bis zu 2 Nachkommastellen beinhalten (z.b 1.25)

**App.description**    
Die Beschreibung der App. Beschreibe hier kurz und knapp deine App. Den Text kannst du optional als HTML formatieren

**App.author**    
Der Ersteller der App. Damit jeder weiß wer hier Blut, Schweiß und Tränen investiert hat.

**App.coverIcon**    
Das Icon deiner App. Hierzu wird eine IconID aus der Datenbank benötigt. Du kannst dein eigenes Icon im Icon Creator erstellen und hochladen

**App.settings**    
Die möglichen Einstellungen der App. Hierzu wird eine Map generiert die aus Keys und Values besteht. z.B
```CreateMap("Key":"Value")```
Du kannst entweder standard Werte eintragen, sodass deine App direkt loslaufen kann oder du lässt den Wert leer ("") damit AWTRIX den Benutzer erst darauf hinweist das es noch was zum Einstellen gibt.
AWTRIX wird die App nicht laden, solange nicht alle Einstellungen gesetzt sind! 

**App.setupDescription**    
Erkläre hier kurz wie deine App eingestellt werden muss oder woher die notwendigen Daten zu erhalten sind. Den Text kannst du optional als HTML formatieren

**App.downloads**   
Hier gibst du an, wieviele Downloads deine App benötigt. Mehrere Downloads sind z.B notwendig wenn ein Download in Abhängigkeit eines anderen steht.

**App.icons**   
Hier gibst du an, welche Icons deine App brauchen wird. Diese werden ebenfalls von AWTRIX heruntergeladen bevor die App getartet wird.

**App.tick**   
Hier gibst du an wie schnell deine App laufen soll. Für einen einfachen Text hat sich 65 (ms) als perfekt erwiesen.

### Optional

**App.lock**   
Wenn auf true gesetzt, wartet AWTRIX auf den Befehl "finish", bevor zur nächsten App gewechselt wird.

**App.game**   
Wenn auf true gesetzt, wird deine App als Spiel behandelt.

**App.howToPlay**   
Wenn du ein Spiel programmierst, kannst du hier beschreiben wie man es spielt.

**App.forceDownload**   
Wenn auf true gesetzt, stößt AWTRIX vor jedem start der App die Download Routine an.

**App.hidden**   
Wenn auf true gesetzt, wird AWTRIX diese App nicht aktiv in den Apploop mit aufnehmen.

**App.shouldShow**   
Wenn auf false gesetzt, wird AWTRIX diese App in der Apploop überspringen, dies ist z.b hilfreich wenn die App kontrolliert angezeigt werden soll.

**App.polling**   
Hier kann eine Sub angegeben werden die im Hintergrund alle 5 Sekunden angestoßen wird. Hier kann z.b entschieden werden ob die App wieder angezeigt werden soll.


## Events
AWTRIX bietet einige Events die zu einem bestimmten Zeitpunkt ausgelöst werden:

**App_Started**   
Diese Sub wird kurz bevor AWTRIX deine App anzeigt aufgerufen.

**App_Exited**   
Dieser Sub wird aufgerufen, wenn AWTRIX zur nächsten App wechselt und diese pausiert.

**App_iconRequest**   
Diese Sub wird kurz bevor AWTRIX deine App anzeigt aufgerufen.
Wenn du ein anderes Icon brauchst, kannst du deine Iconliste hier wieder bearbeiten.

**App_settingsChanged**   
Wenn der Benutzer irgendwelche Einstellungen an deiner App ändert, wird diese Sub aufgerufen.

**App_startDownload**   
Wird bei jedem App Update von Awtrix aufgerufen. Du musst eine URL für jeden Downloadhandler zurück geben

**App_evalJobResponse**   
Wird nach jedem angeforderten Download aufgerufen. Hier können die geruntergeladenen Daten verarbeitet werden.

**App_genFrame**
Diese Sub wird während deine App läuft kontinuierlich aufgerufen. Das Interval setzt du mit App.Tick fest.
Hier wird AWTRIX die Zeichenroutinen übergeben, die letzendlich auf der Matrix angezeigt wird.

**App_controllerButton**
Wenn du ein Spiel erstellst, verwende diese Sub, um die Tastendrücke vom Webinterface oder dem Game-Controller zu erhalten.
button definiert die ButtonID des Controllers, dir ist true, wenn er gedrückt wird.

**App_controllerAxis**
Wenn du ein Spiel erstellst, verwenden diese Sub, um die Analogwerte des angeschlossenen Controllers zu erhalten.