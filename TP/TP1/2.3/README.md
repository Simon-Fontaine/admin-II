# 2.3 Faire tourner un service

**Objectif**  
Exécuter un service dans un container (ici, un serveur web Nginx) et le rendre accessible depuis la machine hôte.

## Commandes

```bash
# Lancement simple
docker run --name=mon-serveur-web nginx

# Arrêt
docker stop mon-serveur-web

# Relance avec publication de port
docker run -p 80:80 --name mon-serveur-web nginx
```

## Explications

- `docker run -p 80:80` publie le port 80 du container vers le port 80 de l’hôte.  
- Avant la publication de port, le container écoutait bien sur 80 **à l’intérieur** mais n’était pas accessible depuis l’extérieur.  
- Via `http://localhost:80`, on peut alors accéder à la page d’accueil Nginx.
