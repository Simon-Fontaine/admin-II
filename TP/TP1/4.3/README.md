# 4.3 Container avec script Python

**Objectif**  
Créer un container qui exécute un simple script Python pour afficher l’heure, puis s’arrête.

## Fichiers

- **Dockerfile**
- **heure.py**

## Commandes

```bash
cd TP/TP1/4.3
docker build -t python-time .
docker run --name mon-python-time python-time
```

## Résultat

Exemple d’output :

```bash
Nous sommes le 2025-02-19 à 15:29:28.384641
```
