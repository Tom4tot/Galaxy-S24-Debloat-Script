# Galaxy S24 Debloat Script - ADB - list of commands

### Introduction and general information
- Made for: Samsung Galaxy S24 SM-S921B-DS (Exynos, 256GB) - Android 14 - One UI 6.1 - Build UPIA.231005.007.S921BXXUIAWM9 - Baseband S921BXXUIAWM9
- Commands are designed for Windows 11 with CMD.
- No root needed, only access to a computer to apply the ADB commands.
- This won't affect your warranty, Knox, etc.
- Last update: 2024-02-07

### Warning
Of course, you might lose some apps/features that you actually want to use, so before running the commands I provide as an example, make sure you won't miss anything.

### Purpose
- Coming from a Pixel 6 running Graphene OS, I just can't stand Google, Samsung and my internet provider bloat. I don't like relying on premade / universal / GUI scripts that I don't have control with, therefore I made some very simple ADB commands to clean up my phone. In case you need to factory reset or if apps come back after an update, it's much faster to apply rather than manually uninstalling/disabling apps.  
  - For system apps, I disable them instead of uninstalling them. Usually, this strategy sticks better. Also, you should know, that without root, you can't actually totally uninstall system apps. You can only uninstall them for a user, so they still exist in the system. That's why it's easy to recover them with other utilities.
- Bonus tip: use ADB for very large transfers: with a USB 3 cable, I moved my entired music library with an average speed of 200MB/s. It'd be impossible to reach with MTP.
 
## List of ADB commands to debloat
- `adb uninstall` uninstall user app
- `adb shell pm disable-user --user 0` disable system app
- `adb shell cmd package list packages` list of all packages, including system and user apps
- `adb shell cmd package list packages -3` list of all user apps
- Alternatively, you can find package names as well as their label very easily with this great app: https://github.com/SmartPack/PackageManager
- Other commands: https://gist.github.com/davidnunez/1404789?permalink_comment_id=3184514#gistcomment-3184514

## Other useful ADB commands
- `adb install` install app. If it's not in the same location as the adb.exe file, write the file's full path
- `for %f in ("[FOLDER'S PATH]\*.apk") do adb install "%f"` install all apks stored in a folder
- `adb push [source] [destination]` copy files from your computer to your phone. Works for folders too.
- Example: `adb pull /sdcard/download/test.pdf C:\Users\Tom\Downloads`
- `adb pull [device file location] [local file location]` Copy files from phone to computer.
- Example: `adb push C:\Users\Tom\Downloads\1-Music\4-Phone /sdcard/music`

## List of user apps installed
### Samsung Apps
- `com.samsung.SMT.lang_en_us_l03`
- `com.samsung.SMT.lang_fr_fr_l01`
- `com.samsung.android.app.find`
- `com.samsung.android.app.notes`
- `com.samsung.android.app.reminder`
- `com.samsung.android.app.spage`
- `com.samsung.android.app.tips`
- `com.samsung.android.app.watchmanager`
- `com.samsung.android.arzone`
- `com.samsung.android.bixby.ondevice.enus`
- `com.samsung.android.bixby.ondevice.frfr`
- `com.samsung.android.calendar`
- `com.samsung.android.game.gamehome`
- `com.samsung.android.nmt.apps.t2t.languagepack.enfr`
- `com.samsung.android.oneconnect`
- `com.samsung.android.spay`
- `com.samsung.android.tvplus`
- `com.samsung.android.voc`
- `com.samsung.sree`
- `com.sec.android.app.clockpackage`
- `com.sec.android.app.kidshome`
- `com.sec.android.app.popupcalculator`
- `com.sec.android.app.sbrowser`
- `com.sec.android.app.shealth`
- `com.sec.android.app.voicenote`
### Google apps
- `com.google.android.apps.docs`
- `com.google.android.apps.photos`
- `com.google.android.apps.youtube.music`
- `com.google.android.videos`

### Advertisement 
- `com.amazon.appmanager`
- `com.amazon.mShop.android.shopping`
- `com.booking`
- `com.booking.aidprovider`
- `com.facebook.katana`
- `com.microsoft.office.officehubrow`
- `com.microsoft.office.outlook`
### Network Provider (Orange, in my case)
- `com.orange.appshop`
- `com.orange.mail.fr`
- `com.orange.orangeetmoi`
- `com.orange.owtv`
- `com.orange.phone`
- `com.orange.securite`
  
