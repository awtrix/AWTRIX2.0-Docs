!> Die Hostsoftware ist auf nicht absehbarer Zeit closed source!

Bitte beachten Sie, dass Java nicht sehr ressourcenschonend ist.
Wenn Du einen Raspberry verwenden möchtes, empfehle ich mindestens einen Raspberry 3+ oder vergleichbar. AWTRIX läuft zwar mit einem ZeroW, aber etwas langsamer. 


AWTRIX 2.0 kann auf jeder Plattform (Windows, MacOS, Linux) laufen, die einzige Voraussetzung ist die Unterstützung von Java 8 (1.8_232). Es handelt sich um eine Nicht-GUI-Anwendung, sodass keine Desktop-Umgebung benötigt wird.   
Dieses Tutorial beschreibt die Installation auf einem Linux-Rechner.  


## Schnellstart
Dieses kurze Beispiel zeigt, wie man die Java-Anwendung startet.
Gehen Sie zum nächsten Punkt für die Installation auf einer Linux-Maschine.

Die aktuelle [AWTRIX Java-Anwendung](https://blueforcer.de/awtrix/beta/awtrix.jar)
 herunterladen

 und starten Sie es über die Kommandozeile oder das Terminal. 

**Linux & MacOS:**    
 ``` sudo java -jar awtrix.jar ```      
 **Windows:**    
 ``` java -jar awtrix.jar ```

   
!> **sudo** wird nicht immer benötigt. Es hängt davon ab, in welchem Ordner Sie die Anwendung starten möchten. AWTRIX muss neue Ordner und Dateien erstellen, so dass AWTRIX in wenigen Fällen keine Schreibrechte hat.

Kurz nach dem Start kann das Webinterface über http://awtrix_ip:7000 aufgerufen werden.




## Installation auf einem Linux-Rechner mit Autostart


Überprüfen Sie zunächst, ob Java installiert ist.  
"Java -Version".  
  
Andernfalls installieren Sie die neueste Java8:  
```sudo apt-get install oracle-java8-jdk```` installieren  

Stellen Sie Ihre Zeitzone ein: z.B.  
```` sudo timedatectl set timezone Europe/Berlin```````  


### AWTRIX Server herunterladen**

```sudo mkdir /usr/local/awtrix```  
```cd /usr/local/awtrix```    
```sudo wget https://blueforcer.de/downloads/awtrix.jar```  


### Autostart

Create a file under  **/etc/systemd/system/** with nano or vi. eg.  
```sudo nano /etc/systemd/system/awtrix.service```  
  
Fügen Sie den untenstehenden Code in diese neue Datei ein:

```
[Unit]
Description = AWTRIX Service
After network.target = awtrix.service

[Service]
Type = forking
WorkingDirectory =/usr/local/awtrix
ExecStart = /usr/local/bin/awtrix.sh start
ExecStop = /usr/local/bin/awtrix.sh stop
ExecReload = /usr/local/bin/awtrix.sh reload

[Install]
WantedBy=multi-user.target
```



Erstellen Sie eine neue Datei unter ***/usr/local/bin/*** eg.   
```sudo nano /usr/local/bin/awtrix.sh```  
  
Und fügen Sie diesen Code ein

```
#!/bin/sh
SERVICE_NAME=awtrix
PATH_TO_JAR=/usr/local/awtrix/awtrix.jar
PID_PATH_NAME=/tmp/awtrix-pid
case $1 in
    start)
        echo "Starting $SERVICE_NAME ..."
        if [ ! -f $PID_PATH_NAME ]; then
            sudo nohup java -jar $PATH_TO_JAR /tmp 2>> /dev/null >> /dev/null &
                        echo $! > $PID_PATH_NAME
            echo "$SERVICE_NAME started ..."
        else
            echo "$SERVICE_NAME is already running ..."
        fi
    ;;
    stop)
        if [ -f $PID_PATH_NAME ]; then
            PID=$(cat $PID_PATH_NAME);
            echo "$SERVICE_NAME stoping ..."
            kill $PID;
            echo "$SERVICE_NAME stopped ..."
            rm $PID_PATH_NAME
        else
            echo "$SERVICE_NAME is not running ..."
        fi
    ;;
    restart)
        if [ -f $PID_PATH_NAME ]; then
            PID=$(cat $PID_PATH_NAME);
            echo "$SERVICE_NAME stopping ...";
            kill $PID;
            echo "$SERVICE_NAME stopped ...";
            rm $PID_PATH_NAME
            echo "$SERVICE_NAME starting ..."
            sudo nohup java -jar $PATH_TO_JAR /tmp 2>> /dev/null >> /dev/null &
                        echo $! > $PID_PATH_NAME
            echo "$SERVICE_NAME started ..."
        else
            echo "$SERVICE_NAME is not running ..."
        fi
    ;;
esac
```

Speichern der Datei und Erteilen von Ausführungsrechten

``` sudo chmod +x /usr/local/bin/awtrix.sh``` 

Testen Sie, ob es damit läuft:  
```sudo /usr/local/bin/./awtrix.sh start```     
Testen Sie, ob es mit stoppt:   
```sudo /usr/local/bin/./awtrix.sh stop```     
Testen Sie, ob der Neustart mit:  
```sudo /usr/local/bin/./awtrix.sh restart```     

Wenn alles funktioniert, aktiviere den Dienst mit 
```sudo systemctl enable awtrix``` 


AWTRIX Starten  
```sudo systemctl start awtrix.service ```  
AWTRIX Stoppen 
```sudo systemctl stop awtrix.service```   
AWTRIX Neustarten
```sudo systemctl restart awtrix.service``` 