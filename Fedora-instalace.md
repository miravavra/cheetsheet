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
`sudo dnf install krusader dropbox nautilus-dropbox keepassxc vlc gnome-tweak-tool gimp darktable kdenlive yt-dlp filezilla google-chrome-stable lpf-spotify-client`

### Instalovat multimediální knihovny
`sudo dnf group install Multimedia`

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
