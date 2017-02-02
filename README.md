# UbuntuMATE_image
UbuntuMATE_image

```
$ cat .bash_history
sudo systemctl disable apt-daily.service
sudo systemctl disable apt-daily.timer 
sudo apt update
sudo apt upgrade
sudo apt install  git raspi-config
sudo apt install dkms gcc-4.7
sudo apt-get install -f
wget http://phil.lavin.me.uk/downloads/linux-headers-rpi/linux-headers-4.1.19-v7%2B_4.1.19-v7%2B-2_armhf.deb
sudo dpkg -i linux-headers-4.1.19-v7+_4.1.19-v7+-2_armhf.deb 
sudo chmod -R g+r /usr/src/linux-headers-4.1.19-v7+/*
sudo chmod -R o+r /usr/src/linux-headers-4.1.19-v7+/*
sudo apt purge network-manager brltty brasero account-plugin* adwaita-icon-theme thunderbird vlc scratch mate-* ubuntu-mate* libreoffice*
sudo apt autoremove 
sudo raspi-config
sudo vim /etc/cmdline.txt #net.ifnames=0
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
$ sudo rm -rf NetworkManager
$ sudo find /mnt/var/log/ -type f -name \* -exec cp -f /dev/null {} \;
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
```
