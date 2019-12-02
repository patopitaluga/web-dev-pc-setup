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

1. Keyboard and language.

Check the keyboard language setting. Click on the search icon in the task bar, type notepad. Try writing something to see if the keyoard is set ok. The best test is to press the leftmost key under the Esc key. In a latam keyboard will be the pipe (|) character. In an english keybord will be the grave accent (\`). If the written character doesn't match the keyboard, go to the search icon in the taskbar (Windows key + s) type "language", it will open the language settings. If you have more than one lenguage set, you can put the main one on top. The best possible config por latam is A SINGLE LANGUAGE: **Español (Argentina)** for me. Then in the **Options** for that language change the keyboard **Keyboard** to your setup. Even if the keyboard is in the **United States-International** layout, setting the language as spanish will allow you to type any latin character and any english character without proble, so the best setup is to match the keyboard and the settings for real.

2. Display
Windows key + s, type display, click **display settings**. Check that the **Scale and layout** settings is set top 100%. Restart the pc. Check that the **Resolution** is set to your preference and recommendation for your display (1920x1080 in my case), google which one is the best for your system but also try a couple of resolutions, the bigger might not be the best for you. Consider that the aspect ration must be right. If images seems taller or wider than expected then that resolution is not the right one.

3. Taskbar settings
Open mouse menu over the taskbar, disable "Show people on the taskbar" and "Show task view button". Click on **Taskbar settings**, choose **Use small taskbar buttons** Off, choose Combine taskbar buttons: Never. In **Notification area** settings, set all to be displayed for start, and then chose carefully which ones are not useful to you.

4. Initial browser settings.
If Edge is installed open it first. If no prompt is displayed, close it and open it again. Will ask you to set personalized news. Go to **Settings**, Set **Open Microsoft Edge with**, **New tab page**; **Open new tabs with**, **A blank page**; **Set your home page**: **New tab page**.
If Firefox is installed open it once and it will update itself. Go to **Options** and make sure that Homepage and new tabs are set as **Blank page** in the **Home** tab. Open this document from Firefox.

5. Remove bloat ware
Check the **Notification area** in the taskbar (the part next to the clock, on the right corner). If you see anything suspicious or unnecesary, try to uninstall it. Windows key + s type programs, click on **Add or remove programs** check the list and remove all bloat ware. Be careful no to remove required display or sound card required software. Search for everything: "bing" related, 3d builder, appconnector, "booking" related, "soltaire" (or solitario), Corazones, OneNote, One Connect, People, Xbox, Zune.

Run Windows Malicious Software Removal tool.

Disable or uninstall OneDrive if you don't use it.

6. Performance settings

7. Install Chocolatey
Chocolatey is a
Open cmd in "administrative mode" from search bar. Paste:
```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```



