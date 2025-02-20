# 4.2 Lancer un résolveur Bind dans un container Docker

**Objectif**  
Utiliser l’image `sameersbn/bind` (ou autre) pour monter un container faisant office de résolveur DNS.

## Commandes

```bash
# Lancement
docker run -d --name=mon-bind -p 53:53/tcp -p 53:53/udp sameersbn/bind

# Test
nslookup www.google.com 127.0.0.1
```

## Observations

- On doit publier à la fois le port TCP 53 et UDP 53.
- `nslookup` (ou `dig`) permet de tester la résolution DNS en interrogeant l’adresse 127.0.0.1.
- Pour configurer Bind en tant que forwarder DNS (par ex. vers 8.8.8.8), il faut modifier ses fichiers de conf (non montrés ici).
- Une capture Wireshark peut confirmer que les requêtes DNS sont bien forwardées.
