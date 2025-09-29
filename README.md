# Galaxy S24 Debloating - ADB - list of commands

### Introduction and general information
- Made for: **Samsung Galaxy S24 SM-S921B-DS** (Exynos, 256GB) - **Android 14-15-16** - **One UI 6.1 - 7 - 8**
- **It works exactly the same way on all android versions to date**
- Commands are designed for **Windows 11 with CMD**.
- No root needed, only access to a computer to apply the ADB commands.
- This won't affect your warranty, Knox, etc.
- Last update: 2025-09-29
- Keywoards: debloat debloating bloatware adware spyware disable uninstall

### Warning
Of course, you might lose some apps/features that you actually want to use, so before running the commands I provide as an example, make sure you won't miss anything. Disabling/uninstalling vital system apps may break your system.

### Purpose
- Coming from a Pixel 6 running Graphene OS, I just can't stand Google, Samsung and my internet provider bloat. I don't like relying on premade / universal / GUI scripts that I don't have control with, therefore I made some very simple ADB commands to clean up my phone. In case you need to factory reset or if apps come back after an update, it's much faster to apply rather than manually uninstalling/disabling apps.  
  - For system apps, I disable them instead of uninstalling them. Usually, this strategy sticks better. Also, you should know, that without root, you can't actually totally uninstall system apps. You can only uninstall them for a user, so they still exist in the system. That's why it's easy to recover them with other utilities.
- Debloatig may improve battery life, memory usage, performance (as less apps/services run in the background).
- Unrelated tip that however changed my life: **use ADB for very large file transfers**: with a USB 3 cable, I moved my entired music library with an average speed of 200MB/s. It'd be impossible to reach that with MTP.

