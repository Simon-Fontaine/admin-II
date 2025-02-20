# 2.2 Réseaux définis par l’utilisateur

**Objectif**  
Créer et utiliser un réseau Docker personnalisé pour bénéficier d’une isolation, d’une configuration IP, et de la résolution DNS par nom de container.

## Commandes

```bash
# Création d'un réseau "my-net"
docker network create my-net

# Vérification
docker network ls
docker network inspect my-net
```

- Le `docker network inspect my-net` donne notamment le subnet IP attribué.

### Lancement de containers sur ce réseau

```bash
docker run --net=my-net --name=web-my-net custom-nginx
```

- Vérifier si ce container peut joindre ceux lancés sur le réseau `bridge` par défaut (spoiler : non, sauf configuration spécifique).
- Vérifier l’accès à Internet.

### Résolution de nom interne

- Sur un second container lancé avec `--net=my-net`, un `ping web-my-net` devrait fonctionner.
- Dans un réseau user-defined (bridge), Docker gère la résolution DNS par nom de container.

### Avantages / Inconvénients

- **Avantages** : Meilleure isolation, résolution de noms automatique, possibilité de configurer le subnet IP, etc.
- **Inconvénients** : Configuration supplémentaire (à faire/maintenir).
