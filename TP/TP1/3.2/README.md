# 3.2 Créer une image sur base d’un Dockerfile

**Objectif**  
Construire une image personnalisée via un Dockerfile, plutôt que de figer un container à la main.

## Fichiers

- **Dockerfile** : décrit les instructions de construction de l’image
- **index.html** : page d’accueil personnalisée copiée dans Nginx

## Construction de l’image

```bash
cd TP/TP1/3
docker build -t mon-nginx-image .
```

## Lancement du container

```bash
docker run -p 80:80 --name mon-nginx mon-nginx-image
```

## Observations

- L’image est basée sur `nginx:latest`, on y installe `nano` et `net-tools`, puis on copie `index.html` vers `/usr/share/nginx/html`.
- Au démarrage du container, on peut accéder à la page sur [http://localhost:80](http://localhost:80).