## Prerequisites
- [Google USB drivers](https://developer.android.com/studio/run/win-usb) so your phone is properly detected
- [Platform tools](https://developer.android.com/tools/releases/platform-tools#downloads) so you can use ADB commands, open CMD within the folder.

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
- Example: `adb push "C:\Users\Tom\Downloads\1-Music\4-Phone" "/sdcard/music"` Quotation marks are useful in case there are spaces in your paths
- `adb pull [device file location] [local file location]` Copy files from phone to computer.
- Example: `adb pull "/sdcard/download/test.pdf" "C:\Users\Tom\Downloads"`

## List of user apps installed
- Note: you can find easily what are the labels of Samsung apps by adding the package name to the following URL: https://galaxystore.samsung.com/detail/ (e.g. https://galaxystore.samsung.com/detail/com.samsung.android.voc)
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
- `com.aura.oobe.samsung` **this is the app allowing your carrier to install apps for you...**
- `com.samsung.android.app.camera.sticker.facearavatar.preload` AR stuff
- `com.samsung.android.app.omcagent` Samsung Recommended apps
- `com.samsung.android.app.parentalcare` Parental Controls
- `com.samsung.android.appseparation` Separated Apps
- `com.samsung.android.ardrawing` AR stuff
- `com.samsung.android.aremoji` AR stuff
- `com.samsung.android.aremojieditor` AR stuff
- `com.samsung.android.bixby.agent` Bixby Voice
- `com.samsung.android.bixby.wakeup` Bixby wake-up
- `com.samsung.android.bixbyvision.framework` Bixby VisionFramework
- `com.samsung.android.dkey` Samsung Wallet Digital Key
- `com.samsung.android.fmm` Find My Mobile (Samsung)
- `com.samsung.android.game.gametools` Game Booster
- `com.samsung.android.game.gos` Game Optimizing Service
- `com.samsung.android.ipsgeofence` Samsung Visit In
- `com.samsung.android.kidsinstaller` Samsung Kids INstaller
- `com.samsung.android.mdecservice` Call & text on other devices
- `com.samsung.android.mdx` Link to Windows Service
- `com.samsung.android.messaging` Samsung Messages
- `com.samsung.android.rubin.app` Customization Service
- `com.samsung.android.samsungpass` Samsung Pass
- `com.samsung.android.samsungpassautofill` Autofill with Samsung Pass
- `com.samsung.android.smartswitchassistant` Samsung Smart Switch
- `com.samsung.android.spayfw` Samsung Pay Framework
- `com.samsung.storyservice` Gallery stories
- `com.sec.android.app.billing` Samsung Checkout
- `com.sec.android.easyMover.Agent` Smart Switch Agent
- `com.sec.android.easyMover` Samsung Smart Switch
- `com.sec.android.mimage.avatarstickers` AR Emoji Stickers
### Google
- `com.android.apps.tag` Tags
- `com.android.bookmarkprovider` Bookmarks Provider
- `com.android.chrome` Chrome
- `com.android.dreams.basic` ScreenSaver
- `com.android.dreams.phototable` ScreenSaver
- `com.android.hotwordenrollment.okgoogle` Google Assistant
- `com.android.hotwordenrollment.xgoogle` Google Assistant
- `com.android.providers.partnerbookmarks` Bookmarks
- `com.google.android.apps.googleassistant` Assistant
- `com.google.android.apps.tachyon` Google Meet
- `com.google.android.gm` Gmail
- `com.google.android.gms.location.history` Google Location History
- `com.google.android.googlequicksearchbox` Google App
- `com.google.android.health.connect.backuprestore` Google Health
- `com.google.android.healthconnect.controller` Google Health
- `com.google.android.onetimeinitializer` Google One Time Init
- `com.google.android.projection.gearhead` Android Auto
- `com.google.android.setupwizard` Android Setup
- `com.google.android.syncadapters.calendar` Google Calendar Sync
- `com.google.android.youtube` YouTube
- `com.google.ar.core` Google Play Service for AR
- `com.sec.android.app.chromecustomizations` Chrome Customizations (e.g. home button)
- `com.sec.android.daemonapp Android Weather` Wather
- `com.sec.android.mimage.avatarstickers` AR stuff
### Advertisements
- `com.facebook.services` Facebook crap
- `com.facebook.appmanager` Facebook crap
- `com.microsoft.appmanager` Link to Windows
- `com.microsoft.skydrive` Microsoft OneDrive
### Orange
- `com.orange.update` App Center

## Example of mass / bulk debloating
### User apps - Samsung+Google+Advertisement
- `adb uninstall com.microsoft.office.outlook && adb uninstall com.samsung.android.bixby.ondevice.frfr && adb uninstall com.google.android.apps.photos && adb uninstall com.sec.android.app.sbrowser && adb uninstall com.samsung.android.calendar && adb uninstall com.samsung.android.app.reminder && adb uninstall com.google.android.apps.youtube.music && adb uninstall com.sec.android.app.shealth && adb uninstall com.samsung.android.nmt.apps.t2t.languagepack.enfr && adb uninstall com.sec.android.app.popupcalculator && adb uninstall com.booking.aidprovider && adb uninstall com.samsung.SMT.lang_en_us_l03 && adb uninstall && com.samsung.android.bixby.ondevice.enus && adb uninstall com.google.android.apps.docs && adb uninstall com.samsung.android.arzone && adb uninstall com.samsung.android.voc && adb uninstall com.samsung.android.app.tips && adb uninstall com.sec.android.app.clockpackage && adb uninstall com.samsung.android.app.find && adb uninstall com.samsung.android.app.notes && adb uninstall com.amazon.appmanager && adb uninstall com.google.android.videos && adb uninstall com.sec.android.app.voicenote && adb uninstall com.amazon.mShop.android.shopping && adb uninstall com.facebook.katana && adb uninstall com.samsung.sree && adb uninstall com.samsung.android.app.spage && adb uninstall com.samsung.android.oneconnect && adb uninstall com.samsung.android.game.gamehome && adb uninstall com.samsung.SMT.lang_fr_fr_l01 && adb uninstall com.microsoft.office.officehubrow && adb uninstall com.samsung.android.spay && adb uninstall com.samsung.android.app.watchmanager && adb uninstall com.samsung.android.tvplus && adb uninstall com.sec.android.app.kidshome && adb uninstall com.booking`
### User apps - Orange
- `adb uninstall com.orange.appshop && adb uninstall com.orange.orangeetmoi && adb uninstall com.orange.phone && adb uninstall com.orange.securite && adb uninstall com.orange.owtv && adb uninstall com.orange.mail.fr`
### System apps - Samsung+Google+Advertisement
- `adb shell pm disable-user --user 0 com.aura.oobe.samsung && adb shell pm disable-user --user 0 com.samsung.android.app.camera.sticker.facearavatar.preload && adb shell pm disable-user --user 0 com.samsung.android.app.omcagent && adb shell pm disable-user --user 0 com.samsung.android.app.parentalcare && adb shell pm disable-user --user 0 com.samsung.android.appseparation && adb shell pm disable-user --user 0 com.samsung.android.ardrawing && adb shell pm disable-user --user 0 com.samsung.android.aremoji && adb shell pm disable-user --user 0 com.samsung.android.aremojieditor && adb shell pm disable-user --user 0 com.samsung.android.bixby.agent && adb shell pm disable-user --user 0 com.samsung.android.bixby.wakeup && adb shell pm disable-user --user 0 com.samsung.android.bixbyvision.framework && adb shell pm disable-user --user 0 com.samsung.android.dkey && adb shell pm disable-user --user 0 com.samsung.android.fmm && adb shell pm disable-user --user 0 com.samsung.android.game.gametools && adb shell pm disable-user --user 0 com.samsung.android.game.gos && adb shell pm disable-user --user 0 com.samsung.android.ipsgeofence && adb shell pm disable-user --user 0 com.samsung.android.kidsinstaller && adb shell pm disable-user --user 0 com.samsung.android.mdecservice && adb shell pm disable-user --user 0 com.samsung.android.mdx && adb shell pm disable-user --user 0 com.samsung.android.messaging && adb shell pm disable-user --user 0 com.samsung.android.samsungpass && adb shell pm disable-user --user 0 com.samsung.android.samsungpassautofill && adb shell pm disable-user --user 0 com.samsung.android.smartswitchassistant && adb shell pm disable-user --user 0 com.samsung.android.spayfw && adb shell pm disable-user --user 0 com.samsung.android.rubin.app && adb shell pm disable-user --user 0 com.samsung.storyservice && adb shell pm disable-user --user 0 com.sec.android.app.billing && adb shell pm disable-user --user 0 com.sec.android.easyMover.Agent && adb shell pm disable-user --user 0 com.sec.android.easyMover && adb shell pm disable-user --user 0 com.sec.android.mimage.avatarstickers && adb shell pm disable-user --user 0 com.android.apps.tag && adb shell pm disable-user --user 0 com.android.bookmarkprovider && adb shell pm disable-user --user 0 com.android.chrome && adb shell pm disable-user --user 0 com.android.dreams.basic && adb shell pm disable-user --user 0 com.android.dreams.phototable && adb shell pm disable-user --user 0 com.android.hotwordenrollment.okgoogle && adb shell pm disable-user --user 0 com.android.hotwordenrollment.xgoogle && adb shell pm disable-user --user 0 com.android.providers.partnerbookmarks && adb shell pm disable-user --user 0 com.google.android.apps.googleassistant && adb shell pm disable-user --user 0 com.google.android.apps.tachyon && adb shell pm disable-user --user 0 com.google.android.gm && adb shell pm disable-user --user 0 com.google.android.gms.location.history && adb shell pm disable-user --user 0 com.google.android.googlequicksearchbox && adb shell pm disable-user --user 0 com.google.android.health.connect.backuprestore && adb shell pm disable-user --user 0 com.google.android.healthconnect.controller && adb shell pm disable-user --user 0 com.google.android.onetimeinitializer && adb shell pm disable-user --user 0 com.google.android.projection.gearhead && adb shell pm disable-user --user 0 com.google.android.setupwizard && adb shell pm disable-user --user 0 com.google.android.syncadapters.calendar && adb shell pm disable-user --user 0 com.google.android.youtube && adb shell pm disable-user --user 0 com.google.ar.core && adb shell pm disable-user --user 0 com.sec.android.app.chromecustomizations && adb shell pm disable-user --user 0 com.sec.android.daemonapp Android Weather && adb shell pm disable-user --user 0 com.sec.android.mimage.avatarstickers && adb shell pm disable-user --user 0 com.facebook.services && adb shell pm disable-user --user 0 com.facebook.appmanager && adb shell pm disable-user --user 0 com.microsoft.appmanager && adb shell pm disable-user --user 0 com.microsoft.skydrive`
### System apps - Orange
- `adb shell pm disable-user --user 0 com.orange.update`

### New system apps to disable (tested one One UI 8 - MAKE SURE YOU DON'T NEED THEM)
- `adb shell pm disable-user --user 0 com.samsung.android.mapsagent && adb shell pm disable-user --user 0 com.samsung.android.visionintelligence && adb shell pm disable-user --user 0 com.samsung.android.carkey && adb shell pm disable-user --user 0 com.samsung.android.app.sketchbook && adb shell pm disable-user --user 0 com.google.android.apps.bard && adb shell pm disable-user --user 0 com.samsung.android.app.interpreter && adb shell pm disable-user --user 0 com.google.audio.hearing.visualization.accessibility.scribe && adb shell pm disable-user --user 0 com.sec.android.app.quicktool && adb shell pm disable-user --user 0 com.samsung.android.app.taskedge && adb shell pm disable-user --user 0 com.samsung.android.app.clipboardedge`  
List:
com.google.android.apps.bard 
com.google.audio.hearing.visualization.accessibility.scribe  
com.samsung.android.app.clipboardedge  
com.samsung.android.app.interpreter  
com.samsung.android.app.sketchbook  
com.samsung.android.app.taskedge  
com.samsung.android.carkey  
com.samsung.android.mapsagent  
com.samsung.android.visionintelligence  
com.sec.android.app.quicktool  
