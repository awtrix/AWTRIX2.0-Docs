AWTRIX offers a wide range of commands for external control.

### MQTT
For MQTT you can connect AWTRIX to an existing MQTT broker.
The default base topic (prefix) is **awtrix**.

### HTTP
For the HTTP API, the base endpoint is  
**http://[AWTRIX-SERVER_IP]:7000/api/v3**  

e.g. for a simple test under Linux curl can be used to make an http request:  
``` BASH
curl -X POST --header 'Content-Type: application/json' -d '{"force":true, "text": "Awesome", "icon":1, "color":[0,255,255], "count":2}' 'http://[HOST_IP]:7000/api/v3/notify'
```



## Basic Controls

> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/basics  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/basics


___

### power
Switches AWTRIX on (true) or off (false).

``` JSON
{"power": true}
```
___

### switchTo

Switch to a defined app


``` JSON
{"switchTo": "Facebook"}
```
___

### Appstate

Disables or enables an app


``` JSON
{"disable": "Facebook"}
{"enable": "Facebook"}
```
___

### Apploop

Controls the apploop

#### **Parameters**  
- app
  - "next" : next app
  - "back" : previous app
  - "pause" : pause apploop (toggle)
  - "hold" : hold the current app without switching (toggle)

``` JSON
{"app": "next"}
```
___

### showAnimation

Displays an animation that is downloaded from the AWTRIX cloud.
Expects an animation name (see [cloudAnimations](api?id=receive basic information)).
"random" plays a random animation.

``` JSON
{"showAnimation": "tetris"}
{"showAnimation": "random"}
```
___

### soundfile

Plays an audio file loaded on the DF player's SD card.

