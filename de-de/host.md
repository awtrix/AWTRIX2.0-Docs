?> Die Host Software für unbestimmte Zeit closed-source!

Bitte beachten Sie, dass Java nicht sehr ressourcenschonend ist.
Wenn Sie eine Himbeere verwenden möchten, empfehle ich mindestens eine Himbeere 3+ oder vergleichbar. Es läuft mit einem ZeroW, aber etwas langsamer.

AWTRIX 2.0 kann auf jeder Plattform (Windows, MacOS, Linux) laufen, die einzige Voraussetzung ist die Unterstützung von Java8. Es handelt sich um eine Nicht-GUI-Anwendung, so dass Sie keine Desktop-Umgebung benötigen.  
Dieses Tutorial beschreibt die Installation auf einem Linux-Rechner.

## Schnellstart

Dieses kurze Beispiel zeigt, wie man die Java-Anwendung startet.
Gehen Sie zum nächsten Punkt für die Installation auf einer Linux-Maschine.

Die aktuelle Java-Datei herunterladen
[AWTRIX Java-Anwendung](https://blueforcer.de/downloads/awtrix.jar)

und starten Sie es über die Kommandozeile oder das Terminal.

**Linux & MacOS:**  
`sudo java -jar awtrix.jar`  
 **Windows:**  
`java -jar awtrix.jar`

!> **sudo** wird nicht immer benötigt. Es hängt davon ab, in welchem Ordner Sie die Anwendung starten möchten. AWTRIX muss neue Ordner und Dateien erstellen, so dass AWTRIX in wenigen Fällen keine Schreibrechte hat.

Kurz nach dem Start kann das Webinterface über http://awtrix_ip:7000 aufgerufen werden.

## Raspberry Installer

Geben Sie folgenden Befehl in Ihr Terminal zur automatischen Installation ein
`wget -N https://blueforcer.de/downloads/AWTRIX.sh ; sudo sh AWTRIX.sh`

Kurz nach dem Start kann das Webinterface über http://awtrix_ip:7000 aufgerufen werden.
Sie können diesen Befehl auch verwenden, um Ihren AWTRIX zu aktualisieren.

## Installation auf einem Linux mit Autostart

Überprüfen Sie zunächst, ob Java installiert ist.  
"Java -Version".

Andernfalls installieren Sie die neueste Java8:  
``sudo apt-get install oracle-java8-jdk` installieren

Stellen Sie Ihre Zeitzone ein: z.B.  
`` sudo timedatectl set timezone Europe/Berlin```

### Java auf Version 1.8.0_201 aktualisieren (für Raspberry)

- Laden Sie das Paket von https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html herunter (hier benötigen Sie "Linux ARM 32 Hard Float ABI").
- Paket nach Himbeere nach /home/pi verschieben (mit FileZilla oder WinSCP)
- Paket auspacken
  - `sudo tar zxvf jdk-8u201-linux-arm32-vfp-hflt.tar.gz -C /opt`
- Java aktivieren und Pakete löschen
  - ``sudo update-alternativen --installieren /usr/bin/javac javac /opt/jdk1.8.0_201/bin/javac 1`
  - ``sudo update-alternativen --install /usr/bin/java java /opt/jdk1.8.0_201/bin/java 1`
  - ``rm jdk-8u201-linux-arm32-vfp-hflt.tar.tar.gz`
  - ``sudo update-alternatives --config javac` **Hier mit Auswahl 1 Version 1.8.0_201** auswählen
  - ``sudo update-alternatives --config java` **Hier mit Auswahl 1 Version 1.8.0_201** auswählen
  - Testen Sie, ob es mit ``Java -version` funktioniert.

### AWTRIX Server herunterladen\*\*

``sudo mkdir /usr/local/awtrix`sudo mkdir /usr/local/awtrix`cd /usr/local/awtrix`cd /usr/local/awtrix`.  
"Sudo wget https://blueforcer.de/downloads/awtrix.jar

\*### **Autostart**

Erstellen Sie eine Datei unter **/etc/systemd/system/** mit nano oder vi. z.B.  
`sudo nano /etc/systemd/system/system/awtrix.service`

Fügen Sie den untenstehenden Code in diese neue Datei ein:

```
(Einheit)
Beschreibung = AWTRIX Service
Nach network.target = awtrix.service

[Service]
Typ = Gabelung
Arbeitsverzeichnis =/usr/local/awtrix
ExecStart = /usr/local/bin/awtrix.sh start
ExecStop = /usr/local/bin/awtrix.sh stop
ExecReload = /usr/local/bin/awtrix.sh neu laden

[Installieren]
WantedBy=multi-user.target
```

Erstellen Sie eine neue Datei unter **_/usr/local/bin/_** eg.  
``sudo nano /usr/local/bin/awtrix.sh`

Und fügen Sie diesen Code ein

```
#!/bin/sh
SERVICE_NAME=awtrix
PATH_TO_JAR=/usr/local/awtrix/awtrix/awtrix.jar
PID_PATH_NAME=/tmp/awtrix-pid
Fall $1 in
    Start)
        echo "Starten von $SERVICE_NAME...."
        wenn [ ! -f $PID_PATH_NAME ]; dann
            sudo nohup java -jar $PATH_TO_JAR /tmp 2>> /dev/null >> /dev/null &
                        echo $! > $PID_PATH_NAME
            echo "$SERVICE_NAME gestartet...."
        sonst
            echo "$SERVICE_NAME läuft bereits...."
        fi
    ;;
    stop)
        wenn [ -f $PID_PATH_NAME ]; dann
            PID=$(cat $PID_PATH_NAME);
            echo "$SERVICE_NAME stoping ...."
            kill $PID;
            echo "$SERVICE_NAME gestoppt...."
            rm $PID_PATH_NAME_NAME
        sonst
            echo "$SERVICE_NAME läuft nicht...."
        fi
    ;;
    restart)
        wenn [ -f $PID_PATH_NAME ]; dann
            PID=$(cat $PID_PATH_NAME);
            echo "$SERVICE_NAME stoppt....";
            kill $PID;
            echo "$SERVICE_NAME gestoppt....";
            rm $PID_PATH_NAME_NAME
            echo "$SERVICE_NAME starting ...."
            sudo nohup java -jar $PATH_TO_JAR /tmp 2>> /dev/null >> /dev/null &
                        echo $! > $PID_PATH_NAME
            echo "$SERVICE_NAME gestartet...."
        sonst
            echo "$SERVICE_NAME läuft nicht...."
        fi
    ;;
esac
```

Speichern der Datei und Erteilen von Ausführungsrechten

`sudo chmod +x /usr/local/bin/awtrix.sh`

Testen Sie, ob es damit läuft:  
` sudo /usr/local/bin/./awtrix.sh start`````` Testen Sie, ob es mit stoppt: `sudo /usr/local/bin/./awtrix.sh stop``  
Testen Sie, ob der Neustart mit:  
`sudo /usr/local/bin/./awtrix.sh Neustart`

Wenn alles funktioniert, aktivieren Sie den Dienst mit dem Befehl

``sudo systemctl enable awtrix```

So führen Sie awtrix aus  
` sudo systemctl start awtrix.service `````` So stoppen Sie awtrix `sudo systemctl stop awtrix.service```  
So starten Sie awtrix neu

Übersetzt mit www.DeepL.com/Translator

As USBPort you need to enter **/dev/ttyS0** in the Settingsmenu via Webinterface. Then restart the Server.
