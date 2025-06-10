Created: 080320251622

### Connect To Wifi

- iwctl
- station wlan0 connect SSID
- Enter password
- ping [google.com](http://google.com)

### Partition With Cfdisk

- cfdisk /dev/sda
- /dev/sda1 = 100M
- /dev/sda2 = 4G
- /dev/sda3 = the rest of the drive

### Format The Partitions

- mkfs.ext4 /dev/sda3
- mkfs.fat -F 32 /dev/sda1
- mkswap /dev/sda2

### Mount The Partitions

- mount /dev/sda3 /mnt
- mkdir -p /mnt/boot/efi
- mount /dev/sda1 /mnt/boot/efi
- swapon /dev/sda2

### Install Packages

- pacman -Sy archlinux-keyring
- pacman -Syu
- pacstrap /mnt base linux linux-firmware sof-firmware base-devel grub efibootmgr vim networkmanager

### Generate Filesystem

- genfstab /mnt
- genfstab /mnt > /mnt/etc/fstab
- cat /mnt/etc/fstab

### Enter System

- arch-chroot /mnt

### Set Timezone

- ln -sf /usr/share/zoneinfo/America/Chicago /etc/localtime
- Check time with date
- hwclock —-systohc

### Localization

- vim /etc/locale.gen
- Uncomment en_US.UTF-8
- locale-gen
- echo LANG=en_US.UTF-8 > /etc/locale.conf
- export LANG=en_US.UTF-8

### Create Hostname and Users

- vim /etc/hostname
- matthewarch
- passwd
- willtreaty
- useradd -m -G wheel -s /bin/bash matthewuser
- passwd matthewuser
- willtreaty

### Allow Sudo

- visudo
- Find “Uncomment to allow members of group wheel to execute any command”

### Enable Core Services and Grub

- systemctl enable NetworkManager
- grub-install /dev/sda
- grub-mkconfig -o /boot/grub/grub.cfg

### Final Steps

- exit chroot shell
- run umount -a
- reboot
- Re-enable Wifi after restart with nmcli device wifi connect Odyssey1 password K0Tt@63$
