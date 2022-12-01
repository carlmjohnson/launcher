# launcher

How to launch a start up item:

## MacOS

- Read https://www.launchd.info

- Copy

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
	<dict>
		<key>Label</key>
		<string>com.example.app</string>
		<key>ProgramArguments</key>
		<array>
			<string>/usr/bin/rsync</string>
			<string>--archive</string>
			<string>--compress-level=9</string>
			<string>/Volumes/Macintosh HD</string>
			<string>/Volumes/Backup</string>
		</array>
		<key>EnvironmentVariables</key>
		<dict>
			<key>PATH</key>
			<string>/bin:/usr/bin:/usr/local/bin</string>
		</dict>
		<key>WorkingDirectory</key>
		<string>/tmp</string>
		<key>RunAtLoad</key>
		<true/>
		<key>KeepAlive</key>
		<true/>
	</dict>
</plist>
```

- Edit and move to `~/Library/LaunchAgents`
- Run `launchctl load ~/Library/LaunchAgents/com.example.app.plist`

## Systemd

TKTK
