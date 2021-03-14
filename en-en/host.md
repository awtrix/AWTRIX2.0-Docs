!> The host software is closed source for not foreseeable time!


AWTRIX 2.0 can run on any platform (Windows, MacOS, Linux), the only requirement is the support of Java 8 (1.8_232). It is a non-GUI application, so no desktop environment is required.  However, it is advisable not to use a desktop distribution to save processor power and memory. So use something like Rasbian lite.  

Please note that Java is not very resource efficient.
If you want to use a Raspberry, I recommend at least a Raspberry 3+ or comparable. AWTRIX runs with a ZeroW, but slower. 


This tutorial describes the installation on a Linux machine. 


## Quickstart
This short example shows how to start the Java application.
Go to the next point for installation on a Linux machine.

The current [AWTRIX Java Application](https://blueforcer.de/awtrix/stable/awtrix.jar)
 download

 and run it from the command line or terminal. 

**Linux & MacOS:**    
 `` sudo java -jar awtrix.jar ``      
 **Windows:**    
 ``java -jar awtrix.jar ``

!> **sudo** is not always needed. It depends in which folder you want to start the application. AWTRIX has to create new folders and files, so in a few cases AWTRIX has no write permissions.


## Linux Installer
Enter the following command in your SSH terminal for automatic installation  
 ``wget -N https://blueforcer.de/awtrix/awtrix.sh ; sudo sh awtrix.sh``

 
?> Shortly after the start the web interface can be accessed via http://awtrix_ip:7000.

Starting AWTRIX  
``Sudo service awtrix start``  
Stop AWTRIX  
 ``Sudo service awtrix stop ``
AWTRIX Restart  
``Sudo service awtrix restart`` 


## Docker
Recommended: [Dockerhub](https://hub.docker.com/r/whyet/awtrix2)
  
## Update
Replace the awtrix.jar or run the setupscript again.