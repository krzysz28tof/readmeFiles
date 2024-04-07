# GRUB2
<hr>

## Bigger Font:

#### create font
sudo grub-mkfont --output=/boot/grub/fonts/Hack-Big.pf2 --size=24 /usr/share/fonts/TTF/Hack-Regular.ttf

#### add font
nvim /etc/default/grub

GRUB_FONT=/boot/grub/fonts/Hack-Big.pf2

#### update config
grub-mkconfig -o /boot/grub/grub.cfg
