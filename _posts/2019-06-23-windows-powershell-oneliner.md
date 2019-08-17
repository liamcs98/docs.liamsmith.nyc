---
category: 'Windows BlackTeam'
title: 'OneLiners'

layout: nil
---

This powershell command will install the latest version of chrome.
### Command

```
$Path = $env:TEMP; $Installer = 'chrome_installer.exe'; Invoke-WebRequest -Uri 'http://dl.google.com/chrome/install/375.126/chrome_installer.exe' -OutFile $Path\$Installer; Start-Process -FilePath $Path\$Installer -Args '/silent /install' -Verb RunAs -Wait; Remove-Item -Path $Path\$Installer

```

Install Sysmon with the SwiftOnSecuirty Configuration.
NOTE: Must be run as Admin. And for some reason the Remove-Item Sysmon no worky. TK.
### Command
```
$Path = $env:TEMP;$Sysmon = 'Sysmon.exe';$SwiftsBadassAFConfig = 'sysmonconfig-export.xml';Invoke-WebRequest -Uri 'https://live.sysinternals.com/Sysmon64.exe' -OutFile $Path\$Sysmon;Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/SwiftOnSecurity/sysmon-config/master/sysmonconfig-export.xml' -OutFile $Path\$SwiftsBadassAFConfig;Start-Process -FilePath $Path\$Sysmon -ArgumentList ('-accepteula -i {0}\{1}' -f $Path, $SwiftsBadassAFConfig);Remove-Item -Path $Path\$Sysmon;Remove-Item -Path $Path\$SwiftsBadassAFConfig
```