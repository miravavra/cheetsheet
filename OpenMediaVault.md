# Open Media Vault
## Nefunkční síť po instalaci
Spustit `omv-firstaid` v příkazové řádce OMV a nastavit síť
## Rozdělení disku
OMV nepodporuje sdílení dat na systémovém disku.
Pokud nechceme přidávat další disk, je třeba samostatně (např. pomocí rescue live distribuce na flashce) vytvořit oddíl pro data.
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
