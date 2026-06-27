# Crown & Quest — Recherche sur l'architecture backend

## 1. Introduction

Dans le cadre du projet *Crown & Quest*, une simulation médiévale immersive en réalité virtuelle, le backend joue un rôle central dans la gestion de la persistance, de la synchronisation multijoueur, de la sécurité et de la cohérence de l’expérience.

Contrairement à un jeu vidéo classique, une simulation VR implique une forte notion d’incarnation, de temps réel et de crédibilité du monde. Le backend doit donc être conçu comme un **système fiable et autoritatif**, tout en restant compatible avec les contraintes d’un projet étudiant sans budget.

Ce document présente une étude des architectures backend possibles, les choix technologiques envisagés, ainsi que le cheminement retenu pour aboutir à une solution optimale, réaliste et évolutive.

---

## 2. Contraintes et objectifs du backend

### 2.1 Contraintes du projet
- Budget nul (aucune solution payante)
- Équipe étudiante avec un temps limité
- Projet évolutif sur plusieurs semestres
- Simulation VR nécessitant du temps réel

### 2.2 Objectifs fonctionnels
Le backend doit permettre :
- La gestion des comptes et de l’identité des joueurs
- La persistance des données (progression, inventaire, paramètres)
- La gestion de sessions multijoueur
- La synchronisation d’événements en temps réel
- La protection contre les incohérences et abus côté client
- La traçabilité et l’observation du système

---

## 3. Analyse des architectures backend existantes

### 3.1 Monolithe classique

Un backend monolithique regroupe l’ensemble des fonctionnalités dans une seule application sans séparation logique claire.

**Avantages :**
- Mise en place rapide
- Facilité de déploiement
- Courbe d’apprentissage faible

**Inconvénients :**
- Couplage fort entre les fonctionnalités
- Difficulté de maintenance à long terme
- Évolutivité limitée

Cette approche est adaptée aux prototypes simples mais devient rapidement problématique pour un projet évolutif.

---

### 3.2 Microservices

L’architecture microservices consiste à découper le backend en plusieurs services indépendants communiquant entre eux via le réseau.

**Avantages :**
- Scalabilité élevée
- Séparation claire des responsabilités
- Architecture industrielle

**Inconvénients :**
- Complexité élevée (réseau, sécurité, monitoring)
- Coût de mise en place important
- Peu adaptée à une équipe étudiante sans DevOps dédié

Cette architecture est jugée **sur-dimensionnée** pour le contexte de Crown & Quest.

---

### 3.3 Modular Monolith (approche retenue)

Le **modular monolith** combine les avantages du monolithe et des microservices.  
Il s’agit d’une seule application déployée, mais découpée en modules métiers strictement séparés.

**Avantages :**
- Déploiement simple
- Organisation claire du code
- Évolutivité progressive
- Possibilité d’extraire des modules en services plus tard

**Inconvénients :**
- Nécessite une discipline architecturale dès le départ

Cette approche offre le meilleur compromis entre **qualité logicielle**, **faisabilité** et **maintenabilité**.

---

## 4. Choix architectural global

### 4.1 Architecture retenue

Le backend de Crown & Quest repose sur :
- Une API REST centrale
- Un découpage en modules métiers indépendants
- Un système de communication temps réel (WebSocket)
- Une base de données relationnelle
- Une couche de persistance et de validation serveur

Cette architecture permet de garantir la cohérence des données tout en offrant une base solide pour le multijoueur et la simulation VR.

---

## 5. Découpage fonctionnel du backend

Les principaux modules identifiés sont :

- **Identity** : authentification, autorisation, rôles
- **Player** : profil joueur, paramètres, préférences
- **Progression** : niveau, statistiques, évolution
- **Inventory** : gestion des objets et équipements
- **World** : état du monde, fort, bâtiments
- **Session** : lobbies, parties, présence des joueurs
- **Telemetry** : logs, événements, statistiques
- **Admin** : supervision et outils internes

Chaque module possède :
- ses entités métier
- ses règles de gestion
- ses cas d’usage
- ses interfaces d’accès

---

## 6. Gestion du temps réel et de la VR

### 6.1 Contraintes spécifiques à la VR
La VR impose :
- une faible latence
- une cohérence forte entre joueurs
- une validation serveur des actions importantes

### 6.2 Modèle serveur autoritatif léger

Le backend adopte un modèle **serveur autoritatif sur les événements** :
- Le client VR gère le rendu et la physique locale
- Le serveur valide les actions critiques (dégâts, interactions, progression)
- Le serveur synchronise l’état logique du monde

Ce modèle permet :
- de limiter la triche
- de préserver les performances
- de rester réaliste techniquement

---

## 7. Sécurité et intégrité des données

Les principes suivants sont retenus :
- Le serveur est la source de vérité
- Aucune modification critique n’est acceptée sans validation
- Les entrées client sont systématiquement vérifiées
- Les actions sensibles sont journalisées

Même sans budget, ces principes permettent d’assurer un niveau de sécurité crédible pour un projet académique.

---

## 8. Évolutivité et pérennité

L’architecture retenue permet :
- l’ajout progressif de fonctionnalités
- l’augmentation du nombre de joueurs
- l’intégration future de modules avancés (IA, IoT)
- une éventuelle transition vers des services séparés

Le backend est conçu comme un **socle évolutif**, et non comme une solution figée.

---

## 9. Conclusion

Ce travail de recherche a permis d’identifier une architecture backend adaptée aux contraintes et aux ambitions de Crown & Quest.

Le choix d’un **modular monolith**, associé à une gestion événementielle et temps réel, offre une solution :
- réaliste
- robuste
- pédagogique
- compatible avec une simulation VR immersive

Ce socle backend constitue une base solide pour les phases de développement ultérieures du projet.
