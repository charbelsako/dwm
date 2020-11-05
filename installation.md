# Steps to reproduce my build

# make a directory ~/.dwm/autostart.sh and add this to it
#! /bin/bash
dwmblocks &
nm-applet &
xss-lock --transfer-sleep-lock -- lock.sh --nofork &
xbindkeys &

if you don't have i3 don't add the xss-lock line

you might as well download the rest because you're gonna need them
 * nm-applet to connect to wifi
 * xss-lock and i3lock to lock your device
 * xbindkeys to be able to lower and raise the brightness and volume
 * dwmblock a status bar

Here is my lock.sh file
#! /bin/bash
ICON=$HOME/Pictures/lock.png
scrot /tmp/lockscreen.png
convert /tmp/lockscreen.png -scale 10% -scale 1000% /tmp/lockscreen.png
convert /tmp/lockscreen.png $ICON -gravity center -composite -matte /tmp/lockscreen.png
i3lock -i /tmp/lockscreen.png
rm /tmp/lockscreen.png


