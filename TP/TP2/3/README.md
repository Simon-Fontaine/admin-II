# 3. Docker Compose

**Objectif**  
Définir une infrastructure multi-container (services, volumes, réseaux) via un fichier YAML (`docker-compose.yml`).

## Exemple simple

Ci-dessous, un exemple qui reprend la configuration de deux containers Nginx partageant un même volume et rattachés à un même réseau user-defined.

```yaml
version: "3"
name: tp2
services:
  web1:
    image: custom-nginx
    ports:
      - "80:80"
    networks:
      - my-net
    volumes:
      - web-volume:/usr/share/nginx/html/
  web2:
    image: custom-nginx
    ports:
      - "81:80"
    volumes:
      - web-volume:/usr/share/nginx/html/
    networks:
      - my-net

volumes:
  web-volume:

networks:
  my-net:
    driver: bridge
    ipam:
      config:
        - subnet: 10.0.1.0/24
```

## Utilisation

1. Sauvegarder ce fichier comme `docker-compose.yaml`.
2. Lancer l’infra :  

   ```bash
   docker-compose up
   ```

3. Vérifier les containers, réseaux, volumes créés :

   ```bash
   docker ps
   docker network ls
   docker volume ls
   ```

4. Tester la publication des ports sur [http://localhost:80](http://localhost:80) et [http://localhost:81](http://localhost:81).
5. Arrêter l’infra :

   ```bash
   docker-compose down
   ```

## Observations

- Tous les objets (containers, réseaux, volumes) sont nommés en fonction du nom du projet `tp2` suivi d’un suffixe.
- La résolution DNS fonctionne entre `web1` et `web2`.
- Les pages partagées via `web-volume` sont identiques pour les deux serveurs.
