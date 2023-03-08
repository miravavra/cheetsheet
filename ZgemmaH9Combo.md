# Instalace multibootu a image OpenATV na linuxový satelitní přijímač Zgemma H9 Combo

## 0. Nejdříve do nového boxu nahrát RECOVERY SOFT:
Recovery soft se instaluje jako první a jen jednou. Přez něj se instalují zálohy a vytvoří i multiboot.

### Instalace RECOVERY softu
- **Rozpakovat** v PC stáhnutý soubor Recovery softu.
- Rozbalené soubory **nakopírovat na USB klíč** naformátovaný na FAT32.
- **Vypnout přijímač** zadním vypínačem.
- **Stisknout a držet** stisknuté tlačítko **RESET** na zadním panelu přijímače **a zapnout zadní vypínač.**
- Tlačítko **RESET držet dokud** se na displeji přijímače **nezobrazí nápis FLASH**. V tomto okamžiku **tlačítko RESET uvolnit** a počkat na ukončení instalace.
- Po nainstalování se zobrazí isnstalační MENU.

## Postup instalace image Enigma2

- **Vypnout přijímač** zadním vypínačem.
- **Nakopírovat** zálohu E2, nebo čistý image E2 tak jak ho stáhneme, teda v zip. formátu **na USB** a USB zasuňte do USB portu prijímača Zgemma.
- **Stiskněte a držte tlačítko OK na dálkovém ovladači a zapněte přijímač zadním vypínačem.** Na displeji se **zobrazí nápis rCUY**, rozsvítí se červená LED a následně se po chvílce zobrazí na obrazovce TV menu pro inštalaci.
- V tomto menu zvolze položku **Bootmenu**.
- Vyberte položku **Flash local image**, tam se zobrazí vložené USB. Z něho vyberete vaší zálohu, nebo čistý image E2 a potvrdíte ho tlačítkem OK na dálkovém ovladači.
- **Vyberiete partition**, kam se záloha naflashuje (Linux1 až Linux4) a potvrďte tlačítkem OK na dálkovém ovladači. Následně se spustí flash.
- Flashování se ukončí nápisem Flashing completed.
- Z boot menu si vyberete Boot1 a nabootuje nainstalovaná záloha.

## Instalace Softcam-feed
OpenATV nemá v základu možost instalovat softcamy takže je nutné nejdříve přidat zdroj pro jejich stahování.

### Stáhnout a nainstalovat Softcam-feed
Nejnovější Softcam-feed stáhnout z https://www.mysatbox.tv/2016/08/softcams-openatv-softcam-feed-updated.html.
Aktuálnost pro jistotu zkontrolovat na AB-FORUM například ve vlákně http://www.ab-forum.info/viewtopic.php?f=370&t=74281&start=160.
Stažený IPK soubor nahrát na USB flašku a nainstalovat do satelitu.

### Nainstalovat Oscam
Mezi zdroji doplňků už nyní máme možnost vybrat Softcamy.
Takže vybereme (Oscam-stable) a nainstalujeme.

Zdroj: https://digitalne.ellano.sk/recenzie-a-testy-2/digitalne-prijimace/uhd-4k-prijimace/item/preview-zgemma-h9-combo
