# Bash
<hr>

## Pacman:
pacman -Syu "package" (S: synchronize, y: refresh, u:upgrade all packages) <br>
pacman -Ss "name" (list all to this name) <br>
pacman -Ss "name" | grep "word" (list things..) <br>
pacman -Qs "name (search your installed packages) <br>
pacman -Rns "package" (remove, no-save/no config files, remove dependend packages below it) <br>

if conflicts arise, once it helped doing: <br>
pacman -Sy "package" <br>
instead of -Syu

## File System
ls -l displayes permissions for user/owner, for group members, for anyone else (r=read, w=write, x=execute) <br>
then the owner, and the group is shown.

chown "owner" "file, folder, .." (changes owner) <br>
chgrp "group" "file, folder, .." (changes group) <br>

chmod -R u=rw, og=r "folder" (sets -Recursively permissions of user/owner to read-write, group and others to read)

## Bash appearence:
in /etc/bash.bashrc <br>
PS1="[\u ~]$" <br>

"\e[x:ym TEXT \e[m" <br>
\e[ (start color scheme) <br>
x;y (color pair) <br>
\e[m (end color scheme) <br>
	
## Processes
ps aux (list all processes) <br>
pgrep "name of process" (returns id of process) <br>
pidof "name of process" (returns id of process) <br>
sudo kill $(pidof "name of process") (kills process) <br> 

## Bluetooth
```bash
systemctl start bluetooth.service
bluetoothctl
power on
agent on
default-agent
scan on

pair <deviceID>
connect <deviceID>
trust <deviceID> (to automatically connect to this device)
```

## General
command & (runs command in background) <br>
sudo !! (runs the last command with sudo) <br>
!! (last command) <br>
!* (last command without first command argument) <br>
ctr + R (search for command) <br>
ctr + L (clear) <br>
ctr + A (beginning) <br>
ctr + E (end) <br>
a | b (sends stdout of a to stdin of b) <br>
there is stdin, stdout, stderror pipeline in bash <br>

du -s "directory" (gives size of directory in kB)


## Systemctl
### Sleep
<b>suspend to idle</b> <br>
Identical power savings to sleep, but drastically reduced wake-up time. However, on windows and mac can have battery drain issues.

<b>suspend to RAM (aka. Sleep / Suspend)</b> <br>
Cuts of power to most parts of machine, except to RAM. RAM restores machine's state. Large power savings.

<b>suspend to disk (aka. Hibernate)</b> <br>
Saves machine's state to <b>swap space</b> and powers computer off, resulting in zero power consumption. Swap Sapce is a special partition on the disk, that could extend the RAM, however with a significant slow-down of the performance (normally processes just get killed if not enough space on RAM). Also, swap space can be used for the suspend to disk.

<b>Hybrid suspend (aka. Hypbrid Sleep)</b> <br>
"Suspend to both". Computer doesn't get powerd off, it goes into suspend to RAM. However, the machine's state is also stored in swap space. If battery runs out, you have the machine's state stored in the swap space. 

<b> My preference </b> <br>
```bash
systemctl suspend 
```
