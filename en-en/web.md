## **Webinterface**

In order to make the operation as simple as possible for everyone, the complete operation takes place via a web interface.
The standard port is 7000.

Here you can manage all your settings, manage your apps and download new one.

![image alt text](assets/appstore.png)

## **Systemsettings**
Here you will find all relevant settings concerning the operation of AWTRIX.

#### General Settings
- **BootAnimation**
  - shows an animation after boot. 
- **SwitchAnimation**
  - Whether the transition animation between the apps should be displayed.
- **ColorSwitch**
  - Another transition animation. 
- **UppercaseLetters**
  - Converts  all letters to capital letters.      
- **VerboseLog**
  - logging mode that records more information than the usual logging mode. 
- **TextColor**
  - The global texcolor (Red, Green, Blue). All values can be from 0-255 and must be separated by a comma.
- **Brightness**
  - The brightness of the matrix (0-255).
- **AppDuration**
  - Time in seconds to change to the next app.
- **UpdateInterval**
  - Global interval in which all apps are updated. Exceptions are the apps that were manually overwritten (see MyApps).
- **ScrollSpeed**
  - The speed at which the text is scrolled in milliseconds. (The lower the faster, default: 65).  
  
### Automatic Brightness   
- **AutoBrightness**
  - Activates the automatic brightness control. (Only with LDR connected).
    
### Connections   
 After changing you need to restart the server 
- **webServerPort**
  - Port the Webserver listens to.

### USB    
 After changing you need to restart the server
- **USBMatrix**
  - Enable to connect the Matrix via USB (Serialconnection).
    to the server. You need to activate USB also in the AWTRIXcontroller (min. v0.7).
- **USBPort**
  - If USBPort "auto" (for autodetection) doesnt work, you need to insert the Port manually (e.g. "COM5" or "/dev/ttyUSB0")
  
### MQTT 
 After changing you need to restart the server
- **MQTTclient**
  - Connects AWTRIX to an existing MQTT Broker.

## Premium

!> This features are only available with a premium subscription. This subscription will be available later. 
Until then, these functions are absolutely free and fully usable.

 After changing you need to restart the server

- **CloudActive**
  - Enables the Cloud connection.

- **Telegram**
  - enables the bot to control AWTRIX with the telegram messenger.
    To get your BotToken you need to create your bot with BotFather in Telegram.  

- **FritzCaller**
  - Enables the Fritz!Box Call monitor, and displays incoming calls.    
!> The CallMonitor function on the Fritz!Box must be activated (e.g. by entering #96*5* on a telephone connected to the Fritz!Box).
You can also add your Fritz!Box phone book, by export it and [convert the xml to json](http://www.utilities-online.info/xmltojson/). Save it as "fritzbox.json" in the config folder. AWTRIX will show the caller names after restart.

- **FritzBoxIP**
  - IP adress of your Fritzbox (needed for FritzCaller).  


## **MyApps**
The administration of all your apps takes place here.  
Here you can disable, configure or delete your apps  
![image alt text](assets/insta.png)

Every App has its own updateInterval. If it is set to 0, it means that this app together with the other apps will be updated after a global period. (Systemsettings->updateInterval).   
This setting is sufficient for most apps not to exhaust the API quota.  
However, if desired, the interval at which the app fetches new data can be forced. Just enter a timespan in seconds (minimum 10s). 

## **Appstore**
AWTRIX has its own appstore.  
Here all tested apps are provided and can be downloaded or updated.  
After a download you find this app in MyApps.  

https://awtrix.blueforcer.de/apps.html
