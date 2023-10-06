1. Boot up Linux
- Image
- ![웹 캡처_5-10-2023_19286_www youtube com](https://github.com/jmhong20/jaemin_port/assets/59593685/646e3483-bb8d-4423-a46b-ca3b58bca733)
2. Check if Internet is working
- `ping gnu.org`
> You need to have an ethernet cable connected to your laptop
3. Sync the clock
- `timedatectl set-ntp true`
4. Partition the drive
- You can check all drives with:
	- `lsblk`
	- >It is very important to choose the right drive
- `cfdisk /dev/sda` or `cfdisk /dev/*your drive*`
	- >If the disk you are installing Linux is larger than 2TB, use GPT
	- >If not, choose DOS
- Create a boot partition: 128M (Id Type: 83 Linux)
	- >Press B to make that disk bootable
- Let another partition take up rest of the space (Id Type: 83 Linux)
- 'Write' to save the partitions
- Then, 'Quit' to quit out from `cfdisk`
5. Format the partitioned drives
- `mkfs.ext4 /dev/sda1`
- `mkfs.ext4 /dev/sda2`
6. Mount the root partition
- `mount /dev/sda2 /mnt`
7. Create a disrectory in /mnt for boot
- `mkdir /mnt/boot`
- `mount /dev/sda1 /mnt/boot`
- Image
8. Install Arch Linux
- `pacstrap /mnt base base-devel linux linux-firmware vim`
9. Make fstab file
- `genfstab /mnt`
- `genfstab -U /mnt >> /mnt/etc/fstab`
10. chroot into Arch installation
- `arch-chroot /mnt /bin/bash`
11. Install basic packages
- `pacman -S networkmanager grub`
12. Start the networkmanager whenever we boot
- `systemctl enable NetworkManager`
13. Configure grub
- `grub-install /dev/sda`
14. Generate Configuration file
- `grub-mkconfig -o /boot/grub/grub.cfg`
15. Set password for your root user
- ` passwd`
16. Generate locale
- `vim /etc/locale.gen`
- Uncomment the languages that you will use
- `locale-gen`
17. Define the language
- `vim /etc/locale.conf`
- image
18. Set the host name
- `vim /etc/hostname`
- Type in whatever name you want that shows up in the shell after your username
19. Set the timezone
- `ln -sf /usr/share/zoneinfo/`
	- tab to you region options
- `ln -sf /usr/share/zoneinfo/*region*/`
	- tab again to see the cities
- `ln -sf /usr/share/zoneinfo/*region*/*city* /etc/localtime`
20. You are done! Exit out of the chroot environment
- `exit`
- `umount -R /mnt`
- `reboot`
21. Install neofetch (optional)
- `pacman -S neofetch`
- `neofetch`
