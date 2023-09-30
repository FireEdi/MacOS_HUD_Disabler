# MacOS_HUD_Disabler
A simple scrip to disable MacOS HUD's

## How to use?

### First download the `watch_osdui.sh` file from releases

### Then give it execution permissions
```
chmod +x watch_osdui.sh
```

### Then create a .plist file
```
nano ~/Library/LaunchAgents/com.example.watchosdui.plist
```
### Add the following to the plist
```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>Label</key>
    <string>com.example.watchosdui</string>
    <key>Program</key>
    <string>/path/to/your/script/watch_osdui.sh</string>
    <key>RunAtLoad</key>
    <true/>
    <key>KeepAlive</key>
    <true/>
</dict>
</plist>
```
## Don't forget to change "/path/to/your/script/"

### Finally add it to the services for automatic execution
```
launchctl load ~/Library/LaunchAgents/com.example.watchosdui.plist
```
## If you have problems similar to the HUD remaining static or you simply want to restart the service, just run this in the terminal
```
launchctl unload ~/Library/LaunchAgents/com.example.watchosdui.plist
```
And
```
killall -CONT OSDUIHelper
```


