# This section is still under development. Ignore it!
___
  
![image alt text](assets/code.png)

## Programming language  
AWTRIX and its Apps are written in B4X Language. 
B4X uses a Proprietary dialect of Visual Basic (hereinafter called "B4X").

## IDE (development environment)
B4J â Modern âVB6 likeâ development tool for cross platform desktop, server and IoT solutions. B4J is a 100% free. With B4J you can easily create desktop applications (UI), console programs (non-UI) and server solutions.
The compiled apps can run on Windows, Mac, Linux and ARM boards (such as Raspberry Pi). The compiled Apps are native Java applications.  
  
[Download B4J](https://www.b4x.com/b4j.html)


## Apps definition
AWTRIX Apps are Java libraries that can be loaded at runtime.
Defined functions called by AWTRIX transfer the information about the screen.

## Procedure 
The functions are divided into four main parts:  
  
**Initialization**  
AWTRIX initializes the app and checks if all necessary settings parameters are set. If so, the app will be included in AWTRIX's internal apploop.  

**Start**  
At every start AWTRIX asks for the desired tickrate (in ms) in which the drawing routine should be called.It also return the set app duration to know how long this app will be active.

**Rendering**  
AWTRIX called the function each set Tick.
AWTRIX expects, with each tick, a list of all drawing commands that represent a frame.
After receiving this list, AWTRIX draws all commands step by step and then displays the finished rendered frame.

**Update**
While updating, AWTRIX asks the APP how many Downloads are needed (ususal one). Then (for each single download) it requests the URL for the desired data, download it, and return the response as String and InputStream for further processing inside the App.
AWTRIX has an global configurable Updateinterval after wich every App will be updated. The user can also force each app to update after a specific duration.



# Starting
To develop your first App its better to start with the Template [Download here](https://github.com/awtrix/AWTRIX2.0-Apps/tree/master/templateApp)
Open the templatePlugin.b4j with the B4J IDE. You can ignore the "Main" Code Module and switch to the "templatePlugin" class.
First step ist to rename the class (Project -> Rename Module). The name should always end with "Plugin"

At Class_Globals you should set the following Variables:  
  
**AppName**  
plugin name (must be unique)  
**AppVersion**  
version of the App  
**tickInterval**  
Tickinterval in ms (should be 65 by default)  
**needDownloads**  
How many downloadhandlers should be generated  
**updateInterval**  
force update after X seconds. 0 for systeminterval  
**lockApp**    
If set to true AWTRIX will wait for the " finish" command before switch wo the next app.  
**iconID**   
default Icon from AWTRIXER.  
**description**  
The description of you App. Use HTML to style your text. This description will be shown in the Appstore and in MyApps  
**setupInfos**  
Use HTML to describe the Settings wich is necessary for you App.  
**appSettings**    
Here you need to define a map containing all Settings can be changed by the user. You can set a default value or Null. If you set Null the User has to enter a Value before AWTRIX will show this App.  
You can get each setting from this map with appSettings.Get("Text")


# Build Frame

blablabla

Available drawing functions:
- text
- line
- circle
- fillCircle
- rect
- pixel
- fill
- bmp