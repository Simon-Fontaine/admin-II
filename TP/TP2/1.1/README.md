# 1.1 Bind Mount

**Objectif**  
Monter un répertoire local de l’hôte dans un container Docker pour éditer les fichiers en temps réel.

## Pré-requis

- Une image de base, par exemple `custom-nginx`, qui inclut `nano`, `iproute2` et `iputils-ping` (ou selon le Dockerfile que tu auras préparé).

## Étapes

1. Créer un répertoire local `html` avec un fichier `index.html`.
2. Lancer un container Nginx en publiant le port 80 et en liant le répertoire local `html` à `/usr/share/nginx/html` dans le container.

```bash
cd TP/TP2/1.1

# Exemple de commande (à adapter au chemin exact de ton projet)
docker run -p 80:80 \
  --name web \
  --mount type=bind,source="$(pwd)"/html,target=/usr/share/nginx/html \
  custom-nginx
```

3. Vérifier sur [http://localhost:80](http://localhost:80) que le container sert bien le fichier `index.html`.
4. Modifier localement `index.html` et rafraîchir la page pour observer la prise en compte immédiate des changements.

## Observations

- Le Bind Mount rend les modifications instantanées entre l’hôte et le container.
- Si on modifie un fichier de configuration (ex. `nginx.conf`) via Bind Mount, il faut redémarrer le service ou le container pour que la modification soit prise en compte.
