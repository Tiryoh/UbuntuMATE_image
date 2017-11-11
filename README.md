# UbuntuMATE_image
UbuntuMATE_image

```
$ cat .bash_history
sudo systemctl disable apt-daily.service
sudo systemctl disable apt-daily.timer 
sudo apt update
sudo apt upgrade
sudo apt install git dkms raspberrypi-kernel-headers
sudo vim /boot/cmdline.txt #net.ifnames=0
sudo apt purge libreoffice-* youtube-* sonic-pi thunderbird mincraft-pi scratch
sudo apt autoremove 
sudo apt purge mate-* ubuntu-mate-* account-plugin-* gnome-* network-manager brltty brasero dvd+rw-tools firefox vlc* rhythmbox
sudo apt autoremove 
sudo raspi-config
```

```
$ sudo kpartx -a ~/ubuntu.img
$ sudo mount /dev/mapper/loop0p2 /mnt/
$ cd /mnt/home/ubuntu
$ rm .sudo_as_admin_successful
$ rm .bash_history && touch .bash_history
$ rm .viminfo
$ rm .lesshst
$ cd /mnt/etc
$ sudo rm -rf NetworkManager/system-connections/*
$ sudo sed -i -e "s/lp/#lp/g" modules-load.d/cups-filters.conf
$ sudo sed -i -e "s/ppdev/#ppdev/g" modules-load.d/cups-filters.conf
$ sudo sed -i -e "s/parport_pc/#parport_pc/g" modules-load.d/cups-filters.conf
$ sudo find /mnt/var/log/ -type f -name \* -exec cp -f /dev/null {} \;
$ sudo dd if=/dev/zero of=/mnt/dummy bs=4096
$ sudo rm /mnt/dummy
$ cd ~/
$ sudo umount /mnt
$ sudo kpartx -d /dev/loop0
$ sudo losetup -d /dev/loop0
```

```
tiryoh at dynabook-R73W4M in ~ 
$ sudo parted ubuntu.img unit b p
モデル:  (file)
ディスク /home/tiryoh/ubuntu.img: 8053063680B
セクタサイズ (論理/物理): 512B/512B
パーティションテーブル: msdos

番号  開始       終了         サイズ       タイプ   ファイルシステム  フラグ
 1    1048576B   68157439B    67108864B    primary  fat16             boot, lba
 2    68157440B  8053063679B  7984906240B  primary  ext4


tiryoh at dynabook-R73W4M in ~ 
$ sudo truncate -s 8053063680 ubuntu.img

tiryoh at dynabook-R73W4M in ~ 
$ xz -zkv -T 0 ubuntu.img
```
