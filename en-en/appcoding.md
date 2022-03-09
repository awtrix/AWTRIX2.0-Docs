
  
![B4J](..\assets\/coding/code.png)

## Programming language  
AWTRIX and its apps are written in B4X. 
B4X uses a proprietary dialect of Visual Basic (hereinafter referred to as "B4X").

## IDE (Development Environment)
B4J is a modern "VB6-like" and 100% free development tool for cross-platform desktop, server and IoT solutions.
The compiled apps can be run on Windows, Mac, Linux and ARM boards (e.g. Raspberry Pi). The compiled apps are native Java applications.  
  
[Download B4J](https://www.b4x.com/b4j.html)
  
AWTRIX uses JDK 8_232, as this version is supported by most platforms without any problems. The JDK is necessary for developing apps and using the IDE.  
[Download OpenJDK8](https://github.com/ojdkbuild/ojdkbuild/releases/download/java-1.8.0-openjdk-debug-1.8.0.232-2.b09/java-1.8.0-openjdk-debug-1.8.0.232-2.b09.ojdkbuild.windows.x86_64.zip)

## Apps definition
AWTRIX Apps are Java libraries that can be loaded at runtime.
Defined functions called by AWTRIX transfer the information to the matrix.

## First Steps
For the first app it is better to start with the template [Download](https://github.com/awtrix/AWTRIX2.0-Apps/tree/master/Template)  
After you have opened the Template.b4j with B4J, it should look like this:  
  
![B4J](..\assets\/coding/start.png)

First you should give your app a unique name.  
Prerequisites for naming:
- No umlauts
- No spaces
- No special characters
- The name is not yet assigned by another app

The app name must be entered first at **4 points**:
- In the main class ``#LibraryName:Template``
- Change to the Template class and use the function ```Public Sub Initialize() As String`` to add your app name to ``App.name = "Template
- Go to Rename Project Module and give this class your app name
- Save the project to a new location with the same app name

## App Configuration
Now it goes to the **configuration** of your app. This is all done in the Initialize() function. There are several parameters that can or must be set.

### Necessary

**App.name**    
 The name of the App. This is used in the Appstore, MyApps and as a file name

**App.version**      
The verison of the App. The version must be numeric and can contain up to 2 decimal places (e.g. 1.25)

**App.description**    
The description of the App. Describe your app here briefly and concisely. You can optionally format the text as HTML

**App.author**    
The creator of the App. So everyone knows who invested blood, sweat and tears here.

**App.coverIcon**    
The icon of your app. This requires an IconID from the database. You can create and upload your own icon in the Icon Creator

**App.settings**    
The possible settings of the App. A map is generated which consists of keys and values. e.g. ```CreateMap("Key": "Value")`` You can either enter standard values so that your app can start immediately or you can leave the value empty ("") so that AWTRIX informs the user that there is still something to adjust.
AWTRIX will not load the app until all settings are set! 

**App.setupDescription**    
Explain briefly how to set up your app or where to get the necessary data. You can optionally format the text as HTML

**App.downloads**   
Here you specify how many downloads your app needs. Multiple downloads are necessary, for example if one download is dependent on another.

**App.icons**   
Here you specify which icons your app will need. These will also be downloaded by AWTRIX before the app is started.

**App.tick**   
Here you specify how fast your app should run. For a simple text 65 (ms) has proven to be perfect.

### Optional

**App.lock**   
If set to true, AWTRIX waits for the "finish" command before switching to the next app.

**App.game**   
If set to true, your app is treated as a game.

**App.howToPlay**   
If you program a game, you can describe how to play it here.

**App.forceDownload**   
If set to true, AWTRIX initiates the download routine before each start of the app.

**App.hidden**   
If set to true, AWTRIX will not actively include this app in the apploop.

**App.shouldShow**   
If set to false, AWTRIX will skip this app in the apploop, this is useful if you want to display the app in a controlled way.

**App.polling**   
A sub can be specified here that is triggered in the background every 5 seconds. Here you can decide if the app should be displayed again.


## Events
AWTRIX offers several events that are triggered at a specific time:

**App_Started**   
This sub is called shortly before AWTRIX displays your app.

**App_Exited**   
This sub is called when AWTRIX switches to the next app and pauses it.

**App_iconRequest**   
This sub is called shortly before AWTRIX displays your app.
If you need another icon, you can edit your icon list here.

**App_settingsChanged**   
If the user changes any settings on your app, this sub is called.

**App_startDownload**   
Is called by Awtrix with every app update. You must return a URL for each download handler

**App_evalJobResponse**   
Called after each requested download. Here the downloaded data can be processed.

**App_genFrame**  
This sub is called continuously while your app is running. You can set the interval with App.Tick.
This is where AWTRIX is passed the drawing routines that will ultimately be displayed on the matrix. Calculations that only need to be performed once should not be added here.

**App_controllerButton**  
When you create a game, use this sub to get the keystrokes from the web interface or the game controller.
button defines the ButtonID of the controller, you are true if it is pressed.

**App_controllerAxis**  
When you create a game, use these sub to get the analog values of the connected controller.



## Download data
To develop an app that displays data from the Internet, AWTRIX offers almost all possibilities. 
When AWTRIX boots, the download is initiated for each app, but several can also be started. How many "download handlers or job numbers" AWTRIX should provide is specified in the configuration **App.downloads**. 
As soon as AWTRIX starts the download, the event **App_startDownload** is called using the JobNr. For each job number, the sub "App_evalJobResponse" is called after a successful download and the requested data is returned. This procedure is processed with each individual download.

**App.Download**  
Sends a simple HTTP GET request

**App.Download2**  
Sends an HTTP GET request with parameters.

**App.PostString**  
Sends a POST request with the specified string.

**App.PostBytes**  
Sends a POST request with the specified data.

**App.PutString**  
Sends a PUT request with the specified string.

**App.PutBytes**  
Sends a PUT request with the specified data.

**App.PatchString**  
Sends a PATCH request with the specified string as a request payload.

**App.PatchBytes**  
Sends a PATCH request with the specified data as a request payload.

**App.Head**  
Sends a HEAD request.

**App.PostMultipart**  
Sends a multi-part POST request.

**App.PostFile**  
Sends a POST request with the specified file.

**App.Header**  
Sets the header for the request as map.

**App.ContentType**  
Sets the MIME header of the request.
This method should only be used for requests with a payload.



## Generate Frame
Of course your app should also show something on the matrix. This is done in the sub **App_genFrame**
This is called in the set tick interval. Since this happens every 65ms by default, avoid calculation-intensive tasks or tasks that are constantly repeated. You can use the sub **App_Started** which is called only once when the app is started. Of course this default is very general and has to be tried out or changed depending on the application.

AWTRIX expects one or more character commands with each tick. These are collected per tick, then displayed and deleted from memory.

### Possible drawing commands

**drawBMP**  
Draws a bitmap. RGB535 values can be passed in a short array, or downloaded icons can be retrieved with ``App.getIcon(6)``

**drawText**  
Draws a text.

**drawCircle**  
Draw a circle.

**fillCircle**  
Draws a filled circle

**drawPixel**  
Draws a single pixel

**drawRect**  
Draws a rectangle

**drawLine**  
Draws a line

**fill**  
Fills the matrix with a color

## Compile & test app

The app is complicated as a library. To do this, click **Project**->**Compile in library** in the upper menu bar. Alternatively you can do this with the shortcut **Alt+F5**.

The compiled .jar can now be copied into the **Apps** folder. This folder is located in the root of the AWTRIX installation. 

The apps can be loaded at runtime. The terminal on the home page of the Awtrix web interface can be used for this purpose. If this does not work, AWTRIX must be restarted.

``` bash
reload apps
```