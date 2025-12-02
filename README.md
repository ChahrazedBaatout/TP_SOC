# TP_SOC_Linux_ENSEA_

## 1.1 Préparation de la carte SD


---

## 1.2 Démarrage
Après insertion de la carte SD et mise sous tension de la carte SoC, le système Linux embarqué démarre correctement.

---

## 1.3. Connexion au SoC via liaison série

Après avoir branché la carte VEEK-MT2S au PC à l’aide du port mini-USB (UART-to-USB), il est possible de détecter le port série correspondant grâce à :
```bash
dmesg | grep tty 
```

Puis, sous Linux, on utilise minicom :
```bash
sudo minicom -s
```
![Configuration Minicom](configuration.png)

Après reboot du SoC, on observe toute la séquence de démarrage Linux jusqu’à l’apparition du login :
![Login](login.png)

## 1.4. Configuration réseau du SoC

L’objectif est d’assigner une adresse IP statique au SoC pour permettre une connexion SSH depuis le PC.
Fichier `/etc/network/interfaces` modifié avec vim :
![editionFichierInterfaces](editionFichierInterfaces.png)
Le réseau est reconfigué 
![ipconfig](ipconfig.png)

Pour verfier le bon focntionnement, on va pinger la carte avec le PC :
![ping](ping.png)
