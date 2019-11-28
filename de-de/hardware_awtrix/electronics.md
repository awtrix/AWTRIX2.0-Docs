# **Elektronik**

Die Elektronik kann entweder auf eine Lochrasterplatine gelötet, "frei verdrahtet" sein oder die fertige Platine [aus meinem Shop](https://blueforcer.de/shop/)

Das direkte Löten an die Matrix kann fatale Folgen haben, da die flexible Leiterplatte und insbesondere die LEDs sehr hitzeempfindlich sind. Lassen Sie das Kabel am Eingang (DI,5V,GND) und trennen Sie nur den Stecker. Wenn deine Matrix einen Ausgang (DO) hat, kannst du sie komplett entfernen. Bevor die DC-Buchse für die Stromversorgung angelötet wird, schrauben Sie ihn mit 2 gelöteten Drähten an das Gehäuse.

## Basis Setup

**_Basis Setup:_**
![Basissetup](assets/AWTRIX_Core_Steckplatine.jpg)

## Optionale Helligkeitsregelung per LDR

**_Optionale Helligkeitsregelung per LDR:_**  
![ldr](assets/AWTRIX_LDR_Steckplatine.jpg)

## Optionaler DFPlayer Mini als Soundausgabe

**_Optionaler DFPlayer Mini als Soundausgabe:_**  
![image alt text](assets/AWTRIX_DFMini_Steckplatine.jpg)

| Wemos | DFPlayer Mini | Function |
| ----- | ------------- | -------- |
| 5V    | VCC           | Power    |
| G     | GND           | Ground   |
| D7    | TX            | Transmit |
| D8    | RX            | Receive  |

## Serielle Verbindung zur Matrix

**_Alternative of CORE Setup:_**  
Wenn Sie Probleme haben, mit der WifiConnection stottern, oder einfach nur kein Wifi vom Server zur Matrix verwenden wollen, können Sie die serielle Verbindung nutzen, um die Daten an die Matrix zu übertragen.

Zuerst müssen Sie die serielle Kommunikation in der AWTRIXController Firmware durch uncomment aktivieren //#define USB_CONNECTION

Es kann auch der **USB-Port** des Pi verwendet werden (auch für jede andere Serverplattform). Dazu muss man einfach den Server per microUSB-Kabel an den Wemos D1 anschließen.

Sie können auch die **GPIO's** verwenden, um den Pi mit den Wemos zu verbinden:

![image alt text](assets/AWTRIX_raspi_V2_Steckplatine.jpg)

| Wemos | Raspberry Pin-No | Function |
| ----- | ---------------- | -------- |
| 5V    | 04 - 5V          | 5V Power |
| GND   | 06 - GND         | Ground   |
| RX    | 08 - TXD         | Transmit |
| TX    | 10 - RXD         | Receive  |

Standartmäßig muss beim Raspberry die serielle Schnittstelle freigeschaltet werden, dazu folgende Zeile in der /boot/config.txt eingetragen werden  
`enable_uart=1`
