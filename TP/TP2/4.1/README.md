# 4.1 Mise en application simple

**Objectif**  
Définir une infrastructure qui utilise plusieurs volumes et réseaux, et valider son bon fonctionnement.

## Exigences

- 2 volumes : Volume1 et Volume2
- 2 réseaux : Réseau1 et Réseau2
- 3 containers : ContainerA, ContainerB, ContainerC

Détails :

- **ContainerA**
  - Accède à Volume1 sur /app
  - Accède à un répertoire local de l’hôte monté sur /src
  - Appartient à Réseau1

- **ContainerB**
  - Accède à Volume1 sur /app1 et Volume2 sur /app2
  - Appartient à Réseau1 et Réseau2

- **ContainerC**
  - Accède à Volume2 sur /app
  - Appartient à Réseau2

## Exemple de docker-compose

Voici un squelette minimaliste :

```yaml
version: "3"
services:
  containerA:
    image: debian:latest
    volumes:
      - volume1:/app
      - ./mon-src:/src
    networks:
      - reseau1

  containerB:
    image: debian:latest
    volumes:
      - volume1:/app1
      - volume2:/app2
    networks:
      - reseau1
      - reseau2

  containerC:
    image: debian:latest
    volumes:
      - volume2:/app
    networks:
      - reseau2

volumes:
  volume1:
  volume2:

networks:
  reseau1:
  reseau2:
```

## Validation

- Lancer l’infrastructure :  

  ```bash
  docker-compose up -d
  ```

- Vérifier quels containers sont connectés à quels réseaux via `docker network inspect`.
- Vérifier les volumes créés via `docker volume ls` et `docker volume inspect`.
- Tester depuis chaque container que les répertoires montés sont bien disponibles.
- Illustrer par des screenshots la bonne configuration.