You need to create a folder "MP3" on your DFplayer SD card and move your mp3s into this folder.
The mp3 must start with a 4-digit number, e.g. 0001.mp3 or 0001 - Testfile.mp3  
AWTRIX uses the range 0001-0100 for internal purposes. Start with own mp3s at 0101.  
[Download default sounds](https://blueforcer.de/awtrix/Soundpack.zip)

#### **Parameters**
- soundfile: Number of the desired MP3

``` JSON
{"soundfile": 101}
```

___

### timer

Starts a timer for the specified period of time and displays an alarm when the time is up.

#### **Parameters**
- timer: time span in ``"hours:minutes:seconds"``
- color: array of integers [R,G,B] (optional)
- count: How often should the timer flash? (optional)
- soundfile: Plays an MP3 when the timer expires (optional)
- text: Text that is displayed (static, up to 8 characters) (optional)

``` JSON
{"timer": "00:00:10", "soundfile":1, "color":[255,0,0], "count":10, "text": "AWTRIX"}
```

``` JSON
{"timer": "stop"} // clears the timer again
```
___
### stopwatch

Starts a stopwatch with predefined icon. AWTRIX is blocked during execution.
When the stopwatch reaches 1 hour, the icon is removed for more space.

#### **Parameters**
- stopwatch: Start/stop the stopwatch
- icon: IconID

``` JSON
{"stopwatch":true, "icon":423}
```
``` JSON
{"stopwatch":false} // Stops the timer
```
___
### yeelight
With this premium function you can play an effect on a Yeelight.  
The first string in the array names the effect, the second parameter specifies how often this effect is repeated. You can also implement this in your notification JSON.

``` JSON
{"yeelight":["Alarm",10]}
```
The following effects are currently available
- Alarm
- Birthday
- Candle Flicker
- Christmas
- Disco
- LSD
- Pastel Flow
- Policy
- policy2
- Rainbow
- Rave
- RGB
- Romance
- Strobe
- Sunrise
- traffic light

> **Please note**  
You cannot play an effect while the Yeelight is switched off (from app etc, not disconnected from the power). Therefore awtrix asks for the powerstate of the lamp and turns it on if necessary. After playback the lamp will switched off again. If the light is switched on before the api call, the bulb will return to the state before the effect started.
But this causes a problem: If the Yeelight is off and an effect is played, the Yeelight has the state "ON". If you now activate an effect again while the light bulb is still playing an effect, the Yeelight will remain on afterwards, because "ON" was the last requested state.
___

### appList

With this API you can change the order of the apps (AppLoop).

#### **Parameters**
- appList: a list of user-defined apploop (array of string)
- icon: iconID

``` JSON
{"appList":["Time", "Facebook", "Time", "Instagram"]}
```

``` JSON
{"appList": "reset"} //s resets the apploop
```
___

## Get basic information
> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/basics  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/basics
> MQTT answers on the topic "[prefix]/response"

#### **Parameters**
- get

#### Possible information
- **cloudAnimations**
  - returns all available cloud animations
- **installedApps**
  - returns all installed apps
- **appList**  
  - returns the complete App-Loop
- **settings**     
  - returns all settings
- **version**       
  - returns the AWTRIX version
- **uptime**         
  - returns the operating time of AWTRIX
- **powerState**
  - indicates whether AWTRIX is true or false and returns
- **log**
  - returns the log
- **matrixInfo**     
  - returns all information of the connected matrix.

``` JSON
{"get": "installedApps"}
```


___


## Change settings

All settings can be changed here
The appropriate keys of the settings can be found in the file "Settings" in the order "config".
Furthermore the settings can be read out in the same format [see here](http://localhost:3000/#/en-en/api?id=get-basic-information)
> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/settings  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/settings
___

Making one or more settings

``` JSON
{"Brightness":100}
```

___


## Notifications

> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/notify  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/notify


Displays an individual notification

#### **Parameters**  
- **text**
  - Text to be displayed (String)
- **multiColorText**
  - Define an Array of textareas with a given RGB color values (Array of Integer) .e.g: ```"multiColorText":[{"text":"Totally ","color":[0,255,0]},{"text":"Awesome","color":[255,0,0]}]```
- **fallingText**
  - Another way to display long text. Instead of scrolling from right to left, each word falls from top to bottom. If a dot or comma is detected, the diplay will pause for 1000 or 500 milliseconds for better experience. Icons are disabled.
- **force (optional)**
  - Determines whether the specified notification should be displayed immediately or after the current app (true/false).
  If set to false, the notification is sorted into a queue. After the current app, AWTRIX displays all notifications one after the other and then deletes them. This allows several notifications to be sent at once. If there are no further notifications in the queue, AWTRIX will display native apps again.
- **name (optional)**
  - Identification of the notification
- **scrollSpeed (optional)**
  - The scroll speed in milliseconds. Lower=Faster; default: 65ms (integer) 
  - Controls the displaytime in milliseconds of each word with fallingText. default: 400
- **icon (optional)**
  - Icon ID from the online database (integer)
  - You can also show up to 4 Icons in your notification. Text is disabled with this function
(jsonkeys: "icon","icon2","icon3","icon4")
- **color (optional)**
  - Custom text color (array of integers [R,G,B])
- **moveIcon (optional)**
  - Moves the icon with the text from the screen (true/false).
- **repeatIcon (optional)** 
  - If **moveIcon** is active, when using **repeat** the icon will be displayed again on subsequent repetitions.
- **duration (optional)**
  - Defines how long (in seconds) the notification should be displayed (integer) (Overridden by **repeat**)
- **repeat (optional)**
  - How often the text should be scrolled before switching to the next app. If the text needs to be scrolled up and the text length does not need to be scrolled up, the global app runtime is used to switch. (integer)
- **rainbow (optional)**
  - Displays the text in rainbow colors. Overwrites **color** (true/false).
  - While using fallingText each word will be displayed in a random color
- **progress (optional)**
  - Displays a progress bar below the text (0-100, integer)
- **progressColor (optional)**
  - Determines the color of the progress bar (array of integers [R,G,B]) 
- **progressBackground (optional)**
  - Determines the background color of the progress bar (array of integers [R,G,B])   
- **soundfile (optional)**
  - Plays a specific file on the DFPlayer when the app starts. (Number of the desired MP3 as integer)
- **yeelight**
  - Plays an effect on your Yeelight ([see here](/en-en/api?id=yeelight))
- **barchart**
  - displays a barchart at the matrix : Send your data values as an Array e.g ```"barchart":[20,50,80,100,50,20,60]```
- **linechart**
  - Like barcharts you can also send linecharts send your data values as an Array e.g ```"linechart":[20,50,80,100,50,20,60]```


```JSON
{
   "name": "Test Notification"
   "force":true,
   "icon":6,
   "moveIcon":true,
   "repeat":2,
   "soundfile":1,
   "text": "Totally Awesome"
   "color":[
      0,
      255,
      0
   ]
}

```

A notification can be removed from the queue
```JSON
{"remove": "TestNotification"}
```

___


## Temporary App

> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/temporaryapp  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/temporaryapp


With this API you can create a temporary app that integrates with the AppLoop with a certain **"Loop Lifetime "**.
This app is displayed at the end of each AppLoop and the lifetime decreases by 1 with each call. When the lifetime decreases to 0, the temporary app is removed from the AppLoop.
You can update the temporary app at any time by resending the request with the same name.
The structure and possible commands are the same as for a notification, except that the parameters **name** and **lifetime** are mandatory.

```JSON
{
   "name": "TestApp."
   "lifetime":5,
   "icon":6,
   "text": "Totally Awesome"
   "color":[
      60,
      255,
      0
   ]
}

```

A temporary app can be removed
```JSON
{"remove": "TestApp"}
```

___

## Drawing

> [!TIP|style:flat|label:HTTP Endpoint|iconVisibility:hidden]
> /api/v3/draw  

> [!TIP|style:flat|label:MQTT Topic|iconVisibility:hidden]
> awtrix/draw
___

You can send various drawing commands to AWTRIX to create a custom screen. To do this, you can define several commands in a JSON-string, which AWTRIX then processes one after the other. This makes smaller animations possible.
All methods are static, automatic scrolling of the text is not possible.
The drawing mode starts with the first command.

Each command only fills the frame buffer. You have to execute **show** to finally display the data on the matrix.


The following example is structured as follows:
 - Fill the entire screen with a gray background.
 - Write "Hello".
 - Displays the last two commands on the matrix.
 - Wait 3 seconds before the next command.
 - Draw a circle next to the text.
 - And display it
 - Wait another 3 seconds
 - Delete the entire content
 - Draw a line from the upper left corner to the lower right corner.
 - Display the line on the matrix.
 - Wait 3 seconds
 - Repeat everything twice
 - Exiting the drawing mode

!> **Please note:** You have to call **exit** to leave the drawing mode and return to the normal state. If you set repetition, the exit command will be ignored and automatically exit the drawing mode when all repetitions are complete.  

``` JSON
{
  "repeat":2,
  "draw": [
    {
      "type": "fill",
      "color." [100,100,100]
    },
    {
      "type": "text",
      "string": "Hello",
      "position": [0,0],
      "color." [255,0,0]
    },
    {
      "type": "show"
    },
    {
      "type": "wait",
      "ms": 3000
    },
    {
      "type": "circle",
      "radius": 3,
      "position": [24,3],
      "color." [255,0,255]
    },
    {
      "type": "show"
    },
    {
      "type": "wait",
      "ms": 3000
    },
    {
      "type": "clear"
    },
    {
      "type": "line",
      "start." [0,0],
      "end." [31,7],
      "color." [255,255,255]
    },
    {
      "type": "show"
    },
    {
      "type": "wait",
      "ms": 3000
    },
    {
      "type": "exit"
    }
  ]
}
```



 #### **Possible commands**

?> The first pixel (upper left corner) has the coordinate [0,0], while the last (lower right corner) has [31,7].  

**<span style="color:blue">loop</span>** How often the drawing routines should be repeated (optional)

- **<span style="color:blue">text</span>** Draws a text.
  - string
  - position
    - Array of integers [X,Y]
  - color
    - Array of integers [R,G,B]
- **<span style="color:blue">rect</span>** Draws a rectangle
  - position
    - Array of integers [X,Y]
  - size
    - Array of Integers [Width,Height]
  - color
    - Array of integers [R,G,B]
- **<span style="color:blue">line</span>** Draws a line
  - start
    - Array of integers [X0,Y0]
  - end
    - Array of integers [X1,Y1]
  - color
    - Array of integers [R,G,B]
- **<span style="color:blue">circle</span>** Draws a circle.
  - position
    - Array of integers [X,Y]
  - radius
    - integer r
  - color
    - Array of integers [R,G,B]
- **<span style="color:blue">pixel</span>** Draws a single pixel.
  - position
    - Array of integers [X,Y]
  - color
    - Array of integers [R,G,B]
- **<span style="color:blue">bmp</span>** Draws a bitmap
  - position
    - Array of integers [X,Y]
  - size
    - Array of Integers [Width,Height]
  - data
    - Array of RGB565 integers [p0,p1,p2,p3,...]
- **<span style="color:blue">fill</span>** Fills the whole matrix with one color.
  - color
    - Array of integers [R,G,B]
- **<span style="color:blue">wait</span>** Wait X milliseconds before the next command
  - ms
    - Integer ms
- **<span style="color:blue">show</span>** Displays all previous commands.
- **<span style="color:blue">clear</span>** Clears the contents of the matrix.
- **<span style="color:blue">exit</span>** Exit drawing mode and return to normal.
