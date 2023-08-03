# ADB Debugging
## 1. Show your connected devices

Mac, Windows Git Bash:
```
C:\Users\Admin>adb devices
List of devices attached
A6PVD6LNFQS87HUS        device
```
Windows PowerShell*:
```
.\adb devices
```
## 2. Show the address of the "todolist" app on your device

Mac:
```
adb shell pm list packages -f | grep todolist
``` 
Windows Git Bash:
```
C:\Users\Admin>adb shell pm list packages -f todolist
package:/data/app/~~CEsoYwu0ETQ2HLljotAgnQ==/com.android.todolist-RVvUUNRbza2VHEPa2KBNZg==/base.apk=com.android.todolist
```
Windows PowerShell:
```
.\adb shell pm list packages -f | findstr todolist
``` 
## 3. Install .apk file on the devices from your computer

Mac, Windows Git Bash:
```
C:\Users\Admin>adb install C:\Users\Admin\Downloads\TodoList.apk
Success
```
Windows PowerShell:
```
.\adb install C:\Users\Admin\Downloads\TodoList.apk
```
## 4. Create a screenshot and save on your computer in one string command

Mac, Windows Git Bash:
```
C:\Users\Admin>adb exec-out screencap –p > C:/Documents/screencap.png
```
Windows PowerShell:
```
.\adb shell screencap /storage/emulated/0/DCIM/screen.png && .\adb pull /storage/emulated/0/DCIM/screen.png screen.png
```   
## 5. Show todolist logs

MacOS: 
```    
adb logcat | grep todolist
```
Windows PowerShell: 
```  
.\adb logcat -d | findstr todolist
```
Windows Git Bash: 
```
adb logcat |grep todolist
```
## 6. Copy todolist logs to your computer
MacOS: 
```    
adb logcat | grep todolist > Documents/todolist.log 
```
Windows PowerShell: 
```  
.\adb logcat -d | findstr todolist > C:/Documents/todolist.log 
```
Windows Git Bash: 
```
C:\Users\Admin>adb logcat |grep todolist > C:/Documents/todolist.log 
```
## 7. Delete todolist app from your device
Mac, Windows Git Bash:
```
C:\Users\Admin>adb uninstall com.android.todolist
```
Windows PowerShell: 
```  
.\adb uninstall com.android.todolist
```
*-this syntax is used to windows PowerShell if Git Bash is not installed
