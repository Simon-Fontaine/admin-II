# 3.1 Figer un container

**Objectif**  
Montrer comment figer un container (avec ses modifications) en créant une nouvelle image via `docker commit`.

## Étapes

1. **Modifier le container en direct**  

```bash
docker exec -it mon-serveur-web bash
apt update && apt install -y nano net-tools
# Modification de /usr/share/nginx/html/index.html ...
```

2. **Commiter l’image**  

```bash
docker container commit mon-serveur-web mon-image-nginx-custom
docker run -p 80:80 --name serveur-custom mon-image-nginx-custom
```

## Observations

- Toutes les modifications faites au container (installation de paquets, fichiers modifiés) sont figées dans l’image `mon-image-nginx-custom`.
- Au redémarrage d’un container basé sur cette nouvelle image, on retrouve la même configuration.
