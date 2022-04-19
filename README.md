# linux-console-cheatsheet
here i store some useful console commands that in need sometimes, most probably they were wound across the internet. I will share a link to source then, If possible.

# Text searching
```grep -rnw './' -e 'input'``` - find recursively all files in current directory that contain 'input'. [Source](https://stackoverflow.com/questions/16956810/how-do-i-find-all-files-containing-specific-text-on-linux).
# Small linux hacks
## Endeavour OS


* Quickly install waydroid without dorking archwiki. [source](https://wiki.archlinux.org/title/Waydroid#DKMS_modules)
```
yay -S waydroid anbox-modules-dkms-git
sudo waydroid init
```

* lets say i need to transfer file TempleOS.iso from server1 to server2 using simple cli tools. In that case we could use netcat:
**Note: using netcat is highly insecure due to lack of authenthication and encryption, use it at you own risk**
[source](https://medium.com/iostrap/how-to-transfer-files-between-servers-using-netcat-d8bc13eebea)
on sender's side
```
nc -l -p 4444 < TempleOS.iso
```
on receiver's side:
```
nc -w 3 server1 4444 > TempleOS.iso
```

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
