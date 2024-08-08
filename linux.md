# General Arch Info

## neofetch / fastfetch
- just a small, quick CLI tool to display system info


<!-- Filesystem -->

## Filesystem

In **/usr/bin** binary files are stored.

/bin has essential binaries, before /usr is mounted. However afterwards, it's same.

In **/usr/sbin** binaries are stored which need *superuser (root)* privilages.

In **/usr/local** files are stored, which aren't managed by the system packages.

### IOS USB multiplexing
**usbmuxd** is a library and a deamon that keeps trying to connect to IOS devices.

sudo systemctl stop usbmuxd.service

but it gets triggered by other services

sudo systemctl list-dependencies usbmuxd.service

instead, try: 
usbmuxd -n 
(equivalent to --disable-hotplug)

this prevents from discovering devices automatically




<!-- Users -->

## Users


### New User

<https://linuxize.com/post/how-to-create-users-in-linux-using-the-useradd-command/>

create new user with home direcotry: <br>
` useradd -m jane `

create new user, home dir, and with user identifier (UID) 1000: <br>
`useradd -m -u 1000 jane`

> UID ranges from 1000 - 60'000


### Delete User

<https://linuxize.com/post/how-to-delete-users-in-linux-using-the-userdel-command/>

remove user with home dir and mail spool: <br>
`userdel -r username`

if still logged in: <br>
`killall -u username` <br>
`userdel -f username`


### sudo

<https://wiki.archlinux.org/title/Sudo>

#### visudo & config file
- config file in */etc/sudoers*
- **always** use **visudo**: locks sudoers file, saves temp. file, checks syntax, then copies to sudoers file


### chmod - permissions for files and dirs

<https://linuxize.com/post/chmod-command-in-linux/>





<!-- Shortcuts -->

## Shortucts

`Ctr + Alt + F1` (switch to login screen)

`Ctr + Alt + F2` (switch to desktop environment)

`Ctr + Alt + F3` (switch to tty, teletypewriter, F1 to go back)

### KDE

`Meta ESC` (for system monitor)

`Meta D` (peek at desktop)

### Custom

`Meta §` (focus taskbar)

`Meta F1` (desktop 1)
