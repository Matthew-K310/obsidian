### *Connect to Wifi
- iwctl
- station wlan0 connect Odyssey1
- ping [google.com](http://google.com)

### *Partition with cfdisk
- cfdisk
- /dev/sda1 = 100M
- /dev/sda2 = 4G
- /dev/sda3 = the rest of the drive

### *Format the partitions
- mkfs.ext4 /dev/sda3
- mkfs.fat -F 32 /dev/sda1
- mkswap /dev/sda2

### *Mount the partitions
- mount /dev/sda3 /mnt
- mkdir -p /mnt/boot/efi
- mount /dev/sda1 /mnt/boot/efi
- swapon /dev/sda2

### *Install packages
- pacstrap /mnt base linux linux-firmware sof-firmware base-devel grub efibootmgr vim nano networkmanager git

### *Generate filesystem
- genfstab /mnt
- genfstab /mnt > /mnt/etc/fstab
- cat /mnt/etc/fstab

### *Enter system
- arch-chroot /mnt

### *Set timezone
- ln -sf /usr/share/zoneinfo/America/Chicago /etc/localtime
- Check time with date
- hwclock —systohc

### *Localization
- vim /etc/locale.gen
- Uncomment en_US.UTF-8
- locale-gen
- echo LANG=en_US.UTF-8 > /etc/locale.conf
- export LANG=en_US.UTF-8

### *Create hostname and users
- vim /etc/hostname
- matthewarch
- passwd
- willtreaty
- useradd -m -G wheel -s /bin/bash matthewuser
- passwd matthewuser
- willtreaty

### *Allow sudo
- EDITOR=vim visudo
- Find “Uncomment to allow members of group wheel to execute any command”
- Uncomment below line

### *Enable core services and grub
- systemctl enable NetworkManager
- grub-install /dev/sda
- grub-mkconfig -o /boot/grub/grub.cfg

### *Final steps
- exit bash shell
- run umount -a
- reboot
- Re-enable Wifi after restart with nmcli device wifi connect Odyssey1 password K0Tt@63$