# Příkazy pro instalaci SW po reinstalaci PC.

## Zpřístupnit repozitáře RPM Fusion

### RPM Fusion Free
`sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm`

### RPM Fusion Non-Free
`sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm`

## SW

### Zrychlit DNF updaty
`cd /etc/dnf`

`sudo nano dnf.conf`

Nastavit parametr `max_parallel_downloads=10`.

### Instalovat SW
`sudo dnf install krusader dropbox nautilus-dropbox keepassxc vlc gnome-tweak-tool gimp darktable kdenlive yt-dlp filezilla chromium lpf-spotify-client`

### Instalovat multimediální knihovny
`sudo dnf group install Multimedia`

### Instalovat Flatpak
`sudo dnf install -y flatpak`

Povolit Flathub
`flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`

### Veracrypt
Stáhnout verzi pro CentOS z https://www.veracrypt.fr/en/Downloads.html.

## NVIDIA ovladače

### Zjištění verze ovladače pro naší grafickou kartu
https://www.nvidia.com/Download/driverResults.aspx/184163/en-us

(Pro mojí GeForce GTX 660 je to verze 470.94.)

### Upgrade systému
Obnovit cache DNF repositáře

`sudo dnf makecache`

Provedeme samotný upgrade

`sudo dnf upgrade`

### Ověříme použití ovladačů NVIDIA
`lsmod | grep nvidia`

### Ověříme použití ovladačů Nouveau
`lsmod | grep nouveau`

### Nainstalujeme Nvidia Driver a (pro vývojáře) Cuda Support
Verze dle zjištění výše.

`sudo dnf -y install akmod-nvidia-470xx`

`sudo dnf install xorg-x11-drv-nvidia-470xx-cuda`

### Restart
Ověříme `neofetch` a `nvidia-smi`

### Odebrání NVIDIA
`sudo dnf remove *nvidia*`

## Připojení k NAS

### Mount NAS do PC
Do `/etc/fstab` doplnit:
`//nas-qnap.local/Multimedia /mnt/NAS_Qnap/Multimedia cifs username=admin,password=admin,uid=1000,gid=1000,rw,file_mode=0777,dir_mode=0777,iocharset=utf8,rw 0 0`

### Symlink do finálního adersáře
V CMD spustit příkazy:
```
sudo ln -s /mnt/NAS_Qnap/Multimedia/Cviceni/ ~/Videa/NAS_cviceni
sudo ln -s /mnt/NAS_Qnap/Multimedia/Filmy/ ~/Videa/NAS_filmy
sudo ln -s /mnt/NAS_Qnap/Multimedia/Serialy/ ~/Videa/NAS_serialy
```
