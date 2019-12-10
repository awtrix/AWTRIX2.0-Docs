Das Ziel der AWTRIX Cloud ist es, die Lücke zwischen Ihrer lokalen Instanz und den Diensten in der Cloud zu schließen und gleichzeitig ein Höchstmaß an Sicherheit und Datenschutz zu gewährleisten. Ich habe die AWTRIX Cloud unter dem Gesichtspunkt der Sicherheit entwickelt. Wenn Sie die neue Cloud-Komponente aktivieren, baut Ihre Instanz eine sichere Verbindung zur AWTRIX Cloud auf. Es ist keine weitere Konfiguration erforderlich oder die Instanz dem Internet zugänglich zu machen. Außerdem sind keine Benutzernamen, Passwörter, E-Mail-Adressen oder andere private Informationen erforderlich und der Cloud-Server speichert keine Informationen über die Verbindungen.

Die Cloud-Verbindung wird während der Startphase kostenlos sein. Später wird es in einem günstigen Abonnement verwendbar sein. Die Abonnementgebühr deckt nicht nur die Kosten für den Betrieb der AWTRIX Cloud. Die Einnahmen werden auch für die Infrastruktur des Betriebs anderer AWTRIX-Dienste wie der Icon-Datenbank oder des Community-Forums verwendet.
So funktioniert es

Wenn Sie die Cloud-Funktionalität aktivieren, verbindet sich AWTRIX mit dem Cloud-Server (der Server ist vollständig selbst geschrieben, ich verwende keine Cloud-Software von Drittanbietern). Nach erfolgreicher Verbindung generiert AWTRIX ein eigenes Token und sendet es zur Anmeldung an den Server. Diese Verbindung wird dann dem Token zugeordnet. Es ist nicht möglich, auf andere Verbindungen zuzugreifen, da jede einzelne als ein eigener Thread instanziiert wird.

Ein Post-Request an die AWTRIX-Cloud mit dem eigenen Token leitet die Nachricht an die verknüpfte Verbindung weiter. Wird das Token nicht gefunden, läuft die Anfrage leer und wird nicht bearbeitet.

Sie haben jederzeit die Möglichkeit, den Token neu zu generieren. 