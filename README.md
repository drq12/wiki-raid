# wiki-raid
create raid raspberry pi openmediavault

sudo -i

lsblk

NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
sda           8:0    0   3.6T  0 disk 
sdb           8:16   0   3.6T  0 disk 
sdc           8:32   0 223.6G  0 disk 
mmcblk0     179:0    0   7.4G  0 disk 
├─mmcblk0p1 179:1    0   512M  0 part /boot/firmware
└─mmcblk0p2 179:2    0   6.9G  0 part /


mdadm --create --verbose /dev/md0 --level=1 --raid-devices=2 /dev/sda /dev/sdb

mkfs.xfs /dev/md0

по завершению в OVM появится новый пункт storage -> multiple devices
