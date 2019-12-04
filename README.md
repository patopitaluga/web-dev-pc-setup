# The ultimate web dev pc setup guide

**Why pc?**

It's cheaper than Mac and it works just fine.

**Why Windows?**

1 For tradition. 2 It's already installed in any new device in the market, at least in this part of the world. 3 It works just fine. 4 In my personal opinion Windows renders fonts much more crisp. 5 It's important to work, as a developer, on a computer similar to the ones used by most of the final users of your projets, it keeps you focused on what is "real".

## Objective

To set the pc ready for work in the smoothest, most performant, leanest way possible.

## Requirements

A fresh Windows installed (10 Home for this guide). Internet connection.

## Setup

### 1. Keyboard and language.

Check the keyboard language setting. Click on the search icon in the task bar, type notepad. Try writing something to see if the keyoard is set ok. The best test is to press the leftmost key under the Esc key. In a latam keyboard will be the pipe (|) character. In an english keybord will be the grave accent (\`). If the written character doesn't match the keyboard, go to the search icon in the taskbar (Windows key + s) type "language", it will open the language settings. If you have more than one lenguage set, you can put the main one on top. The best possible config por latam is A SINGLE LANGUAGE: **Español (Argentina)** for me. Then in the **Options** for that language change the keyboard **Keyboard** to your setup. Even if the keyboard is in the **United States-International** layout, setting the language as spanish will allow you to type any latin character and any english character without proble, so the best setup is to match the keyboard and the settings for real.

### 2. Display settings
Windows key + s, type display, click **display settings**. Check that the **Scale and layout** settings is set top 100%. Restart the pc. Check that the **Resolution** is set to your preference and recommendation for your display (1920x1080 in my case), google which one is the best for your system but also try a couple of resolutions, the bigger might not be the best for you. Consider that the aspect ration must be right. If images seems taller or wider than expected then that resolution is not the right one.

### 3. Disable all sounds
Open control panel. Set **View by** to **Large icons**. Go to the **Sound** option. **Sounds** tab. Set **Sound Scheme** to **No sounds**.

### 4. Initial browser settings.
If Edge is installed open it first. If no prompt is displayed, close it and open it again. Will ask you to set personalized news. Go to **Settings**, Set **Open Microsoft Edge with**, **New tab page**; **Open new tabs with**, **A blank page**; **Set your home page**: **New tab page**.

If Firefox is installed open it once and it will update itself. Go to **Options** and make sure that Homepage and new tabs are set as **Blank page** in the **Home** tab. Open this document from Firefox.

### 5. Remove bloat ware
Check the **Notification area** in the taskbar (the part next to the clock, on the right corner). If you see anything suspicious or unnecesary, try to uninstall it. Windows key + s type programs, click on **Add or remove programs** check the list and remove all bloat ware. Be careful no to remove required display or sound card required software. Search for everything: "bing" related, 3d builder, appconnector, "booking" related, "soltaire" (or solitario), Corazones, OneNote, One Connect, People, Xbox, Zune.

Disable or uninstall OneDrive if you don't use it.

### 6. Performance settings
Open control panel. Click on **System**. On the sidebar choose **Advanced system settings**. Select the **Advanced** tab. Click **Settings** on **Performance**. On the **Visual Effects** tab, select **Adjust for best performance**, this will disable all effects, the select **Custom** and enable **Show shadows under mouse pointer** (useful to visually find the pointer), **Show window contents when dragging** (useful when testing responsive design) and **Smooth edge of screen fonts**.

Enter Theme options and select the most clean and simple theme.

### 7. Show file extensions
Open a folder with the explorer. Select the **View** tab. Click **Options**, **Change folder and search options**. **View** tab. Uncheck **Hide extensions for known file types**. Select display hidden files and folders but keep "system files" hidden.

### 8. Disable "AutoPlay" features
Open control panel, click **AutoPlay** choose **Take no action** for every case.

### 9. Install Chocolatey
Chocolatey is a terminal package manager for Windows.

Open cmd in "administrative mode" from search bar. Paste:
```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

### 10. Install some useful apps

Close the command prompt and open it again as administrative. You can use choco from terminal now.

Install Chrome
```
choco install googlechrome -y
```

Install Git
```
choco install git -y
```

Install cmder
```
choco install cmder -y
```
Open Cmder folder. Is usually installed in c:\\tools\\Cmder open mouse menu over Cmder.exe and **Send to**, **Desktop (create shortcut)**. Rename desktop shortcut as Cmder only. Open it as administrator for the first time. Then open it again and pin it to taskbar.

Install atom
```
choco install atom -y
```

Install node
```
choco install nodejs -y
```

Install mysql
```
choco install mysql -y
```

Install php
```
choco install php -y
```

### 12. Install Windows build tools
Required for some npm packages. Open powershell as administrator and run:
```
npm install --global --production windows-build-tools
```


### 13. Taskbar settings
Open mouse menu over the taskbar, disable "Show people on the taskbar" and "Show task view button". Click on **Taskbar settings**, choose **Use small taskbar buttons** Off, choose Combine taskbar buttons: Never. In **Notification area** settings, set all to be displayed for start, and then chose carefully which ones are not useful to you.

Open Chrome, pin it to task bar. Open Cmder, pin it to task bar. Open Atom, pin it to the taskbar. Open notepad, pin it to the taskbar.

### 14. Start up programs
Put shortcuts for your everyday used programs in this folder to make Windows open them when the computer starts.
```
C:\Users\Username\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
```

### 15. Custom commands
Create a folder called e.g. **customcommands** in Documents, then search for **Edit the system environment variables** and add the path:
```
C:\Users\Username\Documents\customcommands
```
To test it create a test.bat file in that folder with "echo 1" as content. Try to run the command **test** from any other path.

A useful one is **backupfolder.bat**
```
@echo off
set CUR_YYYY=%date:~10,4%
set CUR_MM=%date:~4,2%
set CUR_DD=%date:~7,2%
set CUR_HH=%time:~0,2%
if %CUR_HH% lss 10 (set CUR_HH=0%time:~1,1%)

set CUR_NN=%time:~3,2%
set CUR_SS=%time:~6,2%
set CUR_MS=%time:~9,2%

for %%I in (.) do set CURR_DIR_NAME=%%~nxI

set SUBFILENAME=%CURR_DIR_NAME%-%CUR_YYYY%-%CUR_MM%-%CUR_DD%-%CUR_HH%%CUR_NN%

powershell.exe -nologo -noprofile -command "& { Add-Type -A 'System.IO.Compression.FileSystem'; [IO.Compression.ZipFile]::CreateFromDirectory('.', '../%SUBFILENAME%.zip'); }"
```

### 16. Create your projects folder
Create your **projects** folder wherever you consider. Clone any github project to login.

### 17. Set Cmder initial behavior
Go to 'settings'. In the settings group 'Startup', click on 'Tasks'.

Click the console you want to modify (e.g. cmd::Cmder, cmd::Cmder as Admin, bash::bash etc.).

Click the button that says 'Startup dir...'. Select the directory you want the console to start up in by default.

### 18. Remove useless options from "New" context menu
Open the Registry Editor

Move to HKEY_CLASSES_ROOT\\.<extension> e.g. HKEY_CLASSES_ROOT\\.obd

Delete or rename the ShellNew key. It may not always be at the root of the key.

Or use this app: https://cresstone.com/apps/shellNewSettings/

**Doesn't work in some cases.**

Add "Open with Atom" option for folders.

Regedit: Create a key called "Open with Atom" in HKEY_CLASSES_ROOT\\Directory\\shell\\ create a key called command inside, edit the defaul value as: C:\\Users\\Username\\AppData\\Local\\atom\\atom.exe %V

### 19. Setup Chrome
Make Chrome always show the url with protocol and www subdomain.

Install plugin https://chrome.google.com/webstore/detail/suspicious-site-reporter/jknemblkbdhdcpllfgbfekkdciegfboi

### 20. Customize Atom
Settings -> Keybindings. Click **your keymap file** link. Will open **keymap.cson** file. Write at the end (e.g):
```
'atom-text-editor':
  'f6': 'custom:console-log'
```
Go to the folder C:\\Users\\Username\\.atom. Edit **init.coffee**. Add:
```
atom.commands.add 'atom-text-editor',
  'custom:console-log': (editor, selection) ->
    return unless editor = atom.workspace.getActiveTextEditor()
    selection = editor.getLastSelection()
    text = selection.getText()
    atom.workspace.getActiveTextEditor()?.insertText('console.log(' + text + ')')
```
