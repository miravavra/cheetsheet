# Základní příkazy

  ### Stažení image
  podman pull <image>

  ### Spustit kontejner z image s procesem
  podman run -ti <image> bash
  
  #### Parametry
  -ti interaktivní proces s přístupným terminálem

# Vlastní image
  ## Tvorba image

  ### Zmrazení běžícího kontejneru a vytvoření obrazu
  podman commit <ID_kontejneru>

  ### Pojmenování image
  podman tag <ID_kontejneru> <název>
  
  ## Spuštění image
  podman run -p 8080:80 <název> httpd -D FOREGROUND
  #### Parametry
  -p 8080:80 namapuje port uvnitř kontejneru (80) vně kontejneru (8080)
