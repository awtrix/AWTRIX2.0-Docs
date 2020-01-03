Das Ziel der AWTRIX Cloud ist es, die Lücke zwischen deiner lokalen Instanz und den Diensten in der Cloud zu schließen und gleichzeitig ein Höchstmaß an Sicherheit und Datenschutz zu gewährleisten. Ich habe die AWTRIX Cloud unter dem Gesichtspunkt der Sicherheit entwickelt. Wenn du die Cloud-Komponente aktivierst, baut deine AWTRIX eine sichere Verbindung zur AWTRIX Cloud auf. Es ist keine weitere Konfiguration erforderlich um die Instanz dem Internet zugänglich zu machen. Außerdem sind keine Benutzernamen, Passwörter, E-Mail-Adressen oder andere private Informationen erforderlich und der Cloud-Server speichert keine Informationen über die Verbindungen.

Die Cloud-Verbindung ist Teil der Premium-Funktionalität.

## So funktioniert es

Wenn du die Cloud-Funktionalität aktivierst, verbindet sich AWTRIX mit dem Cloud-Server (der Server ist vollständig selbst geschrieben, ich verwende keine Cloud-Software von Drittanbietern). Nach erfolgreicher Verbindung generiert AWTRIX ein eigenes 12-stelliges Token und sendet es zur Anmeldung an den Server. Diese Verbindung wird dann dem Token zugeordnet. Es ist nicht möglich, auf andere Verbindungen zuzugreifen, da jede einzelne als ein eigener Thread instanziiert wird.

Ein Post-Request an die AWTRIX-Cloud mit dem eigenen Token leitet die Nachricht an die verknüpfte Verbindung weiter. Wird das Token nicht gefunden, läuft die Anfrage ins leere und wird nicht bearbeitet.

Du hast jederzeit die Möglichkeit, den Token neu zu generieren. 


## Verwendung von IFTTT mit der AWTRIX-Cloud

Einige Beispiele, was du mit IFTTT und AWTRIX Cloud machen kannst

- Anzeige des aktuellen Titels, der mit Spotify gespielt wird
- Anzeige einer beliebigen Benachrichtigung von deinem Smartphone
- Anzeige eingehender oder verpasster Anrufe
- Schalte  AWTRIX aus, wenn du das Haus verlässt
- Bitte beachte, dass IFTTT nicht so viele Dienste für iOS hat wie für Android. Aber natürlich können viele IFTTT Dienste auch ohne Smartphone genutzt werden.


Jeder in der Dokumentation beschriebene API-Befehl kann an die Cloud gesendet werden und wird auf sichere Weise an deine AWTRIX weitergeleitet.

Dieses Beispiel zeigt, wie du dein erstes IFTTT-Applet so einrichtest, dass es neue E-Mails aus Gmail anzeigt.

**AWTRIX auf die Nutzung der Cloud vorbereiten**

Aktiviere die Cloud-Konnektivität in den Premiumbereich in den Systemeinstellungen.
Nach dem speichern wird der 32-stellige Cloud-Token generiert. Verwahre diesen Token sicher auf! Jeder mit diesem Token könnte deine AWTRIX steuern.

   1. Erstelle ein Konto bei https://ifttt.com/join
   2. Gehe zu "My Applets" und klicke auf "New Applet".
   3. Klicke auf das blaue "+THIS" und suche nach "Gmail" als Service.
   4. Wähle dann "Any new email in inbox" als Trigger
   5. Klicke auf das blaue "+THAT", suche nach "Webhooks" als Aktion und wähle "Make a web request".
   6. Nun musst du deine URL "bauen":
    https://awtrix.blueforcer.de/cloud?mode=**notify**&token=**xxxx**
    Wobei "mode" den gewünschten API-Endpunkt (basics, notify oder draw) darstellt. Ersetze auch das xxxx durch deinen 32-stelligen Cloud Token
   7. Wähle **POST** als Methode
   8. **application/json** als Content-Typ auswählen
   9. Für den Body die Notification API nutzen:
    {"force":true, "icon":36, "text": "Neue Mail von {{{FromName}}}", "color":[255,255,255]}
    Du kannst die von IFTTT kommenden Eingaben ändern, indem du auf "Add ingredient" klickst und den Text nach deinen Wünschen neu aufbaust.
   10. Klicke dann auf "Create action" und dann auf "Finish".

Jetzt zeigt AWTRIX jedes Mal, wenn eine neue E-Mail im Gmail-Posteingang ankommt, diese auf der Matrix an.

![AWTRIX Pro](\assets\ifttt.png)