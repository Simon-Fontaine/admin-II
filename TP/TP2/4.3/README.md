# 4.3 Exemple du tutoriel Docker (Docker Python + Redis)

**Objectif**  
Suivre le [tutoriel officiel Docker Compose](https://docs.docker.com/compose/gettingstarted/) qui met en place une app Python + Redis.

## Étapes

1. Cloner ou reproduire les fichiers du tutoriel (fichiers .py, Dockerfile, docker-compose.yaml).
2. `docker-compose up -d`
3. Visiter l’application (port défini dans le docker-compose).
4. Observer comment Redis est utilisé comme cache.

### Questions

- Sur quelle base d’images Python le container est-il construit ?
- Comment se fait la communication entre le container Python et Redis ?
- Qu’avez-vous découvert de nouveau ?

## Conclusion

- Vous aurez une infrastructure de containers qui communiquent via un réseau interne.
- Possibilité de pousser plus loin en lisant la doc Docker ou le repo [awesome-compose](https://github.com/docker/awesome-compose).
