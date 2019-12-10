Über die Sidebar "Settings" können verschiedene Einstellungen für den Host und Matrix getätigt werden. Im Folgenden werden alle Möglichkeiten erklärt:

## Host
###  Basic Settings 

**Boot Animation**  
Zeigt beim ersten Verbindungsaufbau der Matrix eine Bootanimation an.
Diese nutzt die Draw API. Die bootanimation.json befindet sich im Ordner "config" und kann beliebig verändert werden.

**Switch Animation**  
Die aktiviert eine Wechselanimation zwischen den Apps. Hierbei wird die Alte App heruntergedimmt und die neue hochgedimmt.

**Color Switch**  
Eine andere form der Wechselanimation. Hier löscht ein farbiger balgen die aktive App von der Matrix

**Uppercase Letters**  
Diese Funktion wandlelt alle Texte in Großbuchstaben um

**Remove Accents**  
Einige Sprachen verwenden Akzente die die Matrix nicht darstellen kann. Diese Funktion ersetzt diese mit lesbaren Zeichen.

**Verbose Log**  
Diese Funktion erweitert den Log. Dies ist vorallem Hilfreich bei Bugreports.

**Analytics**  
Diese Funktion erlaubt die Übergabe der IP-Adresse an den AWTRIX Cloud Server. Es werden keine weiteren Einstellungen oder Informationen gesendet.
Anhand dieser IP Adresse kann ich einsehen in welchem Land AWTRIX läuft und wieviele insgesamt. Diese Information wird nicht an dritte weitergegeben und nicht gespeichert.
Die Information wird temporär zur Laufzeit meines Servers gehalten, und wird komplett gelöscht sobald ein AWTRIX Host länger als 10min offline ist.  
P.s. Jeder normale Webseiten Aufruf, Email-Versand und auch die downloads der Icons hinterlässt am jeweiligen Server immer die IP-Adresse. Bei AWTRIX könnt ihr aber bestimmen ob ich diese zur Auswertung nutzen darf. Dies hilft mir zu sehen wie verbreitet mein Projekt bisher ist, dadurch kann ich AWTRIX auf bestimmte Länder anpassen und es motiviert mich natürlich massiv euch immer mehr Funktionen zu bieten.

**Textcolor**  
Hier kannst du die globale Textfarbe bestimmen.
Trage entweder deine gewünschte Farbe imf Format rgb(R,G,B) ein oder nutze den Colorpicker auf der rechten Seite

**Brightness**  
Hier wird die Helligkeit der Matrix festgelegt. Bitte bedenke: Je heller die Matrix, desto mehr Strom wird verbraucht und desto wärmer wird sie. 

!> Die Matrix kann bei höchster Helligkeitsstufe und komplett weißen Pixeln bis zu 75 Watt beanspruchen!

**App Duration**
Legt die Zeit fest, wie lange eine App angezeigt wird, bevor zur nächsten gewechselt wird.

**Scroll speed**
Mit diesem Wert wird angebegen nach wievielen Millisekunden der Text um eine Y-Position verschoben wird. Ein niedriger Wert lässt den Text schneller scrollen, sorgt allerdings auch für eine höhere CPU Auslastung.

**Update interval**
Dieser wert gibt an, nach wievielen Sekunden alle Apps ihre Daten aktualisieren.

**Volume**
Stellt die Lautstärke des angeschlossenen DFPlayer ein.

**Timezone Offset (UTC)**
Dies stellt die Differnenz zur UTC Zeitzone ein.

### Communication

#### Webserver
**Port**   
änder den Port über den das AWTRIX Webinterface aufgerufen wird

**Enable Login**  
Aktiviert die Anmeldemaske des AWTRIX Webinterfaces

**Login Password**  
Das Passwort für die Anmeldemaske (Standard: **awtrix**)

#### MQTT
Aktiviert den MQTT Client. Weitere Einstellungen sind selbsterklärend

### Matrix connection
Du kannst die Matrix entweder über WiFi oder USB betreiben. Wenn du ein schwaches oder überlastetes WiFi hast, versuche bitte die Kommunikation der Matrix über USB an, um Ruckeln zu vermeiden. 

### Premium
Diese Kategorie bietet tolle Funktionen die nur durch den Kauf eines Premium Schlüssels freigeschaltet werden. Diesen erhälst du bei mir im Shop.
Durch den Kauf eines Schlüssels unterstützt du mich bei der weiteren Entwicklung von AWTRIX und beim bezhalen meiner anfallenden Kosten wie z.b Servermiete, Kauf von neuen Bauteilen usw.

**AWTRIX Cloud**