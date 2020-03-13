With the AWTRIX Cloud, you can send API commands to your AWTRIX from outside.  
  
The goal of the AWTRIX Cloud is to close the gap between your local instance and the services on the Internet, while ensuring the highest level of security and data protection. I have developed the AWTRIX Cloud with security in mind. No further configuration is required to make the instance accessible to the Internet. Furthermore, no user names, passwords, e-mail addresses or other private information are required and the cloud server does not store any information about the connections.  
  
The cloud connection is part of the premium functionality.  
  
## How it works

When you enable the cloud functionality, AWTRIX connects to the cloud server (the server is completely self-written, I don't use third party cloud software). After successful connection, AWTRIX generates its own 12-digit token and sends it to the server for login. This connection is then assigned to the token. It is not possible to access other connections, as each one is instantiated as a separate thread.

A post-request to the AWTRIX cloud with its own token forwards the message to the linked connection. If the token is not found, the request runs into empty and is not processed.

You can regenerate the token at any time. 


## Using IFTTT with the AWTRIX Cloud

Some examples of what you can do with IFTTT and AWTRIX Cloud

- Display of the current title played with Spotify
- View any notification from your smartphone
- Display of incoming or missed calls
- Turn off AWTRIX when you leave the house
- Please note that IFTTT does not have as many services for iOS as for Android. But of course many IFTTT services can be used without a smartphone.


Any API command described in the documentation can be sent to the cloud and will be forwarded to your AWTRIX in a secure way.

This example shows how to set up your first IFTTT applet to display new email from Gmail.

**Prepare AWTRIX to use the cloud**

Enable cloud connectivity in the premium area in the system settings.
After saving, the 32-digit Cloud token is generated. Keep this token safe! Anyone with this token could control your AWTRIX.

   1. create an account at https://ifttt.com/join
   2. go to "My Applets" and click on "New Applet
   3. click on the blue "+THIS" and search for "Gmail" as service.
   4. then choose "Any new email in inbox" as trigger
   5. click on the blue "+THAT", search for "Webhooks" as action and choose "Make a web request".
   6. now you have to "build" your URL:
    https://awtrix.blueforcer.de/cloud?mode=notify&token=xxxx
    Where "mode" represents the desired API endpoint (basics, notify or draw). Also replace the xxxx with your 32-digit Cloud Token
   7. select **POST** as method
   8. select **application/json** as content type
   9. use the Notification API for the body
    {"force":true, "icon":36, "text": "New mail from {{{{{FromName}}}", "color":[255,255,255]}
    You can change the input coming from IFTTT by clicking on "Add ingredient" and rebuild the text as you wish.
   10. click on "Create action" and then click on "Finish".

Now, every time a new email arrives in the Gmail inbox, AWTRIX will display it on the matrix.

![AWTRIX Pro](..\assets\ifttt.png)