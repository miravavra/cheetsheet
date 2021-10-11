# Příkazy pro instalaci SW po reinstalaci PC.
## NVIDIA ovladače
### RPM Fusion Free
`sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm`
### RPM Fusion Non-Free
`sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm`
### Upgrade systému
`sudo dnf upgrade`
### Nvidia Driver a Cuda Support
`sudo dnf -y install kmod-nvidia
sudo dnf install xorg-x11-drv-nvidia-cuda`
### Restart
Ověříme `neofetch` a `nvidia-smi`
## SW
sudo dnf install krusader dropbox nautilus-dropbox keepassxc vlc conky conky-manager gnome-tweak-tool gimp darktable kdenlive veracrypt youtube-dl filezilla
