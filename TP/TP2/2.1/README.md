# 2.1 Réseau par défaut (bridge)

**Objectif**  
Découvrir la configuration réseau par défaut attribuée aux containers Docker.

## Explications / Commandes

- Par défaut, chaque container est sur le réseau `bridge`.
- Vérifier avec `docker inspect <container_name>` ou `docker exec -it <container_name> bash` + `ip addr` (ou `ifconfig`).

### Questions

1. Quelles sont les interfaces réseau et adresses IP de vos containers ?
2. Les containers peuvent-ils se joindre via `ping` ?
3. Ont-ils accès à Internet ?

### Avantages / Inconvénients du `bridge` par défaut

- **Avantages** : Pas besoin de configurer un réseau ; la connectivité internet fonctionne souvent d’emblée.
- **Inconvénients** : Les containers sur ce réseau commun peuvent communiquer entre eux, ce qui peut poser des soucis d’isolation. La résolution DNS par nom de container n’est **pas** activée par défaut (ping par IP seulement).
