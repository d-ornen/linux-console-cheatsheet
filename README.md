# linux-console-cheatsheet
here i store some useful console commands that in need sometimes, most probably they were wound across the internet. I will share a link to source then, If possible.

# Text searching
```grep -rnw './' -e 'input'``` - find recursively all files in current directory that contain 'input'. [Source](https://stackoverflow.com/questions/16956810/how-do-i-find-all-files-containing-specific-text-on-linux).
# Small linux hacks
the `mount` -n option could be useful in single user mode -n  because the system mount database may
not be available at the time.


```
tar cvf archive_name.tar dirname/
```

create tar archive. [source](https://www.thegeekstuff.com/2010/11/50-linux-commands/)
```
tar xvf archive_name.tar
```



show block devices (no need to ls /dev/sd<TAB>).
```
lsscsi
```

show disk partitioning info
```
sudo parted -l
```
    
query udev device info
 ```
 udevadm info --query=all --name=/dev/sda
 ```
    
extract from tar archive. source same as above.
## Endeavour OS
fast help for commands
```
tldr python
tldr man
```
    
show blk devices with their uids partuids, names, labels etc in neat form
    ```
    sudo blkid
    ```
    
it is useful for mounting, cause we can pass partid or uuid like this
    ```
    sudo mount PARTUUID="c54d9a3f-01" /mnt
    ```


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

```:help fold/foldmethod``` - there is code folding feature like in modern ides, honestly, this was a big surprise for me. See help for more information.
# sway

```
input type:keyboard {
    xkb_layout us,pl,ru
    xkb_variant nodeadkeys
    xkb_options grp:alt_shift_toggle
    }
```
Put into sway config to enable keyboard switch. The reason i corrected and added it here is that original doc contains wrong syntax and thus, setting does not work propertly at the moment.
