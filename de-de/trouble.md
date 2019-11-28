## **Troubleshooting**

### Firmware
If you have trouble to compile the Firmware, try updateing platformio via the terminal  
```platformio update```   

or with the menu:

![image alt text](assets/plattformio_update.jpg)  
  
  

### Matrix
If your Matrix shows weird Pixel and you cant read it, you have to set the Matrixmode 2 and flash the Firmware again. 
- just uncomment (remove the first two //) 
```//#define MATRIX_MODEV2```

### Jittering display
 
AWTRIX sends the frames to the ESP with an average of 15 FPS (this depends on the current App).
If the Wifi Router does not pass the frames to the ESP in real time, the display jerks. There is no Framebuffer in the ESP firmware.
It is important to keep the network connection as short as possible. If possible, connect the server via network cable and avoid using Wifi repeaters or Powerlan adpater. These can delay the communication.
If you cannot solve this Problem, try to connect the Matrix via USB.
