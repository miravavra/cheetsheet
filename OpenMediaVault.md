# Open Media Vault

## Nefunkční síť po instalaci
Spustit `omv-firstaid` v příkazové řádce OMV a nastavit síť

## Použití jediného disku pros systém i data
OMV nepodporuje sdílení dat na systémovém disku.
Pokud nechceme přidávat další disk můžeme využít jednu ze dvou následujících možností.

### Plugin sharerootfs
Tento plugin umožní nasdílet pro data nevyužitý prostor na systémovém disku.

### Rozdělení disku
Můžeme také "postaru" rozdělit disk a vytvořit tak samostatný oddíl pro data (např. pomocí rescue live distribuce na flashce).

## Vypnutí uspání po zavření víka notebooku
Upravíme `/etc/systemd/logind.conf` tak, že odkomentujeme (smažeme znak "#" na začátku řádku) následující řádky:
```
HandleSuspendKey=ignore
HandleLidSwitch=ignore
HandleLidSwitchExternalPower=ignore
HandleLidSwitchDocked=ignore
```
Úpravy aktivujeme příkazem
`sudo systemctl restart systemd-logind`.

## Nastavení po instalaci

### System | General Settings
`Auto logout` nastavit dle potřeb (1 hod.)

### System | Date & Time
`Time zone` Europe/Prague

### Nainstalovat omv-extras
Instalací tohoto rozšíření [wiki.omv-extras.org](https://wiki.omv-extras.org) získáme přístup k instalaci Dockeru a Portaineru.

Na stránce najdeme příkaz pro instalaci (provádíme jako root):

`wget -O - https://github.com/OpenMediaVault-Plugin-Developers/packages/raw/master/install | bash`
