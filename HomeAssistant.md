# Instalace Home Assistant jako VM do Proxmoxu
## Instalační image Home Assistantu
- ze stránky https://www.home-assistant.io/installation/alternative zkopírovat odkaz na image **KVM/Proxmox (.qcow2)**
- stáhnout image pomocí `wget` přímo do konzole Proxmoxu
- rozbalit image v konzoli Proxmoxu příkazem `unxz haos_ova-xx.x.qcow2.xz`.

## Vytvořit VM v Proxmoxu

### Záložka General
- doplnit Name např. "HomeAssistant"
- zaškrtnout "Start at boot"

### Záložka OS
- zaškrtnout "Do not use any media"

### Záložka System
- Machine vybrat "q35"
- BIOS vybrat "UEFI"
- EFI Storage vybrat "local-lvm"
- zaškrtnout "Qemu Agent"

### Záložka CPU
- zvolit Cores "2"

### Záložka Memory
- ponechat "2048 MB"

## Import staženého image do VM
Importoavat stažený a rozbalený image do vytvořeného VM příkazem:

`qm importdisk 100 haos_ova-12.1.qcow2 local-lvm --format qcow2`

## Úprava VM před spuštěním

### Přejdeme na záložku Hardware

### Odstranění HDD
Odstranit původní HDD vzniklý při instalaci. Vybrat `Hard Disk (scsi0)` a stisknout tlačítko `Detach`.
Odstranit původní `Unused disk 1` stiskem tlačítka `Remove`.

### Aktivace importovaného image
Klikneme na `Unused disk 0` a stiskneme tlačítko `Add`.
V případě, že disk je SSD ještě zaškrtneme `Discard`.

### Přejdeme na záložku Options

### Upravíme Boot Order
Zaškrtneme `Enabled` u našeho disku, ostatní volby naopak odškrtneme.
Můžeme i změnit pořadí a náš disk přesunout nahoru.

## Spuštění VM
Spustíme VM tlačítkem `Start`.
Přepneme se do konzole VM na záložce `>_ Console`.
Uvidíme connecting... a boot Home Assistenta.

> Pokud uvidíme `Shell>` prompt zadáme "exit" a nastavíme BIOS našeho VM.

Projdeme k nastavení secure bootu a volbu odškrtneme:

`Device Manager > Secure Boot Configuration > Attempt Secure Boot []`

Volbu uložíme `F10` a vrátíme se do hlavní nabídky.
Nastavení ukončíme volbou `Reset`.

**Pokud uvidíme v konzoli logo "Home Assistantu" máme spuštěno a můžeme pokračovat v prohlížeči na IP adrese kterou vidíme v konzoli s portem 8123.**

Zdroj: https://www.youtube.com/watch?v=arKoIPQ5_YU&t=85s
