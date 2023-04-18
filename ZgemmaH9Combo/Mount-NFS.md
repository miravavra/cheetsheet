# Připojení NFS síťového disku
Autofs je náhrada za FSTAB. Umí vytvořit všechny potřebné přípojné body, takže je nemusíte vytvářet.

## Zjistit dostupnost síťového disku
V terminálu spustit příkaz: `showmount -e 10.0.0.20`

## Upravit /etc/auto.network
`/etc/auto.network` je asi zástupcem pro `/etc/auto.master`.

Vložit následující řádek:
`NAS -fstype=nfs,rw,nolock,tcp,nfsvers=3,rsize=8192,wsize=8192,timeo=14,soft 10.0.0.20:/export/cviceni`

- **NAS** je složka v `/mnt/autofs`
- **10.0.0.20:/export/cviceni** je cesta získaná pomocí příkazu "showmount" viz výše

## Nasměrování sdílené složky do požadované složky
Potřebujeme přesměrovat sdílenou složku z "10.0.0.20:/export/cviceni" připojenou do adresáře "/mnt/autofs/NAS" do složky s videi "mnt/hdd/movie/cviceni".

### Symlink
Proto vytvoříme symbolický odkaz:
`ln -s "/media/autofs/NAS" "/media/hdd/movie/cviceni"`

## Restart autofs
`sudo systemctl restart autofs`

nebo

`sudo systemctl stop autofs`

`sudo automount -f -v -d`

Zdroj: https://discourse.osmc.tv/t/mounting-network-shares-with-autofs-alternative-to-fstab/74228
