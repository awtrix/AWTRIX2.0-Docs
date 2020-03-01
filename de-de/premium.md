
Diese Kategorie bietet tolle Funktionen die nur durch den Kauf eines Premium Schlüssels freigeschaltet werden. Diesen erhälst du bei mir im Shop.
Durch den Kauf eines Schlüssels unterstützt du mich bei der weiteren Entwicklung von AWTRIX und beim bezahlen meiner anfallenden Kosten wie z.b Servermiete, Kauf von neuen Bauteilen usw.
Diese Funktionen werden regelmäßig erweitert.


**AWTRIX Cloud**  
Aktiviert die Anbindung an die AWTRIX Cloud. Weitere Informationen dazu findest du [hier](/de-de/cloud.md).  
Nach der Aktivierung erhälst du einen Token den du für die externe Ansteuerung benötigst. Mit "Revoke Token" kannst du dir jederzeit einen neuen erstellen lassen.

**Fritz!Box Call Monitor**  
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
