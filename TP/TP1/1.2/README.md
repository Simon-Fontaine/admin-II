# 1.2 Observer un container

**Objectif**  
Découvrir comment lister et observer les containers actifs ou arrêtés.

## Commandes

```bash
docker container ls -a
```

## Explications

- Cette commande affiche toutes les informations de base (ID, nom, état, image, commande lancée, etc.) à propos des containers.
- On peut ainsi répondre aux questions :  
  1. Quel est l’ID du container ?  
  2. Quel est son nom ?  
  3. Son état (ex. `Exited`, `Up`, …) ?  
  4. Quelle est l’image utilisée (et sa provenance) ?  
  5. Quelle commande a été exécutée dans ce container ?  
- Sur Docker Desktop ou Docker Engine (avec interface), on peut retrouver ces mêmes informations via l’interface graphique.
