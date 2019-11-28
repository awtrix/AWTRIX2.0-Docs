!> The server software is closed Source!

!> Please note that Java is not very resource friendly.
If you want to use a Raspberry i recommend at least a Raspberry 3+ or comparable. It runs on a ZeroW but a bit slower. 


AWTRIX 2.0 can run on any platform (Windows, MacOS, Linux), the only requirement is the support of Java8. It is a non-GUI application so you doesnt need an desktop environment.   
This Tutorial describes the installation on a Linux machine.  


## **Quickstart**
This short example shows how to start the Java application.
Move to the next point for installing on a Linux machine

Download the current java  file
[AWTRIX Java application](https://blueforcer.de/downloads/awtrix.jar)

 and start it via command line or terminal 

 **Linux & MacOS:**  
 ``` sudo java -jar awtrix.jar ```    
 **Windows:**  
 ``` java -jar awtrix.jar ```  

   
!> **sudo** is not always needed. It depends on the folder in which you want to start the Application. AWTRIX need to create new folders and files, so in few cases AWTRIX has no write permissions.

Shortly after the start the web interface can be called via http://awtrix_ip:7000.




## **Installing on a Linux machine with Autostart**


First check if Java is installed  
```java -version```  
  
Otherwise install the latest Java8:  
```sudo apt-get install oracle-java8-jdk```  

Set your timezone: e.g  
``` sudo timedatectl set-timezone Europe/Berlin```  
### Update Java to version 1.8.0_201 (for Raspberry)

- Download the package from https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html (here you need "Linux ARM 32 Hard Float ABI")
- Move package to Raspberry to /home/pi (with FileZilla or WinSCP)
- Unpack package
  - ```sudo tar zxvf jdk-8u201-linux-arm32-vfp-hflt.tar.gz -C /opt```
- Enable Java and delete packages
  - ```sudo update-alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_201/bin/javac 1```
  - ```sudo update-alternatives --install /usr/bin/java java /opt/jdk1.8.0_201/bin/java 1```
  - ```rm jdk-8u201-linux-arm32-vfp-hflt.tar.gz```
  - ```sudo update-alternatives --config javac``` **Here with selection 1 Select version 1.8.0_201**
  - ```sudo update-alternatives --config java```  **Here with selection 1 Select version 1.8.0_201**
  - Test if it works with ``` java -version```

### **Download AWTRIX Server**

```sudo mkdir /usr/local/awtrix```  
```cd /usr/local/awtrix```    
```sudo wget https://blueforcer.de/downloads/awtrix.jar```


### **Autostart**

Create a file under  **/etc/systemd/system/** with nano or vi. eg.  
```sudo nano /etc/systemd/system/awtrix.service```  
  
Paste the code below in this new file:
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


Create a new file under ***/usr/local/bin/*** eg.   
```sudo nano /usr/local/bin/awtrix.sh```  
  
And paste this code
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

save the file and give execution permisions

``` sudo chmod +x /usr/local/bin/awtrix.sh``` 


Test that it runs with:  
```sudo /usr/local/bin/./awtrix.sh start```     
Test that it stops with:   
```sudo /usr/local/bin/./awtrix.sh stop```     
Test that it restarts with:  
```sudo /usr/local/bin/./awtrix.sh restart```     

If everything is working, enable the service with the command

```sudo systemctl enable awtrix```  




To run awtrix  
```sudo systemctl start awtrix.service ```   
To stop awtrix   
```sudo systemctl stop awtrix.service```   
To restart awtrix   
```sudo systemctl restart awtrix.service``` 


### **Update**  
```sudo -i```  
```cd /usr/local/awtrix```  
```systemctl stop awtrix.service```  
```wget -N awtrix.jar https://blueforcer.de/downloads/awtrix.jar```  
```systemctl start awtrix.service```  


## **Run AWTRIX on android device**
!> This needs a powerful device. Ive tested it on a Galaxy S8+ and it runs without any problems.

- [Download Termux](https://play.google.com/store/apps/details?id=com.termux) from Google Playstore
- open it and run follwing command:  
```pkg install wget proot -y && wget https://raw.githubusercontent.com/EXALAB/AnLinux-Resources/master/Scripts/Installer/Debian/debian.sh && bash debian.sh```
- start debian console with   
```./start-debian.sh```
- update debian   
```apt-get update```
- install Java   
```apt-get install default-jre```
- download AWTRIX   
```wget https://blueforcer.de/downloads/awtrix.jar```
- run AWTRIX   
```java -jar awtrix.jar```
