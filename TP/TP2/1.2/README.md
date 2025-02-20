# 1.2 Volume Docker

**Objectif**  
Utiliser un Volume Docker pour stocker et partager des données de manière persistante entre containers, sans nécessiter un répertoire de l’hôte.

## Commandes principales

```bash
# Lancement d'un container Nginx avec un volume nommé "mon-volume"
docker run -p 80:80 \
  --name web-volume \
  --mount source=mon-volume,target=/usr/share/nginx/html \
  custom-nginx
```

## Étapes

1. Vérifier la création du volume :

   ```bash
   docker volume inspect mon-volume
   ```

2. Ouvrir un shell dans le container et éditer `/usr/share/nginx/html/index.html` :

   ```bash
   docker exec -it web-volume bash
   nano /usr/share/nginx/html/index.html
   ```

3. Vérifier dans le navigateur que la modification est effective.
4. Lancer un second container **sur le même volume** (par exemple sur le port 81) :

   ```bash
   docker run -p 81:80 \
     --name web-volume2 \
     --mount source=mon-volume,target=/usr/share/nginx/html \
     custom-nginx
   ```

5. Constater que les deux containers partagent la même page.

## Comparaison Bind Mount / Volume Docker

- **Bind Mount** : partage entre hôte et container (développement local, édition en direct).
- **Volume Docker** : partage de données entre containers, administré par Docker (pas forcément accessible directement depuis l’hôte).
- Les volumes sont recommandés pour les déploiements en production.
