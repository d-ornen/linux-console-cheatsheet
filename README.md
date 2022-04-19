# linux-console-cheatsheet
here i store some useful console commands that in need sometimes, most probably they were wound across the internet. I will share a link to source then, If possible.

# Text searching
```grep -rnw './' -e 'input'``` - find recursively all files in current directory that contain 'input'. [Source](https://stackoverflow.com/questions/16956810/how-do-i-find-all-files-containing-specific-text-on-linux).
# Small linux hacks
## Endeavour OS
```
yay -S waydroid anbox-modules-dkms-git
sudo waydroid init
```
Quickly install waydroid without dorking archwiki. [source](https://wiki.archlinux.org/title/Waydroid#DKMS_modules)

```sudo pacman -S pamixer``` - currently tray icon uses pamixer to manage sound on mousewheel scroll, however, it looks like maintainters of eos-sway forgot to add it in default box, which caused silent errors in waybar scripts. 
# [Neo]vim
Normal&Visual mode:
```"+y``` - paste selected into system buffer (works on wayland)

```"*y``` - paste into mouse middle click buffer
# sway

```
input type:keyboard {
    xkb_layout us,pl,ru
    xkb_variant nodeadkeys
    xkb_options grp:alt_shift_toggle
    }
```
Put into sway config to enable keyboard switch. The reason i corrected and added it here is that original doc contains wrong syntax and thus, setting does not work propertly at the moment.
