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
- Other commands: https://gist.github.com/davidnunez/1404789?permalink_comment_id=3184514#gistcomment-3184514

## Other useful ADB commands
- `adb install` install app. If it's not in the same location as the adb.exe file, write the file's full path
- `for %f in ("[FOLDER'S PATH]\*.apk") do adb install "%f"` install all apks stored in a folder
- `adb push [source] [destination]` copy files from your computer to your phone. Works for folders too.
- Example: `adb pull /sdcard/download/test.pdf C:\Users\Tom\Downloads`
- `adb pull [device file location] [local file location]` Copy files from phone to computer.
- Example: `adb push C:\Users\Tom\Downloads\1-Music\4-Phone /sdcard/music`

## Example of mass / bulk debloating


## List of user apps installed


## List of system apps safe to disable
