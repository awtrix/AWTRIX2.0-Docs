
## AWTRIX Premium

Diese Kategorie bietet tolle Funktionen die nur durch den Kauf eines Premium Schlüssels freigeschaltet werden. Diese Funktionen werden regelmäßig erweitert. Diesen erhälst du bei mir im [Shop](https://blueforcer.de/shop/).    
Durch den Kauf eines Schlüssels unterstützt du mich bei der weiteren Entwicklung von AWTRIX und beim bezahlen meiner anfallenden Kosten wie z.b Servermiete, Kauf von neuen Bauteilen usw.  
Ein Schlüssel ist **pro Benutzer** und kann für bis zu 3 verschiedenen AWTRIX-Geräten verwendet werden. Wenn du eine 4. Awtrix mit Premium für deinen eigenen Gebrauch benötigst, schreib mir einfach. Wir werden sicher eine Lösung finden.


?> Du kannst deine bisherigen Aktivierungen jederzeit [in deinem Konto](https://blueforcer.de/shop/mein-konto/license-keys/) einsehen und ggf. löschen

## Derzeit verfügbare Premium-Funktionen

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
Dadurch wird eine Phillips Hue-Lampe emuliert, so dass du die Textfarbe, die Helligkeit und das Ein- und Ausschalten über Amazonen Alexa steuern kannst. Der integrierte Emulationsserver benutzt Port 80, stelle sicher, dass er von keinem anderen Programm benutzt wird (Getestet mit Amazon Alexa Dot gen3).

**Telegram**  
Dies erlaubt dir AWTRIX über Telegram zu steuern. Neben einigen Spezialfunktionen, kannst du auch beliebige Texte senden, die dann angezeigt werden.
[Um den AWTRIX Telegram bot zu nutzen musst du dir einen Bottoken erstellen.](https://www.siteguarding.com/en/how-to-get-telegram-bot-api-token)



## Fehlerbehebung


!> **Bitte beachte:** Wenn du **Docker** verwendest, wird beim rebuilden des Containers auch die Hardware-ID geändert. Um dies zu umgehen, starte den Container im Host-Modus oder deaktiviere deinen Premium-Account vor jedem rebuild -> Danach kannst du den Schlüssel erneut eingeben, ohne deine Aktivierungen zu verbrauchen. Beim Neustart eines Containers tritt dieses Problem nicht auf.

- Ich erhalte die Meldung **Aktivierungslimit für Lizenzschlüssel erreicht (3/3)**. Entweder hast du das Limit wirklich erreicht und musst die Premium-Funktion bei deinem bisherigen AWTRIX deaktivieren. Dies geschieht auch, wenn du die Schlüssel mit anderen teilst (was natürlich nicht erlaubt ist). Bei Benutzern, die AWTRIX schon lange benutzen, es aber gerade erst aktualisiert haben, können Probleme auftreten, weil sich die Funktionsweise meines Lizenzservers geändert hat. In diesem Fall kannst du deine Aktivierungen unter ["Mein Konto"](https://blueforcer.de/shop/mein-konto/license-keys/) deaktiveren, so dass du den Schlüssel wieder wie gewohnt verwenden kannst. Dies ist nur einmal erforderlich. 

- Ich erhalte die Meldung **Premium kann nicht aktiviert werden, da das Hardwarebinding nicht übereinstimmt**. Dies bedeutet, dass AWTRIX nicht aktiviert werden kann, weil sich deine Hardware geändert hat. AWTRIX erstellt eine hardwarespezifische Datei, wenn Premium zum ersten Mal aktiviert wird. Wenn du jetzt deine AWTRIX-Installation auf eine andere Hardware-Plattform kopierst, kopierst du auch die spezifische Datei, die noch die Hardware-ID deiner alten Plattform enthält, so dass der von dir eingegebene Schlüssel auf der neuen Plattform ungültig ist. AWTRIX löscht automatisch diess Hardwarebinding, sodass du nun den Schlüssel nochmal eingeben kannst. Dies wird natürlich die Anzahl deiner verfügbaren Aktivierungen reduzieren. Du kannst deine Premium-Funktionalität auf deiner alten Plattform jederzeit deaktivieren, wodurch sich auch die Anzahl der verfügbaren Aktivierungen wieder erhöht. Du kannst deine Aktivierungen unter ["Mein Konto"](https://blueforcer.de/shop/mein-konto/license-keys/) jederzeit deaktiveren, solltest du nciht die möglichkeit haben, diese direkt von einer AWTRIX zu entfernen.

