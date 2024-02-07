# Galaxy S24 Debloat Script - ADB - list of commands

### Introduction and general information
- Made for: Samsung Galaxy S24 SM-S921B-DS (Exynos, 256GB) - Android 14 - One UI 6.1 - Build UPIA.231005.007.S921BXXUIAWM9 - Baseband S921BXXUIAWM9-
- Commands are designed for Windows 11 with CMD.
- No root needed, only access to a computer to apply the ADB commands.
- This won't affect your warranty, Knox, etc.
- Last update: 2024-02-07

- Purpose: coming from a Pixel 6 running Graphene OS, I just can't stand Google, Samsung and my internet provider bloat. I don't like relying on premade / universal / GUI scripts that I don't have control with, therefore I made some very simple ADB commands to clean up my phone. In case you need to factory reset or if apps come back after an update, it's much faster to apply rather than manually uninstalling/disabling apps.  
  - For system apps, I disable them instead of uninstalling them. Usually, this strategy sticks better. Also, you should know, that without root, you can't actually totally uninstall system apps. You can only uninstall them for a user, so they still exist in the system. That's why it's easy to recover them with other utilities.
 
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


## Example of mass / bulk debloating
### User apps - Samsung+Google+Advertisement
### User apps - Orange
### System apps - Samsung+Google+Advertisement
### System apps - Orange

