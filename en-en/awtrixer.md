with AWTRIXER you can create 8x8 icons (static or animated) and 32x8 animations
AWTRIXER is based on [Piskel](https://www.piskelapp.com/) and works directly with the AWTRIX backend.
AWTRIXER contains a lot of functions that almost remind of Photoshop.

!> Piskel and therefore AWTRIXER are not optimized for mobile devices!

  <div align=center>
  <img width="1000" src="..\assets\creator.gif"/>
  </div>

  - On the left side you will find all the tools you need to draw. Move the mouse over the symbols to get more information.
  - Please note that transparent colors are not used in the saved icon.
  - You can create an animation by adding several frames. You can create a new frame or duplicate an existing one.
  - On the right side you will find the icon preview and the slider to change the speed of the animation.
  - The **Live View** section allows you to see your work live on your AWTRIX. Use this before you upload an icon, because on the matrix it usually looks slightly different than on your monitor.
  - Use the menu items on the far right to access the general features of AWTRIXER
    - Resize lets you change your canvas from 8x8 to 32x8 Other sizes are not possible here.
    - With Save you can rename your work, save it for later sessions or upload it to the cloud.
    - Export, exports your icon as an image file to the PC. However, these cannot be used by AWTRIX.
    - With Import, you can import existing graphics or animations. Please note that AWTRIX can only work in 8x8 or 32x8. If necessary, use the resize function during the import process.
  
  
  
**You have a also a saving option to save icons locally for private usage**  
To use it, just write the iconname as ID (String instead of Integer) in your API request
All Icons will be saved in a readable textfile (config->privatIcons), so you can edit/add/remove icons manually.
AWTRIX does not recognize any change to that file. To reload your private Icons, simply execute reload icons from the terminal on the mainpage. While saving your Icons via AWTRIXER it will reload automatically.
Like the community Icons youre not able to reload your Icons in AWTRIXER for editing. Use "Save as .awtrixer file" to backup your icon.
Your private Icons will not be shown in the Icondatabase.
Despite this feature it is of course still nice to share common icons with the community.