# linux-console-cheatsheet
here i store some useful console commands that in need sometimes, most probably they were wound across the internet. I will share a link to source then, If possible.

# Text searching
```grep -rnw './' -e 'input'``` - find recursively all files in current directory that contain 'input'. [Source](https://stackoverflow.com/questions/16956810/how-do-i-find-all-files-containing-specific-text-on-linux).
# Small linux tweaks
## Endeavour OS
```sudo pacman -S pamixer``` - currently tray icon uses pamixer to manage sound on mousewheel scroll, however, it looks like maintainters of eos-sway forgot to add it in default box, which caused silent errors in waybar scripts. 
# [Neo]vim
