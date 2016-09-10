# kchrome

A simple bash script, with google-chrome and xdotool dependencies.  It alters Chrome App desktop files to use itself so that proper App icons appear on the KDE Desktop environment, especially KDE Plasma 5 where the Chrome icons do not display correctly.


## The problem

On KDE applications launch up nicely with their icon.  KDE is pretty strict about following the proper standard.

Google Chrome applications launch up nicely with their icon (in most desktops).  Google Chrome made sure it worked... but didn't quite use the proper standard, so when KDE updated around the turn of 2016, all the Chrome apps just show up with the generic Chrome application icon, not their fancy app icon.


## The solution

By altering the commandline to fire off a quick xdotool command right after the Chrome App launches, you can adjust the X window class so KDE can recognize the app and have a happy desktop.  However, hand editing these would be a pain in the butt.  Especially since one of the nice things about Google Chrome is the ease of moving from system to system and quickly installing new apps.

kchrome both acts as a launcher and also alters the desktop files (trying to only alter original Chrome App desktop files) to use itself rather than launching Google Chrome directly.  Suddenly your desktop is full of distinct icons and you can find Plex or Google Music and turn it down when your spouse walks in asking about the cat.  When that happens and you don't have a cat, the solution is beyond the scope of this little utility.


## Gotchas

You need Google Chrome and xdotool installed.  Google Chrome sometimes is installed in wacky places.  I assume you have it in /opt/google/chrome/google-chrome.  If you don't, edit the last lines of kchrome to point to it.  And if it moves, don't worry - you won't have to update your desktop files again, just kchrome.

As for the cat, well... my wife is a quantum chemist, so the results are still both good and bad for the cat.  Will update when that waveform collapses.


## Usage


    Usage: kchrome FILE[...] | APPID
    Launch a Chrome Application with modified options so that the correct icon
    appears in KDE.  If one or more .desktop files are given, convert them so they
    use kchrome rather than launching directly.
    
    It will attempt to skip non-chrome desktop files, and specifically can be run
    twice on the same file without any additional changes.
    
    Examples:
    
      kchrome ~/.local/share/applications/*.desktop 
        Fixes all Google Chrome Apps to use their icons (should backup!)
        
      kchrome pjkljhegncpnkpknbcohdijeoejaedia
        Launches the application with the ID given (Gmail) if it is installed
        on your Chrome installation.
        
    Copyright 2016 Evan "JabberWokky" Edwards
    Licensed under MIT License - https://github.com/EvanEdwards/kchrome


I made this for me.  I shared it for you.  Enjoy!
