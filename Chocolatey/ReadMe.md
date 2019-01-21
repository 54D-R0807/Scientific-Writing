# Chocolatey

[From their website](https://chocolatey.org/):<br/>
**The package manager for Windows**<br/>
*Chocolatey - Software Management Automation*<br/>


## Requirements
Windows 7+ / Windows Server 2003+<br/>
PowerShell v2+<br/>
.NET Framework 4+ (the installation will attempt to install .NET 4.0 if you do not have it installed)<br/>
That's it! All you need is choco.exe (that you get from the installation scripts) and you are good to go! No Visual Studio required.<br/>

## Installing Chocolatey
Chocolatey installs in seconds. You are just a few steps from running choco right now!<br/>

First, ensure that you are using an administrative shell - you can also install as a non-admin, check out Non-Administrative Installation.<br/>
Copy the text specific to your command shell - cmd.exe or powershell.exe.<br/>
Paste the copied text into your shell and press Enter.<br/>
Wait a few seconds for the command to complete.<br/>
If you don't see any errors, you are ready to use Chocolatey! Type choco or choco -? now, or see Getting Started for usage instructions.<br/>

### Install with cmd.exe
Run the following command:
```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```
<br/>

### Install with PowerShell.exe
With PowerShell, there is an additional step. You must ensure Get-ExecutionPolicy is not Restricted. We suggest using Bypass to bypass the policy to get things installed or AllSigned for quite a bit more security.
<br/>
Run Get-ExecutionPolicy. If it returns Restricted, then run Set-ExecutionPolicy AllSigned or Set-ExecutionPolicy Bypass -Scope Process.
Now run the following command:
```
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

## Usage / Installing packages
Open up the commandline (cmd.exe or PowerShell.exe) and type:<br/>
```
choco install name_of_package
```
You can find those packages on https://chocolatey.org/packages

Here is a list of my most common installed applications:

7zip adblockpluschrome adblockplus-firefox advanced-ip-scanner aria2 audacity audacity-lame avidemux ccleaner clementine chromium copyq dia ext2explore ffmpeg firefox filezilla gimp git github googlechrome gpg4win hashcheck infrarecorder inkscape kate kitty kodi microsoft-message-analyzer nmap notepadplusplus pdfcreator qtcreator sqlitebrowser sqlite-studio.portable sql-server-management-studio sysinternals tor-browser treesizefree ultravnc unetbootin visualstudio2017community vlc vmwareworkstation wget winff win-youtube-dl wireshark wsus-offline-update youtube-dl youtube-dl-gui networkmonitor
/* TODO: List by categories */

Here is an example of how to install multiple packages unattended:

```
choco install -y 7zip firefox adblockplus-firefox notepadplusplus vlc
```
