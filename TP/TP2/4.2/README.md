# 4.2 Exemple du cours théorique

**Objectif**  
Analyser et lancer l’exemple présenté dans la doc. On y trouve :

- un container `web` basé sur Nginx, exposé en local sur le port 3000.
- un container `db` basé sur MySQL, stocké dans un volume.
- un répertoire local ./src monté sur /app pour la partie "web".

## Fichier docker-compose.yaml d’exemple

```yaml
version: "3"
name: app-web-exemple
services:
  web:
    image: nginx
    ports:
      - "3000:80"
    networks:
      - net
    volumes:
      - ./src:/app

  db:
    image: mysql
    volumes:
      - db-data:/var/lib/mysql
    networks:
      - net
    environment:
      - MYSQL_ROOT_PASSWORD=my-secure-pwd

volumes:
  db-data:

networks:
  net:
```

## Étapes

1. Copier ce fichier dans ton répertoire de travail.
2. `docker-compose up -d`
3. Vérifier les containers (via `docker ps`), le volume `db-data`, le réseau `net` et l’accès au port 3000.
4. Observer ce qui se passe si tu mets des fichiers dans `./src`.

## Observations

- Le container `web` peut contacter `db` via le réseau `net`.
- La config MySQL est minimale : la variable d’environnement `MYSQL_ROOT_PASSWORD` définit le mot de passe root.
- Rien n’est fait pour que l’appli `web` interagisse réellement avec `db`, mais l’infrastructure réseau est bien en place.
