
## AWTRIX Premium

This category offers great features that are only unlocked by purchasing a premium key. These functions will be expanded regularly. You can get this key in my [Shop](https://blueforcer.de/shop/).   
By purchasing a key you support me in the further development of AWTRIX and in paying my costs such as server rental, purchase of new components etc.  
One Key is **per user** and can used on up to 3 different AWTRIX devices. If you need a 4th Awtrix with premium for your own use, just write me. We will surely find a solution.

?> [In your account](https://blueforcer.de/shop/mein-konto/license-keys/) you can view your previous activations at any time and delete them if necessary.



## Currently available premium functions

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
This only emualtes a Phillips Hue lamp, so you can control the textcolor, brightness and on/off via Amazons Alexa. The integrated emulation server uses Port 80, make sure it is not used by any other programm. (tested with a Amazon Dot Gen3)

**Telegram**  
This allows you to control AWTRIX via telegram. Beside some special functions, you can also send any text which will be displayed.
[To use the AWTRIX telegram bot, you must create a bottoken](https://www.siteguarding.com/en/how-to-get-telegram-bot-api-token)


## Troubleshooting

!> **Please note:** If you are using **Docker**, rebuilding the container will also change the hardware ID. To work around this  start the container in host mode or disable your premium account before each rebuild -> After that you can enter the key again without using up your activations. When restarting a container this problem does not occur

- I get the message **Activation limit for license key reached (3/3)**. Either you really reached the limit and you need to deactivate the Premium function at your previously AWTRIX. This will also happen if you share the keys with others (wich is of course not allowed). For users who have been using AWTRIX for a long time, but have only just updated it, problems may occur because the way my license server works has changed. In this case you can deactivate your activations under ["My Account"](https://blueforcer.de/shop/mein-konto/license-keys/). This is only necessary once. 

- I get the message **Premium cannot be activated because the hardware binding does not match**. This means that AWTRIX cannot be activated because your hardware has changed. AWTRIX creates a hardware-specific file when Premium is activated for the first time. If you now copy your AWTRIX installation to another hardware platform, you also copy the specific file that still contains the hardware ID of your old platform, so that the key you entered is invalid on the new platform. AWTRIX automatically deletes this hardware binding, so you can enter the key again. This will of course reduce the number of activations you have available. You can deactivate your premium functionality on your old platform at any time, which will also increase the number of available activations. You can deactivate your activations at ["My Account"](https://blueforcer.de/shop/mein-konto/license-keys/) at any time if you don't have the possibility to remove them directly from an AWTRIX.
