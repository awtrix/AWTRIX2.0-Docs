
  
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
- Gehe auf Projekt-> Modul umbennenen und gib dieser Klasse deinen Appnamen
- Speichere das Projekt an einem neuen Ort mit dem selben Appnamen ab

Nun geht es an die Konfiguration deiner App. Dies geschiet alles in der Initialize() Funktion. Hier gibt es mehrere parameter die gesetzt werden können bzw müssen.

### Notwendig:

> **App.name**  
 Der Name der App. Dieser wird im Appstore, MyApps und als Dateinamen verwendet

> **App.version**    
> Die Verison der App. Die Version muss nummerisch sein und kann bis zu 2 Nachkommastellen beinhalten (z.b 1.25)

> **App.description**  
> Die Beschreibung der App. Beschreibe hier kurz und knapp deine App. Den Text kannst du optional als HTML formatieren

> **App.author**  
> Der Ersteller der App. Damit jeder weiß wer hier Blut, Schweiß und Tränen investiert hat.

> **App.coverIcon**  
> Das Icon deiner App. Hierzu wird eine IconID aus der Datenbank benötigt. Du kannst dein eigenes Icon im Icon Creator erstellen und hochladen

> **App.settings**  
> Die möglichen Einstellungen der App. Hierzu wird eine Map generiert die aus Keys und Values besteht. z.B
> ```CreateMap("Key":"Value")```
> Du kannst entweder standard Werte eintragen, sodass deine App direkt loslaufen kann oder du lässt den Wert leer ("") damit AWTRIX den Benutzer erst darauf hinweist das es noch was zum Einstellen gibt.
> AWTRIX wird die App nicht laden, solange nicht alle Einstellungen gesetzt sind! 

> **App.setupDescription**  
> Erkläre hier kurz wie deine App eingestellt werden muss oder woher die notwendigen Daten zu erhalten sind. Den Text kannst du optional als HTML formatieren

> **App.downloads** 
> Hier gibst du an, wieviele Downloads deine App benötigt. Mehrere Downloads sind z.B notwendig wenn ein Download in Abhängigkeit eines anderen steht.

> **App.icons** 
> Hier gibst du an, welche Icons deine App brauchen wird. Diese werden ebenfalls von AWTRIX heruntergeladen bevor die App getartet wird.

> **App.tick** 
> Hier gibst du an wie schnell deine App laufen soll. Für einen einfachen Text hat sich 65 (ms) als perfekt erwiesen.
