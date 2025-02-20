# 1.1 Hello World

**Objectif**  
Valider que Docker est correctement installé et fonctionnel.

## Commandes

```bash
docker run hello-world
docker container ls -a
```

## Explications

- La commande `docker run hello-world` télécharge l’image `hello-world` depuis Docker Hub si elle n’est pas déjà présente localement, puis exécute un container qui affiche le message "Hello from Docker!" avant de s’arrêter.
- La commande `docker container ls -a` permet de lister tous les containers (exécutés et arrêtés). On y voit notamment l’ID du container, son nom auto-généré, son état (`Exited`), l’image utilisée, etc.
