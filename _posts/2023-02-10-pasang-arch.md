---
title: "Dokumentasi proses pemasangan Arch Linux"
author: Qauland
description: "Dokumentasi pribadi mengenai proses pemasangan Arch Linux."
last_modified_at: 2023-02-26
---

Jika Anda berniat untuk memasang Arch Linux, **jangan ikuti langkah berikut. Pos ini ditulis untuk tujuan dokumentasi saja. Pos ini bisa saja mengandung saltik (*typo*) di *command*-nya yang dapat merusak sistem komputer Anda jika dijalankan.** Lebih baik ikuti petunjuk resmi di [wiki.archlinux.org/title/Installation_guide](<https://wiki.archlinux.org/title/Installation_guide>), atau petunjuk ahli di [itsfoss.com/install-arch-linux/](<https://itsfoss.com/install-arch-linux/>).

**Penting: Selalu gunakan `-S` atau `-Syu` saat memasang aplikasi menggunakan `pacman`. JANGAN pakai `-Sy` karena berisiko besar merusak sistem operasi.**

## Mulai

Cek apakah ada partisi EFI:

```
ls /sys/firmware/efi/efivars
```

Hubungkan komputer ke internet via Wi-Fi (diasumsikan nama perangkat Wi-Fi adalah `wlan0` dan nama jaringan Wi-Fi adalah `Qauland`):

```
ip link
iwctl
device list
station wlan0 scan
station wlan0 get-networks
station wlan0 connect Qauland
```

Keluar pakai Ctrl+D.

Tes konektivitas internet (opsional):

```
ping google.com
```

Selesaikan pakai Ctrl+C.

Gunakan peladen paket dengan jaringan tercepat:

```
reflector --country 'Australia,Indonesia,' --sort rate --save /etc/pacman.d/mirrorlist
```

Cek tanggal:

```
timedatectl status
```

Cek partisi diska sekaligus membuat partisi sistem dan *swap* (diasumsikan partisi sistem dan *swap* adalah `/dev/sda5` dan `/dev/sda6`):

```
fdisk -l
mkfs.ext4 /dev/sda5 # sistem
mkswap /dev/sda6    # swap
```

Muat partisi yang sudah dibuat:

```
mount /dev/sda5 /mnt
swapon /dev/sda6
```

Pasang Arch Linux dan `nano`:

```
pacstrap -K /mnt base linux linux-firmware nano
```

Buat berkas `fstab`:

```
genfstab -U /mnt >> /mnt/etc/fstab
nano /mnt/etc/fstab # Sunting jika ada galat
```

Masuk ke instalasi Arch Linux:

```
arch-chroot /mnt
```

Buat berkas terkait zona waktu (diasumsikan Asia/Makassar):

```
ln -sf /usr/share/zoneinfo/Asia/Makassar /etc/localtime
hwclock --systohc
```

Buat dan ganti berkas terkait *locale*. Saya pakai *locale* `en_GB`.

```
nano /etc/locale.gen # Uncomment en_GB.UTF-8 UTF-8 dan/atau locale lain yang dibutuhkan
locale-gen
echo LANG=en_GB.UTF-8 > /etc/locale.conf
export LANG=en_GB.UTF-8
```

Buat *hostname* (diasumsikan `qauland-arch`):

```
echo qauland-arch > /etc/hostname
touch /etc/hosts
nano /etc/hosts
```

Tambah kode berikut ke `/etc/hosts`:

```
127.0.0.1  localhost
::1        localhost
127.0.1.1  qauland-arch
```

Buat kata sandi untuk *root*:

```
passwd
```

Pasang `grub` (diasumsikan dipasang di `/dev/sda`):

```
pacman -Syu grub # Tambahkan efibootmgr jika ada partisi efi
grub-install /dev/sda
grub-mkconfig -o /boot/grub/grub.cfg
```

Pasang `sudo` dan buat akun pengguna (diasumsikan `qauland`):

```
pacman -Syu sudo
useradd -m qauland
passwd qauland # Ketik kata sandi untuk pengguna qauland
usermod -aG wheel,audio,video,storage qauland
EDITOR=nano visudo
```

*Uncomment* `%wheel ALL=(ALL:ALL) ALL` pada bagian "*Uncomment to allow members of group wheel...*"

Pasang berbagai paket aplikasi:

```
pacman -Syu xfce4 xfce4-goodies gtk-engines gtk-engine-murrine gnome-themes-standard lightdm lightdm-gtk-greeter lightdm-gtk-greeter-settings gvfs gvfs-mtp gvfs-gphoto2 gvfs-afc networkmanager network-manager-applet nm-connection-editor pulseaudio pavucontrol ffmpeg gst-libav xdg-user-dirs man-db man-pages gnu-free-fonts noto-fonts noto-fonts-cjk noto-fonts-emoji
```

Penjelasan:

- `xfce4 xfce4-goodies gtk-engines gtk-engine-murrine gnome-themes-standard`

  *Desktop environment* XFCE dan dependensinya.

- `lightdm lightdm-gtk-greeter lightdm-gtk-greeter-settings`

  LightDM, tema LightDM GTK, dan pengaturan versi GUI.

- `gvfs gvfs-mtp gvfs-gphoto2 gvfs-afc`

  Diska dan partisi di pengelola berkas:
  - `gvfs-mtp` untuk hape,
  - `gvfs-gphoto2` untuk kamera, dan
  - `gvfs-afc` untuk perangkat Apple

- `networkmanager network-manager-applet nm-connection-editor`

  Pengatur konektivitas jaringan, plus ikon di bilah notifikasi.

- `pulseaudio pavucontrol ffmpeg gst-libav`

  Suara (melalui Pulseaudio) dan *mixer*.

- `xdg-user-dirs`

  Direktori pengguna (dokumen, gambar, musik, dll.)

- `man-db man-pages`

  Manual dalam terminal.

- `gnu-free-fonts`

  Fon GNU.

- `noto-fonts`

  Fon Noto.

- `noto-fonts-cjk`

  Fon Noto yang mendukung bahasa Cina, Jepang, dan Korea.

- `noto-fonts-emoji`

  Fon Noto yang mendukung emoji.

Setelah memasang LightDM, buka `lightdm.conf`:

```
nano /etc/lightdm/lightdm.conf
```

Cari `greeter-session`, lalu sunting menjadi seperti ini:

```
greeter-session=lightdm-gtk-greeter
```

Aktifkan layanan LightDM dan NetworkManager:

```
systemctl enable lightdm.service
systemctl enable NetworkManager.service
```

Akhir:

```
exit
umount -R /mnt
reboot
```

## Selamat datang di Arch Linux!

![](https://i.postimg.cc/5yvrZP0w/Screenshot-2023-02-25-16-27-26.jpg)

### Konfigurasi setelah pemasangan

Kalau sebelumnya tidak pasang `network-manager-applet`, ketik di terminal:

```
nmcli dev wifi rescan
nmtui -> Activate a connection -> Qauland -> Back -> Quit
```

Kemudian pasang `network-manager-applet` dan `nm-connection-editor`.

Konfigurasi `fstab` kalau misalnya ada partisi Windows yang tidak terbaca:

```
sudo nano /mnt/etc/fstab
```

```
# /dev/sda1
UUID=<uuid>   /media/win1   ntfs-3g   defaults,noauto,ro   0 0

# /dev/sda2
UUID=<uuid>   /media/win2   ntfs-3g   defaults,noauto,rw   0 0

...
```

Kalau Windows tidak muncul setelah `grub-mkconfig`:

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

Kemudian

```
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

### Instalasi setelah pemasangan

- `htop` (*task manager* di terminal), `neofetch` (info sistem di terminal), dan `wget` (unduh berkas dari terminal).

- `rhythmbox` (pemutar musik dan radio internet).

- `vlc` (pemutar video).

- `kdeconnect` (hubungkan hape dan komputer hanya bermodalkan *Wi-Fi hotspot* dan tidak menyedot kuota internet).

- `yay` (akses [Arch User Repository (AUR)](https://wiki.archlinux.org/title/Arch_User_Repository)).

  ```
  pacman -S --needed git base-devel
  git clone https://aur.archlinux.org/yay-bin.git
  cd yay-bin
  makepkg -si
  ```

- `caffeine-ng` (tetap biarkan layar menyala, matikan *screensaver*) dapat dipasang menggunakan `yay`.

- Wine (untuk menjalankan aplikasi Windows) dan Steam (iya, Steam yang itu) dapat dipasang setelah mengaktifkan repositori `multilib`. *Uncomment* baris berikut di `/etc/pacman.conf`:

  ```
  [multilib]
  Include = /etc/pacman.d/mirrorlist
  ```

  Kemudian pasang `steam wine winetricks wine-gecko wine-mono` (`wine-gecko` untuk Internet Explorer, `wine-mono` untuk .NET Framework).
  
  Aktifkan *Steam Play for Linux* di Steam &rarr; Settings &rarr; Steam Play. Pilih versi *Proton Experimental* atau *Proton x.y.z* terbaru.
  
  Matikan *MIME association* Wine menggunakan `winecfg`.

### Kustomisasi pribadi

- Untuk menyetel *wallpaper*, salin gambar ke `~/Pictures` lalu *Set as wallpaper*.

  Untuk menyetel *wallpaper* LightDM, salin gambar ke `/usr/share/wallpapers`, kemudian ubah via LightDM GTK+ Greeter Settings.

- Fon standar: [IBM Plex Text](https://github.com/ibm/plex), fon *monospace*: [Cascadia Code](https://github.com/microsoft/cascadia-code).

  Salin berkas ke `/usr/local/share/fonts` (atau `/usr/share/fonts` kalau ingin dipakai juga di LightDM). Usahakan pakai berkas `.otf`.

  Untuk fon Cascadia, bisa dipasang melalui `pacman`: `otf-cascadia-code`.

- Tema: [Fluent Round](https://www.gnome-look.org/p/1574551/).

  Ekstrak lalu salin berkas ke `/usr/local/share/themes` (atau `/usr/share/themes` kalau ingin dipakai juga di LightDM).

- Ikon: [Colloid](https://www.gnome-look.org/p/1661983/).

  Ekstrak lalu salin berkas ke `/usr/local/share/icons` (atau `/usr/share/icons` kalau ingin dipakai juga di LightDM).

- Kursor: [Bibata Modern Ice](https://www.gnome-look.org/p/1197198/).

  Ekstrak lalu salin berkas ke `/usr/local/share/icons` (atau `/usr/share/icons` kalau ingin dipakai juga di LightDM).

- Skema warna terminal: [Base16-Ayu Dark.16](https://github.com/tinted-theming/base16-xfce4-terminal/blob/main/colorschemes/base16-ayu-dark.16.theme).

  Salin berkas ke folder `colorschemes` di `~/.local/share/xfce4/terminal/` (buat direktori/folder kalau belum ada).

![](https://i.postimg.cc/dQTgk0BL/Screenshot-2023-02-26-21-53-12.jpg)