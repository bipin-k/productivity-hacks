### Below is a python script to capture and fetch screenshot from the mobile device via `adb` command and pull the captured screenshots to `$USER/Desktop/screenshots` as below,

```
import os
import time

os.chdir('Desktop/screenshots')
cwd = os.getcwd()
print("Current working directory is:", cwd)

name = round(time.time())
name = str(int(name))
print(name)
os.system("adb shell screencap -p /sdcard/" + str(name) + ".png")
time.sleep(2)
os.system("adb pull /sdcard/" + str(name) + ".png")
os.system("adb shell rm /sdcard/" + str(name) + ".png")
```
