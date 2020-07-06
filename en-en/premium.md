
This category offers great features that are only unlocked by purchasing a Premium Key. You can get this key in my [Shop](https://blueforcer.de/shop/).
By purchasing a key you support me in the further development of AWTRIX and in paying my costs such as server rental, purchase of new components etc.
These functions will be expanded regularly.


**AWTRIX Cloud**  
Activates the connection to the AWTRIX Cloud. You can find further information about this [here](/en-en/cloud.md).  
After activation you will receive a token which you need for external control. With "Revoke Token" you can have a new one created at any time.

**Fritz!Box Call Monitor**  

!> To activate the call monitor in the Fritz!Box, you must enter the following number on a connected telephone and call: ``#96*5*``  

Anyone who owns a FritzBox from AVM can use this function to integrate the FritzBox into AWTRIX, so that, for example, information about an incoming call or the caller's telephone number is displayed.
  
Enter the IP address of the FritzBox and, if desired, set up the telephone book. If a telephone book is stored, AWTRIX will display the appropriate name when a call is received, otherwise the telephone number.   You can either export a phonebook from the FritzBox and [convert it to a JSON](http://www.utilities-online.info/xmltojson/) or, if that doesn't work, create your phonebook manually. You just have to use a new line for each number. The structure is very simple:
``` BASH
01514875965=Blueforcer
01603262987=Günther
06185772637=Hostel
and so on...
```  

**Pushover**  
This allows you to send notifications to AWTRIX via Pushover. The login data entered will of course remain local to your AWTRIX.

**Sleep Mode**  
Sleep mode allows you to set a period of time during which AWTRIX will "sleep". During this phase, AWTRIX will not respond to any API commands. You have the option to select a defined app, which will be displayed continuously during this phase. You can also set the brightness. Enter 0 here to switch off the matrix completely.

**Alarm Clock**   
Here you can set an alarm that is repeated daily. Besides an individual icon, you can also play a sound file.

**Yeelight**  
Here you have the possibility to connect a Yeelight RGB lamp with AWTRIX. Besides the normal "light bulbs" also Strips and Bedside Lamp are supported. Enter the IP address of the Yeelight after you have activated the LAN mode in the Yeelight App. You can now play various effects via the API. For example, you can activate light effects in addition to sounds for your important notifications.

**E1.31**  
Alows you to send E1.31 (like Artnet) data to your AWTRIX. With xLight for example you need to add a new Controller with 2 universes with 384 channels each. Also add a new matrix layout with 8 strings á 32 Strands and top left starting position. When you start to send data, AWTRIX will stop its normal operation and shows your data. 5s after you stop sending data, AWTRIX will return to normal operation.

**Alexa**  
This only emualtes a Phillips Hue lamp, so you can control the textolor, brightness and on/off via Amazons Alexa. (The integrated emulation server uses Port 80, make sure it is not used by any other programm).

**Python**  
You can write simple python apps for awtrix.
AWTRIX uses the Java ScriptEngine Nashorn together with jython for that. Because the awtrix runnable jar contains the jython library, the file size is now 54mb.
Place your python file in the apps folder and restart awtrix. all python apps will be loaded like regular native apps.


!> Accessing a pythonscript will block awtrixs mainthread. That means if your python function contains heavy loops or other time-consuming things like downloads, Awtrix stops for that time. So keep your processings fast, otherwise unexpected side effects may occur.  
All python apps will be loaded as a module. The python import system uses a cache, so if you change something in your python app, it will be not loaded since the module is already cached. Until i find a solution for that, you can rename your app as a workaround.


Example of an app.py:

!> All variable names and function names must remain exactly as they are

```python
import urllib, json

Version = 1.0
Author = "Blueforcer"
Description = "AWTRIX app written in python"
HowToSetup = "Example Text"
Covericon = 1164
Repeat=2
MoveIcon=True
CustomScreen=False #not working yet
Settings = {"Prefix": "MissionName: "} #Usersettings

#Dont modfiy this
def init():	
    return [Version,Author,Description,HowToSetup,Covericon,Repeat,MoveIcon,CustomScreen]

def started():
    print("App started")

def running():
    print("App running")

def finished():
    print("App finished")

def getSettings():
    return Settings   

#This function is called when AWTRIX trigger all apps to do their downloads.
#Unlike native apps you will need to return the iconID and Text wich should be show
#You also will get a map of the Userettings to work with
def getData(settings):
    url = "https://api.spacexdata.com/v3/launches/next"
    response = urllib.urlopen(url)
    data = json.loads(response.read())
    SpaceXMission = data["mission_name"]
    return [1164,settings["Prefix"] + SpaceXMission]
```    