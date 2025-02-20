# 1.3 Les images

**Objectif**  
Lister les images Docker locales et comprendre comment les gérer (supprimer, etc.).

## Commandes

```bash
docker image ls
docker rmi <image_id>
```

## Explications

- `docker image ls` permet de lister toutes les images présentes localement, avec leur taille, leur tag, etc.
- Les images inutilisées occupent de l’espace, il est donc bon de nettoyer régulièrement avec `docker rmi <image_id>` pour supprimer celles qui ne servent plus.
- Lorsqu’une image n’existe pas localement, Docker la télécharge depuis un registre (par défaut le Docker Hub).