## List of system apps safe to disable
### Samsung
- `com.aura.oobe.samsung` this is the app allowing your carrier to install apps for you...
- `com.samsung.android.messaging` Samsung Messages
- `com.samsung.android.smartswitchassistant` Samsung Smart Switch
- `com.samsung.android.samsungpass` Samsung Pass
- `com.samsung.android.game.gametools` Game Booster
- `com.samsung.android.game.gos` Game Optimizing Service
- `com.samsung.cmfa.AuthTouch` CMFA AuthTouchService: Samsung password manager
### Google
- `com.android.chrome` Chrome
- `com.google.android.apps.googleassistant` Assistant
- `com.google.android.apps.tachyon` Google Meet
- `com.google.android.googlequicksearchbox` Google App
- `com.google.android.gm` Gmail
- `com.google.android.gms.supervision`
- `com.google.android.youtube` YouTube
### Advertisements
- `com.facebook.services`
- `com.facebook.appmanager`
- `com.microsoft.skydrive` Microsoft OneDrive
### Orange
- `com.orange.update` App Center

## Example of mass / bulk debloating
### User apps - Samsung+Google+Advertisement
- `adb uninstall com.microsoft.office.outlook && adb uninstall com.samsung.android.bixby.ondevice.frfr && adb uninstall com.google.android.apps.photos && adb uninstall com.sec.android.app.sbrowser && adb uninstall com.samsung.android.calendar && adb uninstall com.samsung.android.app.reminder && adb uninstall com.google.android.apps.youtube.music && adb uninstall com.sec.android.app.shealth && adb uninstall com.samsung.android.nmt.apps.t2t.languagepack.enfr && adb uninstall com.sec.android.app.popupcalculator && adb uninstall com.booking.aidprovider && adb uninstall com.samsung.SMT.lang_en_us_l03 && adb uninstall && om.samsung.android.bixby.ondevice.enus && adb uninstall com.google.android.apps.docs && adb uninstall com.samsung.android.arzone && adb uninstall com.samsung.android.voc && adb uninstall com.samsung.android.app.tips && adb uninstall com.sec.android.app.clockpackage && adb uninstall com.samsung.android.app.find && adb uninstall com.samsung.android.app.notes && adb uninstall com.amazon.appmanager && adb uninstall com.google.android.videos && adb uninstall com.sec.android.app.voicenote && adb uninstall com.amazon.mShop.android.shopping && adb uninstall com.facebook.katana && adb uninstall com.samsung.sree && adb uninstall com.samsung.android.app.spage && adb uninstall com.samsung.android.oneconnect && adb uninstall com.samsung.android.game.gamehome && adb uninstall com.samsung.SMT.lang_fr_fr_l01 && adb uninstall com.microsoft.office.officehubrow && adb uninstall com.samsung.android.spay && adb uninstall com.samsung.android.app.watchmanager && adb uninstall com.samsung.android.tvplus && adb uninstall com.sec.android.app.kidshome && adb uninstall com.booking`
### User apps - Orange
- `adb uninstall com.orange.appshop && adb uninstall com.orange.orangeetmoi && adb uninstall com.orange.phone && adb uninstall com.orange.securite && adb uninstall com.orange.owtv && adb uninstall com.orange.mail.fr`
### System apps - Samsung+Google+Advertisement
- `adb shell pm disable-user --user 0 com.orange.update && adb shell pm disable-user --user 0 com.microsoft.skydrive && adb shell pm disable-user --user 0 com.google.android.youtube && adb shell pm disable-user --user 0 com.google.android.googlequicksearchbox && adb shell pm disable-user --user 0 com.google.android.gm && adb shell pm disable-user --user 0 com.google.android.apps.tachyon && adb shell pm disable-user --user 0 com.google.android.apps.googleassistant && adb shell pm disable-user --user 0 com.facebook.system && adb shell pm disable-user --user 0 com.facebook.services && adb shell pm disable-user --user 0 com.facebook.appmanager && adb shell pm disable-user --user 0 com.android.chrome && adb shell pm disable-user --user 0 com.samsung.android.smartswitchassistant && adb shell pm disable-user --user 0 com.samsung.android.samsungpass && adb shell pm disable-user --user 0 com.samsung.android.game.gametools && adb shell pm disable-user --user 0 com.samsung.android.game.gos && adb shell pm disable-user --user 0 com.samsung.android.messaging && com.samsung.cmfa.AuthTouch && adb shell pm disable-user --user 0 com.google.android.gms.supervision`
### System apps - Orange
- `adb shell pm disable-user --user 0 com.orange.update`

