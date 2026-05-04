# Technologies

## 1. Introduction

Dans le cadre du projet *Crown & Quest*, simulation médiévale immersive en réalité virtuelle, le choix des technologies constitue un enjeu fondamental. Ces choix conditionnent la qualité de l'expérience utilisateur, la faisabilité du projet dans le temps imparti, et la cohérence de l'ensemble du système.

Ce document présente les technologies retenues, les alternatives étudiées, ainsi que la justification de chaque choix en regard des contraintes du projet.

---

## 2. Contraintes et critères de sélection

### 2.1 Contraintes du projet
- Budget nul (solutions open source ou gratuites pour usage académique)
- Équipe étudiante, temps de développement limité
- Simulation VR immersive avec retour haptique
- Compatibilité avec le matériel disponible

### 2.2 Critères retenus
- Maturité et stabilité de la technologie
- Qualité de la documentation et de la communauté
- Compatibilité avec les casques VR cibles
- Facilité d'intégration entre les différentes briques

---

## 3. Moteur de jeu — Unity

### 3.1 Présentation

**Unity** (Unity Technologies) est un moteur de jeu multiplateforme largement utilisé dans l'industrie du jeu vidéo et de la simulation XR. Il supporte nativement le développement VR via le package **XR Interaction Toolkit** et intègre des connecteurs pour tous les principaux casques du marché (Meta Quest, HTC Vive, Valve Index, etc.).

- **Langage** : C#
- **Rendu** : Universal Render Pipeline (URP) ou Built-in
- **Version recommandée** : Unity 6 LTS

### 3.2 Alternatives étudiées

| Moteur | Points forts | Raisons d'exclusion |
|--------|-------------|---------------------|
| **Unreal Engine 5** | Rendu photoréaliste, Blueprints | Courbe d'apprentissage élevée en C++, plus lourd à déployer |
| **Godot 4** | Open source, léger | Support VR encore limité et moins mature |
| **Babylon.js** | WebXR natif | Inadapté à une simulation VR riche et haptique |

### 3.3 Justification du choix

Unity est retenu pour les raisons suivantes :

- **Écosystème VR mature** : XR Interaction Toolkit, support natif OpenXR
- **Compatibilité haptique** : SDK bHaptics officiellement supporté sur Unity
- **Productivité** : éditeur visuel, Asset Store, prototypage rapide
- **Communauté** : documentation abondante, nombreux tutoriels et exemples VR
- **Licence académique** : Unity Student / Unity Personal gratuit pour projets sans revenus

---

## 4. Retour haptique - SDK Custom

### 4.1 Alternatives étudiées

| Solution | Points forts | Raisons d'exclusion |
|----------|-------------|---------------------|
| **OWO Suit** | Retour haptique musculaire (électrostimulation) | API moins mature, coût élevé, contraintes de sécurité |
| **Subpac** | Retour haptique basse fréquence (basses) | Pas d'API de développement, usage passif |
| **HaptX Gloves** | Très haute précision tactile | Coût prohibitif (usage industriel) |
| **Haptic solution maison** | Personnalisable | Développement matériel hors périmètre du projet |
| **bHaptics** | SDK complet | Coûteux et dépendence matérielle |

### 4.2 Choix

**SDK custom:**

  - **Maîtrise** de la chaîne de développement
  - **Liberté** de choix dans le matériel
  - **Coûts réduits**
  - **Sujet d'apprentissage**


!!! conclusion

    Nous avons décidé de créer nos gilets à la main et donc notre sdk de communication également.

---

## 6. Autres technologies associées

| Rôle | Technologie retenue | Justification |
|------|--------------------|-----------   |
| Casque VR cible | Meta Quest 3 | Disponibilité, OpenXR support |
| Tracking des mains | OpenXR Hand Tracking | Standard ouvert, intégré à Unity XR Toolkit |
| Backend | API REST (modular monolith) | Voir [recherche backend](./backend.md) |
| IoT & capteurs | Protocole MQTT / HTTP | Voir [recherche IoT](./IoT_api.md) |
| Gestion de version | Git + GitHub | Standard équipe |

---
