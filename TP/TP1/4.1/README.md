# 4.1 Démarrer un serveur Web Apache

**Objectif**  
Mettre en pratique la construction d’une image pour un serveur Apache, avec VirtualHost sur 80 et 8080.

## Fichiers

- **Dockerfile**
- **httpd.conf** / **httpd-vhosts.conf**
- **site-port80/** et **site-port8080/** : dossiers contenant les index.html

## Commandes

```bash
cd TP/TP1/4.1
docker build -t apache-multi-vhost .
docker run -d --name apache-multi -p 80:80 -p 8080:8080 apache-multi-vhost
```

## Observations

- Le container écoute sur le port 80 et 8080 (cf. `EXPOSE 80` et `EXPOSE 8080` dans le Dockerfile).
- Dans la config de VirtualHost, `site-port80` répond sur 80 et `site-port8080` sur 8080.
- On peut personnaliser chaque index.html selon le port souhaité.
