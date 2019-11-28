## AXTRIXER  

With AWTRIXER you can create Icons (8x8), images (1x8-8x32) and animations (8x8).
You can also stream it to the matrix and upload it to the AWTRIX cloud. 
[Download here](https://blueforcer.de/download/)

![image alt text](assets/awtrixer.png)


## Creator
#### Livedrawing: 
To use the livedrawing functionality you have to specify the Awtrix_IP and select live drawing by the tick box. 
The entered IP is saved persistently so that the IP is preconfigured for further use.

The working area of the AWTRIXER is the matrix in the desired dimensions. Here you can draw via color selection, fill and clear.

#### Import images
**File --> Import** 
Here you can import an image in *.jpg, *.jpeg, *.bmp or *.png format.
Please note that the image will be resized to the set size of the matrix.

#### Draw
- Left mouse click paints the pixel in the selected color.
- Middle mouse click copies the color of the pixel.
- Right mouse click deletes the pixel.

#### Color selection
Here you can choose between 120 predefined colors.  

**Custom color:**  
Here you can select a custom color in the HSB/RGB or Web color space.  
- Use: Uses the selected color directly for drawing in the matrix.
- Save: Saves the selected color in the color selection under Custom Color until you close the AWTRIXER.

#### Upload
The drawn icon (only 8x8) can be uploaded to the AWTRIX server after entering the captcha. 
   
!> **Attention:** With the upload the creator gives away any rights to the created icon. 
You cannot edit or delete the icon after upload. The icons are visible to everyone. I reserve the right to delete icons uploaded with AWTRIXER from the server without prior consultation. This includes double icons, any unconstitutional symbols, sexist or in any way offensive or insulting graphics and useless icons such as a completely white one. Likewise I will delete icons whose names are not meaningful.

### Animations
<img align="right" width="192" height="621" src="v2/assets/animation.png">

**Animations -> New Animations**
Here you can create animations based on the set dimensions of the matrix and the drawn image. If you want to Upload it you should set a Icon dimension of 8x8.

- **Import:** Imports a series of images in *.jpg, *.jpeg, *.bmp or *.png format and generates an animation from them.  
- **Add:** Adds the current frame to the animation.
- **Duplicate:** duplicates the selected frame and inserts it after the selected frame.
- **Update:** Updates the selected frame with the contents on the matrix.
- **Delete:** Deletes the selected frame.

- **Export for Drawing API:** Exports the animation (with the current settings) for further use via MQTT/Rest API, 
as animation.json in the start directory or as content in the clipboard.
        
- **Speed:** Here you can set the frame rate of the animation between min.60ms and max 2000ms.

- **Play:** Plays the animation. If live drawing is activated also on AWTRIX.


## Database
Here you can find all uploaded Icons/Animations with the corresponding IconID.  
After selecting an icon, it can also be copied to the Creator (except animations).  
If live drawing is activated, the icons of the database can also be displayed directly on the AWTRIX.

## AWTRIXER mobile

AWTRIXER is also [available](https://blueforcer.de/download/) for Android and iOS.  
The mobile version is limited to creating static 8x8 Icons.  
  
![image alt text](assets/ios.png)

