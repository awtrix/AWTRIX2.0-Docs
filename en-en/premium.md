
This category offers great features that are only unlocked by purchasing a Premium Key. You can get this key in my [Shop](https://blueforcer.de/shop/).
By purchasing a key you support me in the further development of AWTRIX and in paying my costs such as server rental, purchase of new components etc.
These functions will be expanded regularly.


**AWTRIX Cloud**  
Activates the connection to the AWTRIX Cloud. You can find further information about this [here](/en-en/cloud.md).  
After activation you will receive a token which you need for external control. With "Revoke Token" you can have a new one created at any time.

**Fritz!Box Call Monitor**  
Anyone who owns a FritzBox from AVM can use this function to integrate the FritzBox into AWTRIX, so that, for example, information about an incoming call or the caller's telephone number is displayed.

To activate the call monitor in the Fritz!Box, you must enter the following number on a connected telephone and call: ``#96*5*``  
  
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
