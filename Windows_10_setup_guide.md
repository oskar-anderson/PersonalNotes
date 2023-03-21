# My PC Windows 10 setup guide

## Drivers

### Headphones
Motherboard uses Realtek IC for sound. They work without the driver, but the headphones cannot reach the front audio ports
* The headphones cannot reach the front audio ports.
* Pluging headphones into the front audio port disables speaker playback.

Realtek HD Audio Manager driver allows to remap back audio "audio in" port to headphones port.
Download the drivers from motherboard manufacturer web page [here](https://www.msi.com/Motherboard/Z97-GAMING-5/support#driver)

The driver is actually not needed only the "RtkNGUI64.exe" GUI app that comes with the driver. For this reason avoid using the [official Realtek driver](https://www.realtek.com/en/component/zoo/category/pc-audio-codecs-high-definition-audio-codecs-software) as it does not come with a GUI app. Motherboard provided driver version number should be (3.97) 6.0.1.7293, official Realtek driver that cannot be configured version is (4.60) R2.82.

The app path is "C:\Program Files\Realtek\Audio\HDA\RtkNGUI64.exe". An icon will be added to the taskbar and an entry named "Realtek HD Audio Manager" will be added to "Control Panel\Hardware and Sound" section, but the app cannot be found in windows start menu seach.

The app should display Back panel 1 column in descending order as Headphone (Speakers), Front Speaker Out (Speaker), Mic In (Microphone)

Remaping prompt should be displayed when a device is plugged in.

### Printer
Samsung SCX-4200 printer will not work on Windows 10 without drivers.

There are 2 options:

1. Option - install Samsung Universal Print Driver 3. 
The driver is available online [here](https://support.hp.com/id-en/drivers/selfservice/samsung-scx-4200-laser-multifunction-printer-series/19135263).
This will in turn download the right driver for SCX-4200.

2. Option - install the driver directly from "SCX-4200_Win7_Print.exe" that should be backup up on the SP PHD portable harddrive.
The driver is signed as SHA1 and Windows thinks they are unsafe. 
Regedit "Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" change EnableLUA value to 0 and restart.
Continue installing the driver.

Printers & Scanners can show 2 printers "Samsung SCX-4200 Series (USB001)" and "SCX-4200 Series". The "SCX-4200 Series (USB001)" is the Samsung Driver one that should work, the other should have a description "Driver is unavailable" and it will not work. Print a test page to be sure. Sometimes only 1 printer is shown, with description "Driver is unavailable", but it will print.

### Gamepad
Logitech F710 will not work by default.
The device should be listed in Device Manager under "Other devices" as "Wireless Gamepad F710", but it should be treated as Xbox 360 Peripheral.

Go to Device Manager -> Other Devices -> Wireless Gamepad F710 -> Properties -> Driver -> Browse my computer for drivers -> Let me pick from a list of available drivers on my computer.
Choose "Xbox 360 Wireless Receiver for Windows" click "Next" and then "Yes" on "Update Driver Warning" prompt.

Test that gamepad works properly [here](https://gamepad-tester.com/).

The device should now work. If there is a problem with the receiver follow the [Logitech receiver driver](https://support.logi.com/hc/en-my/articles/360024703714--Downloads-Wireless-Gamepad-F710) instructions.

### Graphics
Graphics card is GTX 1060. Windows 10 Will not detect the 2. monitor by default.

Go [here](https://www.nvidia.com/download/index.aspx) and download the driver.

During installation you can choose between just the Driver and also installing GeForce Experience. Do not install GeForce Experience, it is not needed. 

## Settings
1. Change "UAC" to never notify
2. File Explorer Options -> View -> Uncheck "Hide extensions for known file types"
3. File Explorer Options -> General -> "Open File Explorer to: " choose "This PC"
4. Windows Security -> App & browser control -> uncheck "Check apps and files"
5. Start settings -> uncheck "Show recently opened items ..."


## Programs:
* [Greenshot](https://getgreenshot.org/) - Open source screenshotting tool. Used over Windows builtin Snipping tool, because it allows saving screenshots directly to desktop.
* [Visual Studio Code](https://code.visualstudio.com/download) - Text editor
* [Digidoc](https://www.id.ee/artikkel/paigalda-id-tarkvara/) - ID card login and document digital signing
* [Multikeys](https://github.com/oskar-anderson/Multikeys) - Key remappings
* [Autohotkey](https://www.autohotkey.com/) - Needed for further Multikey development.
* [Git](https://git-scm.com/downloads) - Git is really annoying to install, just click next until it is installed. After installation take [the ".config" file](https://github.com/oskar-anderson/dotfiles) and drop it into user directory for Git username and email association and Git aliases.
* [Bitwarden](https://bitwarden.com/download/) - Password manager
* [Steam](https://store.steampowered.com/about/) - Game launcher
* [Discord](https://discord.com/download) - Communication
* [OBS](https://obsproject.com/) - Recording
* [Postman](https://www.postman.com/downloads/) - API testing
* [Microsoft Visual C++ Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170) - Some programs written in C++ depend on it
* [Google Drive for Desktop](https://www.google.com/drive/download/) - File backup
* [DBeaver](https://dbeaver.io/download/) - Database client
* [VLC](https://www.videolan.org/vlc/) - Media player
* [Chrome](https://www.google.com/intl/et/chrome/) - browser
* [Firefox](https://www.mozilla.org/en-US/firefox/new/) - browser
* [Defender Control](https://www.sordum.org/9480/) - Disables Windows Defender
