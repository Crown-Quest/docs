# IoT Hardware – Crown & Quest

## 1. Contexte et objectifs

Dans le cadre du projet Crown & Quest, l’IoT joue un rôle central dans l’immersion du joueur.  
L’objectif est de permettre au joueur de **ressentir physiquement les interactions** du monde virtuel (chocs, météo, ambiances) à travers un **gilet haptique connecté**.

Pour la phase 2 du projet (recherche et prototypage), deux approches ont été étudiées :
- l’utilisation d’un **gilet haptique existant**
- la **conception et fabrication d’un gilet haptique DIY**

Cette étude vise à comparer ces approches et à justifier le choix technique retenu.

---

## 2. Option 1 – Achat d’un gilet haptique existant

### 2.1 Principe général

Les gilets haptiques commerciaux (ex : bHaptics TactSuit, OWO Vest) sont des dispositifs intégrant :
- une matrice de moteurs vibrants répartis sur le torse et le dos,
- une électronique embarquée propriétaire,
- une batterie intégrée,
- une communication sans fil (Bluetooth/BLE),
- un SDK permettant de déclencher des effets haptiques via des “patterns”.

Ces produits offrent une solution **clé en main**, rapidement exploitable pour des démonstrations.

---

### 2.2 Avantages

- Mise en œuvre rapide
- Qualité de rendu haptique éprouvée
- SDK et documentation existants
- Démonstrations immersives immédiates

---

### 2.3 Limites

- Coût élevé (≈ 300–350 € par gilet)
- Architecture fermée et propriétaire
- Peu de contrôle sur le hardware interne
- Faible valeur pédagogique sur la partie IoT
- Difficulté à justifier l’achat dans une logique de R&D

---

### 2.4 Conclusion option 1

Bien que pertinente pour une démonstration rapide, cette solution ne répond pas pleinement aux objectifs pédagogiques du projet, notamment en matière de **conception IoT, électronique et intégration bas niveau**.

---

## 3. Option 2 – Conception et fabrication d’un gilet haptique DIY (choix retenu)

### 3.1 Objectifs de la solution DIY

- Concevoir un système haptique **maîtrisé de bout en bout**
- Permettre une **expérimentation progressive** (scalabilité)
- Travailler sur :
  - électronique embarquée
  - communication sans fil
  - intégration Unity ↔ IoT
  - patterns haptiques
- Réduire les coûts
- Maximiser la valeur pédagogique

---

### 3.2 Architecture générale

Le gilet haptique DIY est composé de :

- Un **support textile** (gilet tactique / porte-plaques)
- Un **microcontrôleur ESP32**
- Des **actionneurs haptiques** (moteurs vibrants)
- Des **drivers ou circuits de pilotage**
- Une **batterie Li-ion / LiPo**
- Une communication **Bluetooth Low Energy (BLE)** avec Unity (Meta Quest 3)

---

### 3.3 Zones haptiques (Phase 2)

Pour la phase 2, le prototype repose sur **4 zones haptiques** :

- Poitrine gauche
- Poitrine droite
- Épaule gauche
- Épaule droite

Ce découpage est jugé :
- techniquement ambitieux mais réaliste,
- suffisant pour ressentir impacts, météo et ambiances,
- facilement extensible dans les phases suivantes.

---

### 3.4 Actionneurs haptiques

Deux types d’actionneurs sont envisageables :

- **ERM (Eccentric Rotating Mass)**  
  - moteurs vibrants simples
  - robustes, peu coûteux
  - parfaitement adaptés au prototypage

- **LRA (Linear Resonant Actuator)**  
  - vibrations plus précises
  - coût plus élevé
  - optionnelle pour des versions ultérieures

Pour la phase 2, le choix se porte sur des **ERM**, plus simples à intégrer.

---

### 3.5 Pilotage des vibrations

Deux approches sont possibles :

#### a) Drivers haptiques dédiés
- Ex : DRV2605L (un par zone)
- Permettent :
  - impulsions nettes
  - rampes
  - effets prédéfinis
- Très qualitatif pour les démonstrations

#### b) Pilotage PWM via MOSFET
- Solution plus économique
- Pilotage logiciel des patterns
- Très scalable (16–40 zones)
- Suffisant pour météo, chocs et ambiances

Le choix exact est laissé ouvert durant la phase 2 afin de comparer les deux approches.

---

### 3.6 Microcontrôleur et communication

- **ESP32**
  - Bluetooth Low Energy (BLE)
  - Wi-Fi (optionnel)
  - Large écosystème
  - Faible consommation

#### Communication recommandée
- **BLE direct entre Meta Quest 3 (Unity) et ESP32**
- Avantages :
  - très faible latence
  - fonctionnement hors connexion backend
  - simplicité d’intégration

---

### 3.7 Patterns haptiques (logique fonctionnelle)

Le ressenti “réaliste” repose principalement sur des **patterns haptiques**, et non sur le hardware seul.

Exemples de patterns implémentables :

- **Choc**
  - impulsion forte et courte
- **Bousculade**
  - double impulsion dégressive
- **Vent**
  - vibration légère continue
- **Pluie**
  - micro-impulsions aléatoires
- **Tonnerre**
  - vibration basse fréquence + pic soudain

Ces patterns sont déclenchés par Unity selon les événements du jeu.