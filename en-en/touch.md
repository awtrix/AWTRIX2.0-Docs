# Touchbuttons

If you connected the three touchbuttons to your AWTRIX, you have some nice features to control your AWTRIX.

- While in normal operation, you can switch between apps with left or right button.
- Some apps can be controlled by pressing the middle button. e.g **Toggl**
- If you hold the middle button you will enter a small menu. Here you have several options:
    - **SLEEP** You can put your AWTRIX into standby (Matrix will switch off) 
    - **BRIGHT** Change the brightness
    - **VOLUME** Change the volume
    - **MQTT** Control your smarthome via MQTT
- You can exit the menu by holding the middle button.

### Send MQTT commands via the MQTT menu:
- create a mqtt.json inside the config folder e.g
  ```json
   [
    {
        "name": "Light1 On",
        "topic": "schlafzimmer/licht/cmd",
        "payload": "on"
    },
    {
        "name": "Washingmachine Off",
        "topic": "keller/Washingmachine/cmd",
        "payload": "off"
    }
]   
  ```
- You can add as many options as you like.
- You dont need to restart awtrix if you made changes to the json, just reload the menu.
- Choose your option from your mqtt.json by name via left or right button, and acitvate it (short middle push). AWTRIX will send the payload to the given topic.
- You can exit the menu by holding the middle button.