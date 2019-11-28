#### DEV 195022119 - Januar 22, 2019
- remove automatic restart
- added automatic brightness control (needs LDR and latest controllerFW)
___

#### DEV 1455050119 - Januar 5, 2019
- Add status from AWTRIXController  
- AWTRIX Controller 0.3
  - WiFi Manager removed
  - add LDR support
  - add OTA support
___

#### DEV 1406040119 - Januar 4, 2019
- Memoryleak fixed
___
#### DEV 22301119 - Januar 1, 2019
- Add Changelogs
- Add setupinfos to apps
- Add number of available Apps in Appstore
- Add number of installed Apps in MyApps
___
#### DEV 1527311218 - December 31, 2018
- The app structure has changed
- True/False settings have been replaced by togglebuttons
- Until there is a fix to the MemoryLeak, Awtrix restarts every 24h to clear the memory again.
- New appchanging Animation
- Fixed a bug where the list was not rebuilt after an app was setup.
- Weblogger is active again
- The appstore now shows if an app already exists or an AppUpdate is available.
- settings are no longer written to a database but to a text file. This saves 6MB of libs and is easier to handle.
___