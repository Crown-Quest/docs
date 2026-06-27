# Conventions

Ce document décrit les règles et conventions utilisées sur ce projet.


## Commits Git

Nous utilisons les commits conventionnels :
- https://www.conventionalcommits.org/fr/v1.0.0/

Types autorisés :
- feat
- doc
- fix
- refacto
- style

Scopes autorisés :
- project-management
- research
- architecture
- meetings
- VR
- IoT
- IA
- other

> exemple :
> doc(project-management): Created convention.md

## Branches

`<TYPE>/<NUMÉRO D'ISSUE>-<NOM DE LA FEATURE>_<SUFFIXE>`

> Tout en minuscules.

- TYPE : voir les types autorisés des commits Git
- NUMÉRO D'ISSUE : numéro de l'issue (Kanban)
- NOM DE LA FEATURE : nom de l'issue Kanban
- SUFFIXE : optionnel :
    un suffixe peut être ajouté si plusieurs branches sont créées pour la même feature.

> exemple :
> doc/1-convention_geoffrey

## Gestion du dépôt

- Main protégée
- Pour pousser sur la branche main, une feature doit être créée et une merge request
(pull request) doit être ouverte.
- Une pull request peut être fusionnée dans main si les conditions suivantes sont remplies :
    - Aucun pipeline/job de CI n'a échoué
    - Il y a au moins 1 review d'approbation

L'approbation d'une review ne doit pas être sous-estimée :
    - Les différentes lignes doivent être lues par le relecteur.
    - La definition of done doit être respectée.
