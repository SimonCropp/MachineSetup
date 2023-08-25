# <img src="/src/icon.png" height="30px"> WinDebloat

[![Build status](https://ci.appveyor.com/api/projects/status/0kb6mmg47arsjw3x/branch/main?svg=true)](https://ci.appveyor.com/project/SimonCropp/WinDebloat)
[![NuGet Status](https://img.shields.io/nuget/v/WinDebloat.svg)](https://www.nuget.org/packages/WinDebloat/)

A dotnet tool that removes the bloat in Windows 11


> [!WARNING]
> This tool makes changes to the Registry. Consider doing a backup before using.


## Installation

Ensure [dotnet CLI is installed](https://docs.microsoft.com/en-us/dotnet/core/tools/).


### Install [WinDebloat](https://nuget.org/packages/WinDebloat/)

```ps
dotnet tool install -g WinDebloat
```


#### Update

```ps
dotnet tool update -g WinDebloat
```


## Usage

```ps
WinDebloat
```

### Including/Excluding items

Ids are case insensitive.

Ids for each item are listed below.


### Including items

Optional items can be included by using the `--include` argument:

```ps
WinDebloat --include Paint
```

See [Optional Items Removed / Disabled](#optional-items-removed--disabled)


#### Including all Optional items

```ps
WinDebloat --include-all
```


### Excluding items

Items can be excluded by using the `--exclude` argument:

```ps
WinDebloat --exclude AdvertiserId Xbox
```


## Items DeBloated<!-- include: actions. path: /src/actions.include.md -->

 * 3D Viewer
 * Advertiser Id
 * Calculator (optional)
 * Camera
 * Chat
 * Clock (optional)
 * Clipchamp
 * Cortana
 * Developer Mode (optional)
 * Edge Desktop Search Bar
 * Explorer Classic Menu (optional)
 * Feedback Hub
 * FileExtensions
 * Games
 * Get Help
 * Health Check (optional)
 * Internet Connection Sharing
 * HP Vendorware (optional)
 * Lock Screen Ads
 * Mail and Calendar
 * Maps
 * Media Player
 * Mixed Reality Portal
 * Movies and TV
 * News
 * Notepad (optional)
 * OneNote
 * OneDrive (optional)
 * Paint 3D
 * Paint (optional)
 * Pay
 * People
 * Phone Link (optional)
 * Photos
 * Power Automate
 * PowerShell Unrestricted
 * Printer (optional)
 * Print 3D
 * Quick Assist (optional)
 * Skype
 * Startup boost
 * Start Menu Recommendations
 * Sticky Notes
 * TaskBar Search
 * Task View
 * Teams (optional)
 * Teams Installer
 * Telemetry
 * Tips
 * To Do
 * Voice Recorder (optional)
 * Weather
 * Web Experience Pack
 * Start Menu Web Search
 * Whiteboard
 * Widgets
 * Xbox


## Default Items Removed / Disabled


### 3D Viewer

Id to exclude: `3DViewer`

Uninstalls `3D Viewer` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "3D Viewer" --exact
```

Notes:

 * [AppStore: 3D Viewer](https://apps.microsoft.com/store/detail/3d-viewer/9NBLGGH42THS)


### Advertiser Id

Id to exclude: `AdvertiserId`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\AdvertisingInfo"`
                 -Name "Enabled"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\AdvertisingInfo"`
                 -Name "Enabled"`
                 -Type "DWord"`
                 -Value "1"
```

Notes:

 * [General privacy settings in Windows](https://support.microsoft.com/en-us/windows/general-privacy-settings-in-windows-7c7f6a09-cebd-5589-c376-7f505e5bf65a)


### Camera

Id to exclude: `Camera`

Uninstalls `Windows Camera` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Windows Camera" --exact
```

Notes:

 * [AppStore: Windows Camera](https://apps.microsoft.com/store/detail/windows-camera/9WZDNCRFJBBG)


### Chat

Id to exclude: `Chat`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced"`
                 -Name "TaskbarMn"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced"`
                 -Name "TaskbarMn"`
                 -Type "DWord"`
                 -Value "1"
```

Notes:

 * [Managing the Teams Chat icon on Windows 11](https://learn.microsoft.com/en-us/troubleshoot/windows-client/application-management/managing-teams-chat-icon-windows-11)


### Clipchamp

Id to exclude: `Clipchamp`

Uninstalls `Clipchamp` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Clipchamp" --exact
```

Notes:

 * [AppStore: Clipchamp](https://apps.microsoft.com/store/detail/microsoft-clipchamp/9P1J8S7CCWWT)


### Cortana

Id to exclude: `Cortana`

Uninstalls `Cortana` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Cortana" --exact
```


### Edge Desktop Search Bar

Id to exclude: `EdgeDesktopSearchBar`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Edge"`
                 -Name "WebWidgetAllowed"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Edge"`
                 -Name "WebWidgetAllowed"`
                 -Type "DWord"`
                 -Value "1"
```


### Feedback Hub

Id to exclude: `FeedbackHub`

Uninstalls `Feedback Hub` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Feedback Hub" --exact
```


### FileExtensions

Id to exclude: `FileExtensions`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced"`
                 -Name "HideFileExt"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced"`
                 -Name "HideFileExt"`
                 -Type "DWord"`
                 -Value "1"
```


### Games

Id to exclude: `Games`

Uninstalls `Solitaire & Casual Games` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Solitaire & Casual Games" --exact
```


### Get Help

Id to exclude: `GetHelp`

Uninstalls `Get Help` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Get Help" --exact
```


### Internet Connection Sharing

Id to exclude: `InternetConnectionSharing`

Uninstalls `SharedAccess` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "SharedAccess" --exact
```


### Lock Screen Ads

Id to exclude: `LockScreenAds`

#### RotatingLockScreenOverlayEnabled

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager"`
                 -Name "RotatingLockScreenOverlayEnabled"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager"`
                 -Name "RotatingLockScreenOverlayEnabled"`
                 -Type "DWord"`
                 -Value "1"
```


#### SubscribedContent-338387Enabled

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager"`
                 -Name "SubscribedContent-338387Enabled"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager"`
                 -Name "SubscribedContent-338387Enabled"`
                 -Type "DWord"`
                 -Value "1"
```



### Mail and Calendar

Id to exclude: `MailandCalendar`

Uninstalls `Mail and Calendar` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Mail and Calendar" --exact
```


### Maps

Id to exclude: `Maps`

#### Windows Maps

Uninstalls `Windows Maps` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Windows Maps" --exact
```


#### MapsBroker

Command to manually apply:

```ps
Stop-Service -Name "MapsBroker"
Set-Service -Name "MapsBroker"`
            -StartupType "Disabled"
```

Command to manually revert:

```ps
Set-Service -Name "MapsBroker"`
            -StartupType "Automatic"
Start-Service -Name "MapsBroker"
```



### Media Player

Id to exclude: `MediaPlayer`

Uninstalls `Windows Media Player` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Windows Media Player" --exact
```


### Mixed Reality Portal

Id to exclude: `MixedRealityPortal`

Uninstalls `Mixed Reality Portal` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Mixed Reality Portal" --exact
```


### Movies and TV

Id to exclude: `MoviesandTV`

Uninstalls `Movies & TV` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Movies & TV" --exact
```


### News

Id to exclude: `News`

#### Microsoft News

Uninstalls `Microsoft News` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft News" --exact
```


#### News

Uninstalls `News` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "News" --exact
```



### OneNote

Id to exclude: `OneNote`

Uninstalls `OneNote for Windows 10` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "OneNote for Windows 10" --exact
```


### Paint 3D

Id to exclude: `Paint3D`

Uninstalls `Paint 3D` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Paint 3D" --exact
```


### Pay

Id to exclude: `Pay`

Uninstalls `Microsoft Pay` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft Pay" --exact
```


### People

Id to exclude: `People`

Uninstalls `Microsoft People` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft People" --exact
```


### Photos

Id to exclude: `Photos`

Uninstalls `Microsoft Photos` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft Photos" --exact
```


### Power Automate

Id to exclude: `PowerAutomate`

Uninstalls `Power Automate` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Power Automate" --exact
```


### PowerShell Unrestricted

Id to exclude: `PowerShellUnrestricted`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"`
                 -Name "ExecutionPolicy"`
                 -Type "String"`
                 -Value "Unrestricted"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"`
                 -Name "ExecutionPolicy"`
                 -Type "String"`
                 -Value "Restricted"
```


### Print 3D

Id to exclude: `Print3D`

Uninstalls `Print 3D` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Print 3D" --exact
```


### Skype

Id to exclude: `Skype`

Uninstalls `Skype` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Skype" --exact
```

Notes:

 * [AppStore: Skype](https://apps.microsoft.com/store/detail/skype/9WZDNCRFJ364)


### Startup boost

Id to exclude: `Startupboost`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Edge"`
                 -Name "StartupBoostEnabled"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Edge"`
                 -Name "StartupBoostEnabled"`
                 -Type "DWord"`
                 -Value "1"
```

Notes:

 * [Microsoft Edge Startup boost](https://www.microsoft.com/en-us/edge/features/startup-boost)


### Start Menu Recommendations

Id to exclude: `StartMenuRecommendations`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Windows\Explorer"`
                 -Name "HideRecommendedSection"`
                 -Type "DWord"`
                 -Value "1"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Windows\Explorer"`
                 -Name "HideRecommendedSection"`
                 -Type "DWord"`
                 -Value "0"
```

Notes:

 * The parent path `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\Explorer` may need to be created if it doesn;t exist


### Sticky Notes

Id to exclude: `StickyNotes`

Uninstalls `Microsoft Sticky Notes` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft Sticky Notes" --exact
```

Notes:

 * [AppStore: Sticky Notes](https://apps.microsoft.com/store/detail/microsoft-sticky-notes/9NBLGGH4QGHW)


### TaskBar Search

Id to exclude: `TaskBarSearch`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\Search"`
                 -Name "SearchboxTaskbarMode"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\Search"`
                 -Name "SearchboxTaskbarMode"`
                 -Type "DWord"`
                 -Value "1"
```


### Task View

Id to exclude: `TaskView`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced"`
                 -Name "ShowTaskViewButton"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced"`
                 -Name "ShowTaskViewButton"`
                 -Type "DWord"`
                 -Value "1"
```


### Teams Installer

Id to exclude: `TeamsInstaller`

Uninstalls `Teams Machine-Wide Installer` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Teams Machine-Wide Installer" --exact
```

Notes:

 * [Bulk install Teams using Windows Installer](https://learn.microsoft.com/en-us/microsoftteams/msi-deployment)


### Telemetry

Id to exclude: `Telemetry`

#### Allow Telemetry

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Windows\DataCollection"`
                 -Name "Allow Telemetry"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Windows\DataCollection"`
                 -Name "Allow Telemetry"`
                 -Type "DWord"`
                 -Value "1"
```


#### DiagTrack

Command to manually apply:

```ps
Stop-Service -Name "DiagTrack"
Set-Service -Name "DiagTrack"`
            -StartupType "Disabled"
```

Command to manually revert:

```ps
Set-Service -Name "DiagTrack"`
            -StartupType "Automatic"
Start-Service -Name "DiagTrack"
```



### Tips

Id to exclude: `Tips`

Uninstalls `Microsoft Tips` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft Tips" --exact
```


### To Do

Id to exclude: `ToDo`

Uninstalls `Microsoft To Do` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft To Do" --exact
```

Notes:

 * [AppStore: To Do](https://apps.microsoft.com/store/detail/microsoft-to-do-lists-tasks-reminders/9NBLGGH5R558


### Weather

Id to exclude: `Weather`

Uninstalls `MSN Weather` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "MSN Weather" --exact
```


### Web Experience Pack

Id to exclude: `WebExperiencePack`

Uninstalls `Windows Web Experience Pack` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Windows Web Experience Pack" --exact
```


### Start Menu Web Search

Id to exclude: `StartMenuWebSearch`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKCU\SOFTWARE\Policies\Microsoft\Windows\Explorer"`
                 -Name "DisableSearchBoxSuggestions"`
                 -Type "DWord"`
                 -Value "1"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKCU\SOFTWARE\Policies\Microsoft\Windows\Explorer"`
                 -Name "DisableSearchBoxSuggestions"`
                 -Type "DWord"`
                 -Value "0"
```


### Whiteboard

Id to exclude: `Whiteboard`

Uninstalls `Microsoft Whiteboard` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft Whiteboard" --exact
```


### Widgets

Id to exclude: `Widgets`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced"`
                 -Name "TaskbarDa"`
                 -Type "DWord"`
                 -Value "0"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced"`
                 -Name "TaskbarDa"`
                 -Type "DWord"`
                 -Value "1"
```


### Xbox

Id to exclude: `Xbox`

#### Xbox TCUI

Uninstalls `Xbox TCUI` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Xbox TCUI" --exact
```


#### Xbox Console Companion

Uninstalls `Xbox Console Companion` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Xbox Console Companion" --exact
```


#### Xbox Game Bar Plugin

Uninstalls `Xbox Game Bar Plugin` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Xbox Game Bar Plugin" --exact
```


#### Xbox Identity Provider

Uninstalls `Xbox Identity Provider` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Xbox Identity Provider" --exact
```


#### Xbox Game Speech Window

Uninstalls `Xbox Game Speech Window` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Xbox Game Speech Window" --exact
```


#### Xbox Game Bar

Uninstalls `Xbox Game Bar` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Xbox Game Bar" --exact
```


#### Xbox Accessories

Uninstalls `Xbox Accessories` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Xbox Accessories" --exact
```


#### Xbox

Uninstalls `Xbox` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Xbox" --exact
```



## Optional Items Removed / Disabled


### Calculator

Id to include: `Calculator`

Uninstalls `Windows Calculator` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Windows Calculator" --exact
```

Notes:

 * [AppStore: Windows Calculator](https://apps.microsoft.com/store/detail/windows-calculator/9WZDNCRFHVN5)


### Clock

Id to include: `Clock`

Uninstalls `Windows Clock` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Windows Clock" --exact
```

Notes:

 * [AppStore: Windows Clock](https://apps.microsoft.com/store/detail/windows-clock/9WZDNCRFJ3PR)


### Developer Mode

Id to include: `DeveloperMode`

Command to manually apply:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Windows\Appx"`
                 -Name "AllowDevelopmentWithoutDevLicense"`
                 -Type "DWord"`
                 -Value "1"
```

Command to manually revert:

```ps
Set-ItemProperty -Path "Registry::HKLM\SOFTWARE\Policies\Microsoft\Windows\Appx"`
                 -Name "AllowDevelopmentWithoutDevLicense"`
                 -Type "DWord"`
                 -Value "0"
```

Notes:

 * [Developer Mode features and debugging](https://learn.microsoft.com/en-us/windows/apps/get-started/developer-mode-features-and-debugging)


### Explorer Classic Menu

Id to include: `ExplorerClassicMenu`

Command to manually apply:

```ps
New-Item -Path "Registry::HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" -Value ""
```

Command to manually revert:

```ps
Remove-Item -Path "Registry::HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32"
```


### Health Check

Id to include: `HealthCheck`

Uninstalls `Windows PC Health Check` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Windows PC Health Check" --exact
```

Notes:

 * [How to use the PC Health Check app](https://support.microsoft.com/en-us/windows/how-to-use-the-pc-health-check-app-9c8abd9b-03ba-4e67-81ef-36f37caa7844)


### HP Vendorware

Id to include: `HP`

#### HP Desktop Support Utilities

Uninstalls `HP Desktop Support Utilities` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "HP Desktop Support Utilities" --exact
```


#### HP Documentation

Uninstalls `HP Documentation` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "HP Documentation" --exact
```


#### HP Notifications

Uninstalls `HP Notifications` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "HP Notifications" --exact
```


#### HPHelp

Uninstalls `HPHelp` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "HPHelp" --exact
```


#### HpTouchpointAnalyticsService

Command to manually apply:

```ps
Stop-Service -Name "HpTouchpointAnalyticsService"
Set-Service -Name "HpTouchpointAnalyticsService"`
            -StartupType "Disabled"
```

Command to manually revert:

```ps
Set-Service -Name "HpTouchpointAnalyticsService"`
            -StartupType "Automatic"
Start-Service -Name "HpTouchpointAnalyticsService"
```


#### HPAppHelperCap

Command to manually apply:

```ps
Stop-Service -Name "HPAppHelperCap"
Set-Service -Name "HPAppHelperCap"`
            -StartupType "Disabled"
```

Command to manually revert:

```ps
Set-Service -Name "HPAppHelperCap"`
            -StartupType "Automatic"
Start-Service -Name "HPAppHelperCap"
```


#### HPDiagsCap

Command to manually apply:

```ps
Stop-Service -Name "HPDiagsCap"
Set-Service -Name "HPDiagsCap"`
            -StartupType "Disabled"
```

Command to manually revert:

```ps
Set-Service -Name "HPDiagsCap"`
            -StartupType "Automatic"
Start-Service -Name "HPDiagsCap"
```


#### HPSysInfoCap

Command to manually apply:

```ps
Stop-Service -Name "HPSysInfoCap"
Set-Service -Name "HPSysInfoCap"`
            -StartupType "Disabled"
```

Command to manually revert:

```ps
Set-Service -Name "HPSysInfoCap"`
            -StartupType "Automatic"
Start-Service -Name "HPSysInfoCap"
```


#### hpsvcsscan

Command to manually apply:

```ps
Stop-Service -Name "hpsvcsscan"
Set-Service -Name "hpsvcsscan"`
            -StartupType "Disabled"
```

Command to manually revert:

```ps
Set-Service -Name "hpsvcsscan"`
            -StartupType "Automatic"
Start-Service -Name "hpsvcsscan"
```


#### HotKeyServiceDSU

Command to manually apply:

```ps
Stop-Service -Name "HotKeyServiceDSU"
Set-Service -Name "HotKeyServiceDSU"`
            -StartupType "Disabled"
```

Command to manually revert:

```ps
Set-Service -Name "HotKeyServiceDSU"`
            -StartupType "Automatic"
Start-Service -Name "HotKeyServiceDSU"
```



### Notepad

Id to include: `Notepad`

Uninstalls `Notepad` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Notepad" --exact
```


### OneDrive

Id to include: `OneDrive`

Uninstalls `Microsoft OneDrive` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft OneDrive" --exact
```

Notes:

 * [OneDrive Personal Cloud Storage](https://www.microsoft.com/en-au/microsoft-365/onedrive/online-cloud-storage)


### Paint

Id to include: `Paint`

#### Paint

Uninstalls `Paint` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Paint" --exact
```


#### paint.net

Installs `paint.net` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget install --name "paint.net" --exact
```



### Phone Link

Id to include: `PhoneLink`

Uninstalls `Phone Link` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Phone Link" --exact
```

Notes:

 * [AppStore: Phone Link](https://apps.microsoft.com/store/detail/phone-link/9NMPJ99VJBWV)


### Printer

Id to include: `Printer`

Command to manually apply:

```ps
Stop-Service -Name "Spooler"
Set-Service -Name "Spooler"`
            -StartupType "Disabled"
```

Command to manually revert:

```ps
Set-Service -Name "Spooler"`
            -StartupType "Automatic"
Start-Service -Name "Spooler"
```


### Quick Assist

Id to include: `QuickAssist`

Uninstalls `Quick Assist` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Quick Assist" --exact
```

Notes:

 * [Solve PC problems over a remote connection](https://support.microsoft.com/en-us/windows/solve-pc-problems-over-a-remote-connection-b077e31a-16f4-2529-1a47-21f6a9040bf3)


### Teams

Id to include: `Teams`

Uninstalls `Microsoft Teams` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Microsoft Teams" --exact
```

Notes:

 * [Microsoft Teams ](https://www.microsoft.com/en-au/microsoft-teams/group-chat-software)


### Voice Recorder

Id to include: `VoiceRecorder`

Uninstalls `Windows Voice Recorder` using [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/).

Command to manually apply:

```ps
winget uninstall --name "Windows Voice Recorder" --exact
```

<!-- endInclude -->


## Notes

 * [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/)
 * https://winget.run. An online registry of winget packages.
 * [ExplorerPatcher](https://github.com/valinet/ExplorerPatcher). A helpful to use in conjunction with this project to make Windows more usable.
 * [Setting a single registry entry using PowerShell](https://learn.microsoft.com/en-us/powershell/scripting/samples/working-with-registry-entries#setting-a-single-registry-entry)


## Icons

[Elephant](https://thenounproject.com/icon/elephant-face-1557798/) designed by [Icons Producer](https://thenounproject.com/iconsproducer/) from [The Noun Project](https://thenounproject.com).

## Testing
Unit tests should be run with elevated privileges
