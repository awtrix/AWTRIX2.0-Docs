## **Customize**

You can replace the Bootanimation and also the Switchinganimation (transition between two Apps) on your own.     
[You will find some user-made in the Forum](https://forum.blueforcer.de/d/106-animated-drawings/).


### Bootanimation 
[Create a animation with AWTRIXER for Desktop](https://docs.blueforcer.de/#/v2/awtrixer?id=animations) and export it for the Drawing API.  
Then copy the created json file to the config folder and rename it to **boot.json**.  

### Switchanimation
[Create a animation with AWTRIXER for Desktop](https://docs.blueforcer.de/#/v2/awtrixer?id=animations) and export it for the Drawing API.  
Then copy the created json file to the config folder and rename it to **switch.json**.  

#### *Pro-Tipp*
To be more flexible, you can use any drawing command from the [API](https://docs.blueforcer.de/#/v2/api?id=possible-commands) to build your json.

### AppLoop
The order in which the apps are displayed can be customized.  
e.g **Time -> Facebook -> Time -> Matrix -> Time -> Instagram** ...  

There are 2 ways to do this
- modify the appList file in the config folder. Each app must be in one line. After saving you need to restart the server
- via [API](https://docs.blueforcer.de/#/v2/api?id=applist)