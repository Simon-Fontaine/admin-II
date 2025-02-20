# 2.2 Inspecter un container

**Objectif**  
Apprendre à extraire des informations détaillées d’un container (IP, ports exposés, etc.).

## Commandes

```bash
docker inspect <nom_container>
docker stop <nom_container>
```

## Explications

- `docker inspect` permet d’obtenir un JSON avec de nombreuses informations, notamment :
  - Adresse IP du container
  - Ports mappés
  - Config réseau
  - Points de montage
  - Commande exécutée
- Pour arrêter le container, deux possibilités :
  1. `docker stop <nom_container>` depuis un autre terminal,
  2. Taper `exit` dans le container, ce qui termine le processus principal (`bash`) et donc stoppe le container.
