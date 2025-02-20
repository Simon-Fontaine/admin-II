# 2.1 Interagir avec un container

**Objectif**  
Découvrir comment exécuter un shell interactif dans un container.

## Commandes

```bash
docker run -it ubuntu bash
```

## Explications

- Les options :
  - `-i` : pour maintenir l’entrée standard ouverte (mode interactif),
  - `-t` : pour allouer un pseudo-TTY (pour avoir un terminal).
- Dans ce cas, la "commande unique" exécutée par le container est `bash`.  
- Une fois dans le container, on peut faire des `apt update` ou `apt install` comme si c’était une mini-distribution Ubuntu.  
- Le processus principal est `bash`. Pour lister tous les processus, on peut utiliser `ps aux` ou `ps -ef` et observer qu’il n’y a pratiquement que `bash`.
- On est connecté en tant que `root` dans le container.
- Par défaut, le container a accès à Internet grâce aux mécanismes réseaux de Docker (NAT). Le résolveur est souvent la passerelle Docker ou un DNS configuré par Docker. On peut le vérifier dans `/etc/resolv.conf`.
