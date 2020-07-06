# Touchbuttons

Wenn du  die drei Touchbuttons an deine AWTRIX angeschlossen hast, hast du einige nette Funktionen um deine AWTRIX direkt zu steuern.

- Während des normalen Betriebs kannst du mit der linken oder rechten Taste zwischen den Apps wechseln.
- Einige Apps können durch Drücken der mittleren Taste gesteuert werden. z.B. **Toggl**
- Wenn du die mittlere Taste gedrückt hälst, gelangst du in ein kleines Menü. Hier hast du folgende Optionen:
    - Du können deine AWTRIX in den Standby-Modus versetzen (Matrix schaltet sich aus) 
    - Ändern der Helligkeit
    - Ändern der Lautstärke
    - MQTT Befehle absetzen um z.b dein Smarthome zu steuern
- Du kannst das Menü verlassen, indem du die mittlere Taste gedrückt hälst.

### MQTT-Befehle über das MQTT-Menü senden:
- Erstelle eine mqtt.json innerhalb des Config Ordners, z.B.
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
- Du kannst so viele Optionen hinzufügen, wie du möchtest.
- Du brauchst AWTRIX nicht neu zu starten wenn du Änderungen an der Json vorgenommen hast, lade einfach das Menü neu.
- Gehe in das MQTT Menü und wähle die Option mit der linken oder rechten Taste aus, die du in der mqtt.json festgelegt hast und aktivieren Sie mit einem kurzen klick auf den mittleren Button. AWTRIX wird die payload an das angegebene Topic senden.
- Du kannst das Menü verlassen, indem du die mittlere Taste gedrückt hälst.
