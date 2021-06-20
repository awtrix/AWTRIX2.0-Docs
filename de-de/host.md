!> Die Hostsoftware ist auf nicht absehbarer Zeit closed source!

AWTRIX 2.0 kann auf jeder Plattform (Windows, MacOS, Linux) laufen, die einzige Voraussetzung ist die Unterstützung von Java 8 (1.8_232). Es handelt sich um eine Nicht-GUI-Anwendung, sodass keine Desktop-Umgebung benötigt wird.  Es istallerdings ratsam auf eine Desktop Distribution zu verzichten, um Prozessorleistung und Arbeitsspeicher zu sparen. Nutze daher so was wie Rasbian lite.

Bitte beachte, dass Java nicht sehr ressourcenschonend ist.
Wenn Du einen Raspberry verwenden möchtest, empfehle ich mindestens einen Raspberry 3+ oder vergleichbar. AWTRIX läuft zwar mit einem ZeroW, aber  langsamer.

Dieses Tutorial beschreibt die Installation auf einem Linux-Rechner.

## Schnellstart
Dieses kurze Beispiel zeigt, wie man die Java-Anwendung startet.
Gehe zum nächsten Punkt für die Installation auf einer Linux-Maschine inkl. Autostart.

Die aktuelle [AWTRIX Java-Anwendung](https://blueforcer.de/awtrix/stable/awtrix.jar) herunterladen und starte es über die Kommandozeile oder das Terminal.

**Linux & MacOS:**

```bash
sudo java -jar awtrix.jar
```

**Windows:**

```bash
java -jar awtrix.jar
```

!> **sudo** wird nicht immer benötigt. Es hängt davon ab, in welchem Ordner du die Anwendung starten möchtest. AWTRIX muss neue Ordner und Dateien erstellen, so dass AWTRIX in wenigen Fällen keine Schreibrechte hat.

## Linux Installer
Gebe zur automatischen Installation folgenden Befehl in dein SSH Terminal ein

```bash
wget -N https://blueforcer.de/awtrix/awtrix.sh ; sudo sh awtrix.sh
```

?> Kurz nach dem Start kann das Webinterface über http://awtrix_ip:7000 aufgerufen werden.

AWTRIX Starten

```bash
sudo service awtrix start
```

AWTRIX Stoppen

```bash
sudo service awtrix stop
```

AWTRIX Neustarten

```bash
sudo service awtrix restart
```

## Docker
Empfohlen: [Dockerhub](https://hub.docker.com/r/whyet/awtrix2)

## Update
Ersetze die awtrix.jar oder führe das setupscript erneut aus.
