# Podman (Docker)

## Základní příkazy

### Stažení image
podman pull <image>

### Spustit kontejner z image s procesem
podman run -ti <image> bash

#### Parametry
-ti interaktivní proces s přístupným terminálem

## Vlastní image

### Tvorba image

#### Zmrazení běžícího kontejneru a vytvoření obrazu
podman commit <ID_kontejneru>

#### Pojmenování image
podman tag <ID_kontejneru> <název>
  
### Spuštění image
podman run -p 8080:80 <název> httpd -D FOREGROUND

#### Parametry
-p 8080:80 namapuje port uvnitř kontejneru (80) vně kontejneru (8080)
  
### Změna mapování portů
https://365tipu.cz/2025/04/30/tip2961-jak-zmenit-mapovani-portu-ci-ip-adresu-na-ktere-bezi-kontejner-v-dockeru/

#### Postup změnou parametrů při spuštění
Musí se zastavit kontejner `docker stop`, poté ho odstranit `docker rm` a pak znovu spustit `docker run` s novým mapováním. 

> Což je mimochodem dost dobrý důvod k tomu, abyste si schovávali jak jste vlastně vytvořili kontejner na počátku.
> Nebo je nespouštěli z příkazové řádky, ale s pomocí YAML souborů (případně k tomu využívali něco jako Portainer).

#### Postup vytvořením nové image
Vytvořit nové image viz `docker commit` výše a poté použít toto nové image pro spuštění s jinými parametry – v image se totiž uloží vše, kompletní stav kontejneru.

#### Postup změnou konfiguračních souborů (hardcore)
Pro pokročilejší je tu možnost najít konfigurační soubor vašeho kontejneru – je v JSON formátu a bude v /var/cocker/contains/_ID_/ (kde _ID_ je ID vašeho kontejneru, dlouho šestnáctkové číslo získatelné třeba přes docker inspect.

Konfigurační soubor ale můžete měnit jen v okamžiku kdy zastavíte kontejner `docker stop` a navíc zastavíte i docker jako takový (tedy například `systemctl stop docker`).

Pak už můžete v hostconfig.json měnit PortBindings a ExposedPorts. 

Pak už jen spustit docker jako takový `systemctl start docker` a pak spustit váš kontejner `docker start`. Jestli máte správně nové mapování pak ověřit přes `docker ps`.

