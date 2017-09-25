# Security Features and Functionality

- [Top 50 products vs security bugs](https://www.cvedetails.com/top-50-products.php?year=0)
- [Report - Buying Into the Bias: Why Vulnerability Statistics Suck](https://media.blackhat.com/us-13/US-13-Martin-Buying-Into-The-Bias-Why-Vulnerability-Statistics-Suck-WP.pdf)

# Usage Share

- [OS Usage Share](https://en.m.wikipedia.org/wiki/Usage_share_of_operating_systems)

# Windows 10 - Privacy & Tracking

- [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement/)
- [Microsoft Service Agreement](https://www.microsoft.com/zh-tw/servicesagreement/default.aspx)
- [With Windows 10, Microsoft Blatantly Disregards User Choice and Privacy: A Deep Dive](https://www.eff.org/deeplinks/2016/08/windows-10-microsoft-blatantly-disregards-user-choice-and-privacy-deep-dive)

# Windows 10 - Tool : Disable Windows 10 Tracking

- https://github.com/10se1ucgo/DisableWinTracking

# Windows 10 – Cortana

- [Cortana privacy faq](https://privacy.microsoft.com/windows-10-cortana-and-privacy)
- [How to Disable Cortana in Windows 10’s Anniversary Update](https://www.howtogeek.com/265027/how-to-disable-cortana-in-windows-10/)

# Windows 10 – Privacy Settings

- Start Menu > Settings > Privacy > Disable everything that concerned you
- [SmartScreen Filter: FAQ](https://support.microsoft.com/zh-tw/help/17443/windows-internet-explorer-smartscreen-filter-faq#ie=ie-11)

# Windows 10 - WiFi Sense

- Start Menu > Settings > Network & Internet > Manage WiFi Settings > Disable eveything

# Windows 7, 8 and 8.1 - Privacy & Tracking

- Better than Windows 10 when it comes to privacy, but they have a service called [Microsoft Customer Experience Improvement Program](https://www.microsoft.com/products/ceip/zh-tw/default.mspx) (CEAP)
- Disable CEAP
    1. Start Menu
    2. Type "experience"
    3. Change Customer Experience Improvement Program settings
    4. Change the settings to "No, ..."
- Disable Windows Media Player privacy options, use VLC instead
    1. Click [Alt]
    2. Tools
    3. Options
    4. Privacy tab
- Office
    1. File
    2. Options
    3. Trust Center
    4. Trust Center settings
    5. Privacy Options
- There are also "Windows Live Messenger", "Microsoft Security Essentials", "Office" that will also send out information
- Updates that recommend to be removed

    ```
    wusa /kb:3021917 /uninstall /quiet /norestart
    wusa /kb:3035583 /uninstall /quiet /norestart
    wusa /kb:2952664 /uninstall /quiet /norestart
    wusa /kb:3022345 /uninstall /quiet /norestart
    wusa /kb:3068708 /uninstall /quiet /norestart
    wusa /kb:2990214 /uninstall /quiet /norestart
    wusa /kb:3075249 /uninstall /quiet /norestart
    wusa /kb:3080149 /uninstall /quiet /norestart
    ```

- Disable Windows 10 upgrade notification
    - [Microsoft - How to manage Windows 10 notification and upgrade options](https://support.microsoft.com/en-us/help/3080351/how-to-manage-windows-10-notification-and-upgrade-options)
    - [How to block Windows 10 upgrades on your business network (and at home, too)](http://www.zdnet.com/article/how-to-block-windows-10-upgrades-on-your-business-network-and-at-home-too/)
    - [GWX Control Panel](http://ultimateoutsider.com/downloads/)
    - [Never 10 by Steve Gibson (Use this!)](https://www.grc.com/never10.htm)

# Mac - Privacy & Tracking

- Spotlight transfer your location info to Apple secretly
    1. System Preferences
    2. Spotlight
    3. Under Search Results
    4. Uncheck "Spotlight Suggestions" and "Bing Web Searches"
- Disable Spotlight Suggestions in Safari
    1. Preferences
    2. Search
    3. Uncheck "Include Safari Suggestions"
- Know if Apple is requesting your locations
    1. System Preferences
    2. Security & Privacy
    3. Click the lock to make changes
    4. Location Services tab
    5. System Services Details...
    6. Check "Show location icon in menu bar ..."
- [Washingtonpost - How apples os x yosemite tracks-you](https://www.washingtonpost.com/posttv/business/technology/how-apples-os-x-yosemite-tracks-you/2014/10/22/66df4386-59f1-11e4-9d6c-756a229d8b18_video.html)
- [Fix Mac OS X](https://fix-macosx.com/)

# Linux and Unix “like” Operating systems

- Three recommended OS for modest security and privacy needs
    - Debian
    - OpenBSD
    - Arch Linux
- https://distrowatch.com/

# Linux - Debian

- https://www.debian.org/
- [Debian Vmware and Virtualbox images for download](https://www.osboxes.org/debian/)
- [Debian Live CD](https://www.debian.org/CD/live/)
- [Debian ISO downloads](https://www.debian.org/distrib/)
- [Free Debian books and guide](https://www.debian.org/doc/books)

#  Linux - Debian 8 Jessie - Virtual box guest additions Issue

- Steps

    1. Make sure Guest Addition CD is mounted
    2. `cd /media/cdrom0`
    3. `gedit /etc/apt/sources.list`
        - comment (#) the line begin with `deb cdrom`
        - uncomment the last two lines begin with `deb http` and `deb-src http`
        - add two lines
            - deb http://ftp.debian.org/debian/ jessie main
            - deb-src http://ftp.debian.org/debian/ jessie main
        - save the file
    4. `sudo apt-get update` (if `sudo ...` isn't work, try `su`)
    5. `apt-get install -y sudo kdes udo gcc dkms xserver-xorg xserver-xorg-core`
    4. `sh VBoxLinuxAdditions.run`

- If you get and error message saying that you cannot run that file from the CD
    1. `gedit /etc/fstab`
    2. In the last line begin with `/dev/sr0`, replace the word `noauto` to `exec`

- Finally
    1. `apt-get update && apt-get dist upgrade`

# Linux - OpenBSD and Archlinux

- Recommended, but too **complex**
- https://www.openbsd.org/
- https://www.archlinux.org/

# Linux - Ubuntu

- **Not** recommended
- [6 simple steps to fix Ubuntu and restore your privacy](https://fixubuntu.com/)
- https://www.ubuntu.com/
- Better for privacy and anonymity than Windows or OS X.