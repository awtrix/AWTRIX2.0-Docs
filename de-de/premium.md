
Diese Kategorie bietet tolle Funktionen die nur durch den Kauf eines Premium Schlüssels freigeschaltet werden. Diesen erhälst du bei mir im [Shop](https://blueforcer.de/shop/).
Durch den Kauf eines Schlüssels unterstützt du mich bei der weiteren Entwicklung von AWTRIX und beim bezahlen meiner anfallenden Kosten wie z.b Servermiete, Kauf von neuen Bauteilen usw.
Diese Funktionen werden regelmäßig erweitert.


**AWTRIX Cloud**  
Aktiviert die Anbindung an die AWTRIX Cloud. Weitere Informationen dazu findest du [hier](/de-de/cloud.md).  
Nach der Aktivierung erhälst du einen Token den du für die externe Ansteuerung benötigst. Mit "Revoke Token" kannst du dir jederzeit einen neuen erstellen lassen.

**Fritz!Box Call Monitor** 

!> Um den Callmonitor in der Firtz!Box zu aktivieren, muss man auf einem angeschlossenen Telefon die folgende Nummer eingeben und anrufen:   ```#96*5*``` 

Wer eine FritzBox der Firma AVM sein eigen nennt, kann mit dieser Funktion die FritzBox in AWTRIX einbinden, so dass beispielsweise über einen eingehenden Anruf oder die Rufnummer des Anrufenden informiert wird.  
  
Gib hierzu die IP Adresse der Fritzbox an und richte, wenn gewünscht, noch das Telefonbuch ein. Wenn ein Telefonbuch hinterlegt ist, zeigt AWTRIX bei einem Anruf den passenden Namen an, ansonsten die Telefonnummer.   Du kannst entweder ein Telefonbuch aus der FritzBox exportieren und [in eine JSON umwandeln](http://www.utilities-online.info/xmltojson/) oder, wenn das nicht klappt, dein Telefonbuch manuell erstellen. Dazu musst du nur für jede Nummer eine neue Zeile verwenden. Der Aufbau ist sehr einfach:
``` BASH
01514875965=Blueforcer
01603262987=Günther
06185772637=Herbert
usw..
``` 


**Pushover**  
Hiermit kannst du über Pushover, Benachrichtigungen an AWTRIX senden. Die eingetragenen Logindaten verbleiben selbstverständlich lokal auf deiner AWTRIX.

**Sleep Mode**  
Der Sleepmode erlaubt es dir eine Zeitspanne festzulegen in dem AWTRIX "schlafen" wird. Während dieser Phase reagiert AWTRIX auf keine API-Befehle. Du hast die Möglichkeit eine definierte App auszuwählen, die während dieser Phase kontinuierlich angezeigt wird. Außerdem kannst du die Helligkeit festlegen. Trage hier 0 ein um die Matrix komplett auszuschalten.

**Alarm Clock**  
Hier kannst du einen Alarm einstellen, der sich täglich widerholt. Neben einem individuellen Icon, kannst du auch ein Soundfile abspielen lassen.

**Yeelight**
Hier hast du die Möglichkeit eine Yeelight RGB Lampe mit AWTRIX zu verbinden. Dabei werden neben den normalen "Glühbirnen" auch Strips und Bedside Lamp unterstützt. Trage die IP Adresse der Yeelight ein nachdem du in der Yeelight App den LAN-Modus aktiviert hast. Du kannst nun verschiedene Effekte über die API abspielen. So kannst du z.b bei deinen wichtigen Benachrichtigungen neben Sounds auch Lichteffekte aktivieren.

**E1.31**  
Ermöglicht es dir, E1.31-Daten (wie Artnet) an deine AWTRIX zu senden. Mit xLight zum Beispiel müssen du einen neuen Controller mit 2 Universen mit je 384 Kanälen hinzufügen. Füge auch ein neues Matrix-Layout mit 8 Strings á 32 Strands und der Startposition oben links hinzu. Wenn du mit dem Senden von Daten beginnst, stoppt AWTRIX seinen normalen Betrieb und zeigt deine Daten an. 5s nachdem du das Senden von Daten gestoppt hast, kehrt AWTRIX zum normalen Betrieb zurück.

**Alexa**  
Dadurch wird eine Phillips Hue-Lampe emuliert, so dass du die Textfarbe, die Helligkeit und das Ein- und Ausschalten über Amazonen Alexa steuern kannst. (Der integrierte Emulationsserver benutzt Port 80, stelle sicher, dass er von keinem anderen Programm benutzt wird).

**Python**  
Du kannst einfache Python-Anwendungen für awtrix schreiben.
AWTRIX verwendet dafür die Java ScriptEngine Nashorn zusammen mit jython.
Platziere deine Python-Datei in den apps-Ordner und starte awtrix neu. Alle Python-Anwendungen werden wie normale native Anwendungen geladen.

Beispiel für eine app.py:

!> Alle Variablennamen und Funktionsnamen müssen genau so bleiben wie sie sind.

```python
import urllib, json

Version = 1.0
Author = "Blueforcer"
Description = "AWTRIX app written in python"
HowToSetup = "Example Text"
Covericon = 1164
Repeat=2
MoveIcon=True
CustomScreen=False #not working yet
Settings = {"Prefix": "MissionName: "} #Usersettings

#Dont modfiy this
def init():	
    return [Version,Author,Description,HowToSetup,Covericon,Repeat,MoveIcon,CustomScreen]

def started():
    print("App started")

def running():
    print("App running")

def finished():
    print("App finished")

def getSettings():
    return Settings   

#This function is called when AWTRIX trigger all apps to do their downloads.
#Unlike native apps you will need to return the iconID and Text wich should be show
#You also will get a map of the Userettings to work with
def getData(settings):
    url = "https://api.spacexdata.com/v3/launches/next"
    response = urllib.urlopen(url)
    data = json.loads(response.read())
    SpaceXMission = data["mission_name"]
    return [1164,settings["Prefix"] + SpaceXMission]
```    