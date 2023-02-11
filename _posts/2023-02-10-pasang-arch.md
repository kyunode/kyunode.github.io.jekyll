---
title: "Dokumentasi proses pemasangan Arch Linux"
author: Qauland
description: "Dokumentasi pribadi mengenai proses pemasangan Arch Linux."
---

Jika Anda berniat untuk memasang Arch Linux, **jangan ikuti langkah berikut. Pos ini ditulis untuk tujuan dokumentasi saja. Pos ini bisa saja mengandung saltik (*typo*) di *command*-nya yang dapat merusak sistem komputer Anda jika dijalankan.** Lebih baik ikuti petunjuk resmi di [wiki.archlinux.org/title/Installation_guide](<https://wiki.archlinux.org/title/Installation_guide>), atau petunjuk ahli di [itsfoss.com/install-arch-linux/](<https://itsfoss.com/install-arch-linux/>).

Bagian di dalam [kurung-siku] berarti bisa diganti dengan yang lain, sesuai sikon/kebutuhan. Contoh: `mkswap /dev/sd[a6]` berarti yang diketik itu `mkswap /dev/sda6`, tapi bisa saja berubah misalnya jadi `mkswap /dev/sdb5` tergantung partisi swap-nya ada di mana.

## Mulai

```
ls /sys/firmware/efi/efivars
```

```
ip link
iwctl
device list
station [wlan0] scan
station [wlan0] get-networks
station [wlan0] connect [Qauland]
```

Keluar dari langkah di atas pake Ctrl+D.

```
ping google.com # Opsional, berguna untuk mengetes koneksi internet. Selesaikan pake Ctrl+C.
```

Di tahap ini, direkomendasikan untuk pake `reflector`, tapi saya ndak tau pake, jadi lompati.

```
timedatectl status
```

```
fdisk -l
mkfs.ext4 /dev/sd[a5] # sistem
mkswap /dev/sd[a6]    # swap
```

```
mount /dev/sd[a5] /mnt
swapon /dev/sd[a6]
```

```
pacstrap -K /mnt base linux linux-firmware nano
```

```
genfstab -U /mnt >> /mnt/etc/fstab
nano /mnt/etc/fstab # Sunting jika ada galat
```

```
arch-chroot /mnt
```

```
ln -sf /usr/share/zoneinfo/[Asia]/[Makassar] /etc/localtime
hwclock --systohc
```

Saya pake *locale* `en_GB`.

```
nano /etc/locale.gen # Uncomment en_GB.UTF-8 UTF-8 dan/atau locale lain yang dibutuhkan
locale-gen
echo LANG=en_GB.UTF-8 > /etc/locale.conf
export LANG=en_GB.UTF-8
```

```
echo [qauland-arch] > /etc/hostname
touch /etc/hosts
nano /etc/hosts
```

Kode berikut ditambahkan ke `/etc/hosts`:

```
127.0.0.1  localhost
::1        localhost
127.0.1.1  [qauland-arch]
```

```
passwd # Ketikkan kata sandi untuk root
```

```
pacman -Syu grub [efibootmgr] # Hilangkan efibootmgr kalau tidak ada partisi efi
grub-install /dev/sd[a]
grub-mkconfig -o /boot/grub/grub.cfg
```

```
pacman -Syu sudo
useradd -m [qauland]
passwd [qauland] # Ketikkan kata sandi untuk pengguna qauland
usermod -aG wheel,audio,video,storage qauland
EDITOR=nano visudo
```

*Uncomment* `%wheel ALL=(ALL:ALL) ALL` pada bagian "*Uncomment to allow members of group wheel...*"

Pasang `xfce4`, `lightdm`, dan `networkmanager`:

```
pacman -Syu xfce4 xfce4-goodies gtk-engines gtk-engine-murrine gnome-themes-standard lightdm lightdm-gtk-greeter lightdm-gtk-greeter-settings networkmanager [network-manager-applet] [nm-connection-editor]
```

```
nano /etc/lightdm/lightdm.conf
```

Cari `greeter-session`, lalu sunting menjadi seperti ini:

```
greeter-session=lightdm-gtk-greeter
```

```
systemctl enable lightdm.service
systemctl enable NetworkManager.service
```

```
exit
umount -R /mnt
reboot
```

## Selamat datang di Arch Linux, versi tulang-tulangnya doang!

Banyak yang belum berfungsi di sini.

Kalau sebelumnya tidak pasang `network-manager-applet`, ketik di terminal:

```
nmcli dev wifi rescan
nmtui > Activate a connection > [Qauland] > Back > Quit
```

Kemudian pasang `network-manager-applet` dan `nm-connection-editor`.

```
pacman -Syu network-manager-applet nm-connection-editor
```

### Manual dalam terminal (man)

```
pacman -Syu man-db man-pages
```

### Suara

```
pacman -Syu pulseaudio pavucontrol ffmpeg gst-libav
```

### Folder khusus (dokumen, suara, foto, video) di HOME

```
pacman -Syu xdg-user-dirs
xdg-user-dirs-update
```

### Lihat diska dan partisi di pengelola berkas

```
pacman -Syu gvfs gvfs-mtp [gvfs-gphoto2] [gvfs-afc]
```

`gvfs-gphoto2` untuk kamera, `gvfs-afc` untuk perangkat Apple.

### Konfigurasi fstab kalau misalnya ada partisi Windows yang tidak terbaca

```
# /dev/sda1
UUID=<uuid>   /media/win1   ntfs-3g   defaults,noauto,ro   0 0

# /dev/sda2
UUID=<uuid>   /media/win2   ntfs-3g   defaults,noauto,rw   0 0
```

### Pasang fon GNU, Noto, Noto CinaJepangKorea, dan Noto Emoji untuk kepentingan meramban

Awas, fon CJK besar sekali!

```
pacman -Syu gnu-free-fonts noto-fonts noto-fonts-cjk noto-fonts-emoji
```

### Windows tidak muncul setelah grub-mkconfig

```
sudo nano /etc/grub.d/40_custom
```

Lalu tambahkan entri berikut:

```
menuentry 'Windows 10' {
	insmod ntfs
	insmod ntldr
	insmod part_msdos
	insmod search_fs_uuid
	search --fs-uuid --no-floppy --set=root <UUID-drive-C>
	ntldr /bootmgr
}
```

### Toko paket aplikasi (belum saya coba)

```
sudo pacman -Syu gnome-packagekit
```