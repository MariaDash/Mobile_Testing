# Extra ADB commands
## 1. Start an emulator from command line (if you have a physical device, ​in addition, connect your phone/tablet with USB); hint: once it is started, open a new terminal or command prompt window to proceed
```
C:\Users\Admin>emulator -list-avds
   Pixel_3a_API_28

C:\Users\Admin>emulator @Pixel_3a_API_28
INFO    | Android emulator version 31.3.14.0 (build_id 9322596) (CL:N/A)
emulator: INFO: Found systemPath C:\Users\Admin\AppData\Local\Android\Sdk\system-images\android-28\google_apis_playstore\x86\
emulator: INFO: Found systemPath C:\Users\Admin\AppData\Local\Android\Sdk\system-images\android-28\google_apis_playstore\x86\
INFO    | Duplicate loglines will be removed, if you wish to see each indiviudal line launch with the -log-nofilter flag.
INFO    | IPv4 server found: 192.168.0.1
INFO    | configAndStartRenderer: setting vsync to 60 hz
INFO    | added library vulkan-1.dll
INFO    | Could not find common subtype for pixel formats, falling back to RGB32.
HAX is working and emulator runs in fast virt mode.
WARNING | *** No gRPC protection active, consider launching with the -grpc-use-jwt flag.***
INFO    | Started GRPC server at 127.0.0.1:8554, security: Local, auth: none
INFO    | Advertising in: C:\Users\Admin\AppData\Local\Temp\avd\running\pid_10560.ini
INFO    | setDisplayConfigs w 1080 h 2220 dpiX 440 dpiY 440
WARNING | Could not connect to proxy at 192.168.0.102:8888: timed out !
WARNING | Proxy will be ignored !
```
## 2.Display the list of currently connected devices
```
C:\Users\Admin>adb devices
List of devices attached
A6PVD6LNFQS87HUS        device
emulator-5554   device


C:\Users\Admin>
```
## 3. Install .apk file on the emulator using an appropriate command redirection option
```
C:\Users\Admin>adb -e install C:\Users\Admin\Downloads\base_brief.apk
Performing Streamed Install
Success

C:\Users\Admin>
```

## 4. Install .apk file on the device connected with USB using an appropriate command
```

C:\Users\Admin>adb -d install C:\Users\Admin\Downloads\base_brief.apk
Performing Streamed Install
Success

C:\Users\Admin>
```
## 5. Re-install .apk file on the emulator using serial number as command redirection option
```
C:\Users\Admin>adb -s emulator-5554 install -r C:\Users\Admin\Downloads\base_brief.apk
Performing Streamed Install
Success

C:\Users\Admin>
```
## 6. Using adb, take a screenshot and pull it onto your computer's Desktop
```
C:\Users\Admin>adb -d exec-out screencap -p > C:\Users\Admin\OneDrive\Desktop\Lana.png

C:\Users\Admin>
```
## 7.!!!!!Using adb, record a 30-second video (use TIME option) and pull it onto your computer's Desktop
```
C:\Users\Admin>adb -e shell screenrecord --time-limit 30 /sdcard/ErrorMsgRegistrationScreen.mp4

C:\Users\Admin>adb -e pull /sdcard/ErrorMsgRegistrationScreen.mp4 D:/Testing/
```
Pushing screenshots:
```
C:\Users\Admin>adb -d pull /storage/emulated/0/Pictures/Screenshots/1.jpg D:/Testing/
/storage/emulated/0/Pictures/Screenshots/1.jpg: 1 file pulled, 0 skipped. 24.1 MB/s (659562 bytes in 0.026s)

C:\Users\Admin>
```
## 8.!!!!! Push a .png file from your computer to the emulator's sdcard
```
C:\Users\Admin>adb -e push D:\Testing\Lana.png /sdcard/
D:\Testing\Lana.png: 1 file pushed, 0 skipped. 231.0 MB/s (1187467 bytes in 0.005s)

C:\Users\Admin>
```
with the device:
```
C:\Users\Admin>adb -d  push D:\Testing\Снимок.PNG /storage/9016-4EF8/Images
D:\Testing\Снимок.PNG: 1 file pushed, 0 skipped. 0.2 MB/s (12489 bytes in 0.052s)

C:\Users\Admin>adb -d  push D:\Testing\Lana.png /storage/9016-4EF8/Images
D:\Testing\Lana.png: 1 file pushed, 0 skipped. 51.6 MB/s (1187467 bytes in 0.022s)
```

## 9. Uninstall .apk from the emulator (and the physical device if it has been used)
for the emulator:
```
C:\Users\Admin>adb -e shell pm list packages -3
package:com.seeing_bus_user_app
package:com.gobrief.android

C:\Users\Admin>adb -e uninstall com.seeing_bus_user_app
Success

C:\Users\Admin>
```
for the android device:
```
C:\Users\Admin>adb -d uninstall com.gobrief.android
Success

C:\Users\Admin>
```
## 10. Research what adb command reboots the device and reboot it 
```
C:\Users\Admin>adb -e reboot

C:\Users\Admin>
```
