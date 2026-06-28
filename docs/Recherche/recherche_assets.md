# Crown & Quest — Recherche d'assets Unity Asset Store

*Sélection des ressources 3D, audio et animation pour le prototype (POC)*

Projet de fin d'année — Simulation VR / IoT médiévale

---

## Sommaire

1. [Objectif de la recherche](#1-objectif-de-la-recherche)
2. [Environnement](#2-environnement)
3. [Armes](#3-armes)
4. [Personnages](#4-personnages-ennemis-pnj-personnage-principal)
5. [Animations](#5-animations)
6. [Effets sonores (SFX)](#6-effets-sonores-sfx)
7. [Synthèse des assets retenus](#7-synthèse-des-assets-retenus-pour-le-poc)
8. [Conclusion et prochaines étapes](#8-conclusion-et-prochaines-étapes)

---

## 1. Objectif de la recherche

Dans le cadre du développement du POC (Proof of Concept) de Crown & Quest, une phase de recherche a été menée sur l'Unity Asset Store afin d'identifier des ressources prêtes à l'emploi (environnements 3D, armes, personnages, animations et effets sonores) permettant d'accélérer la création de l'univers médiéval du projet, sans mobiliser de temps de production sur des assets qui ne sont pas au cœur de la valeur ajoutée du projet (IA, IoT, VR).

Cette recherche a été structurée selon cinq catégories, correspondant aux grands besoins identifiés pour peupler et animer l'univers du jeu :

- **Environnement** (map, château, village, forêt)
- **Armes**
- **Personnages** (ennemis, PNJ, personnage principal)
- **Animations**
- **SFX** (effets sonores et voix)

Pour chaque catégorie, plusieurs assets ont été comparés sur des critères communs : qualité visuelle, compatibilité avec la version de Unity utilisée pour le projet, licence/coût, poids du package, et adéquation avec la direction artistique — un médiéval fantastique, modulaire et crédible — définie dans le document de vision du projet.

### Légende

- ✅ **Retenu pour le POC** : asset sélectionné et qui sera intégré dans le prototype.
- ⏳ **Non retenu / à creuser** : catégorie explorée mais sans candidat satisfaisant à ce stade, ou piste à approfondir plus tard.

---

## 2. Environnement

L'univers de Crown & Quest repose sur plusieurs lieux distincts — forteresse, château, village, forge, arène — décrits dans le concept du projet. Trois assets complémentaires ont été retenus pour couvrir respectivement la structure du château, l'ambiance du village et le mobilier/décor de remplissage.

### 2.1 Château modulaire — ✅ Retenu

| Champ | Détail |
|---|---|
| **Asset** | Medieval Castle – Modular |
| **Éditeur** | Advance Studios |
| **Prix** | Gratuit |
| **Lien** | [Voir sur l'Asset Store](https://assetstore.unity.com/packages/3d/environments/fantasy/medieval-castle-modular-282498) |
| **Compatibilité** | Built-in, URP et HDRP (testé sur Unity 2022.3.11f1) |

**Description :** Pack d'éléments modulaires (murs, tours, portes, créneaux) permettant d'assembler un château médiéval personnalisé pièce par pièce, plutôt qu'une scène figée.

**Pourquoi ce choix :** l'approche modulaire correspond directement au besoin du château et de la forteresse de Crown & Quest : possibilité d'adapter la disposition des bâtiments à la mise en scène voulue, gratuité idéale pour un POC, et poids léger (16 Mo) qui limite l'impact sur les temps de build.

### 2.2 Village médiéval — ✅ Retenu

| Champ | Détail |
|---|---|
| **Asset** | Medieval Village Environment |
| **Éditeur** | Asset Maiden |
| **Prix** | 16,49 $ |
| **Lien** | [Voir sur l'Asset Store](https://assetstore.unity.com/packages/3d/environments/fantasy/medieval-village-environment-121867) |
| **Compatibilité** | Conçu sous Unity 2018.4.33 (à vérifier en import sur Unity 6 LTS) |

**Description :** Environnement de village médiéval complet (maisons, rues, décor extérieur) avec une forte popularité (plus de 1000 ajouts en favoris).

**Pourquoi ce choix :** apporte une zone habitée crédible en complément du château, utile pour donner une impression de « monde vivant » évoquée dans la vision du projet. Le faible coût reste raisonnable pour un projet étudiant ; un test d'import anticipé est recommandé compte tenu de l'ancienneté du package (dernière mise à jour en 2021).

### 2.3 Props / décoration RPG — ✅ Retenu

| Champ | Détail |
|---|---|
| **Asset** | RPG Medieval Props Pack 01 |
| **Éditeur** | Astra Forge |
| **Prix** | Gratuit |
| **Lien** | [Voir sur l'Asset Store](https://assetstore.unity.com/packages/3d/environments/rpg-medieval-props-pack-01-294298) |
| **Compatibilité** | URP et HDRP (non compatible Built-in) |

**Description :** Pack de props de décoration médiévale (tonneaux, caisses, échelle pliante, tente, charrette à bras, vases, amphores) destiné à habiller les scènes RPG.

**Pourquoi ce choix :** permet de « remplir » la forteresse, le village et la forge avec des éléments de détail qui renforcent l'immersion sans coût de modélisation supplémentaire ; gratuit et directement compatible avec le pipeline URP utilisé par le projet.

---

## 3. Armes

L'arène et la forge impliquent la manipulation d'armes (combat, forge). Un seul pack a été retenu pour cette catégorie afin de couvrir un socle d'armes médiévales de base réutilisable à la fois par le joueur et par les PNJ ennemis.

### 3.1 Pack d'armes médiévales — ✅ Retenu

| Champ | Détail |
|---|---|
| **Asset** | Free pack of medieval weapons |
| **Éditeur** | Osmanov |
| **Prix** | Gratuit |
| **Lien** | [Voir sur l'Asset Store](https://assetstore.unity.com/packages/3d/props/weapons/free-pack-of-medieval-weapons-136607) |
| **Compatibilité** | Package d'origine Unity 2018.2.2 (vérifier le rendu des matériaux après import) |

**Description :** Pack gratuit de modèles d'armes médiévales (épées, etc.), avec plus de 3000 utilisateurs l'ayant ajouté en favoris, signe d'une certaine fiabilité communautaire.

**Pourquoi ce choix :** fournit un socle gratuit d'armes pour équiper le personnage principal et les PNJ de l'arène, suffisant pour un POC où l'objectif est de valider les mécaniques de combat et de ressenti haptique plutôt que la diversité visuelle de l'arsenal.

---

## 4. Personnages (ennemis, PNJ, personnage principal)

> ⏳ **Aucun asset retenu à ce stade.**
>
> Les packs de personnages explorés ne correspondaient pas de façon satisfaisante aux besoins du projet (rig compatible avec les animations RPG retenues, style visuel cohérent avec le reste de l'univers, ou simplement qualité insuffisante pour les standards visés). Cette catégorie reste donc ouverte et devra être réexaminée — éventuellement avec un budget dédié — lors de la phase d'expansion du monde (intégration de l'IA et des PNJ).

---

## 5. Animations

Le personnage principal nécessite un socle d'animations de base (déplacement, combat, interactions) pour donner vie aux mouvements en réalité virtuelle.

### 5.1 Animations RPG du MC — ✅ Retenu

| Champ | Détail |
|---|---|
| **Asset** | RPG_Animations_Pack_FREE |
| **Éditeur** | DoubleL |
| **Prix** | Gratuit |
| **Lien** | [Voir sur l'Asset Store](https://assetstore.unity.com/packages/3d/animations/rpg-animations-pack-free-288783) |
| **Compatibilité** | Built-in, URP et HDRP (Unity 2022.3.27f1), maintenu activement (mise à jour 1.8 en 2026) |

**Description :** Pack gratuit d'animations RPG inspirées du style « Souls-like » (déplacements, coups, montée à l'échelle), avec plus de 1400 utilisateurs l'ayant ajouté en favoris.

**Pourquoi ce choix :** couvre les animations génériques du personnage principal (MC) sans nécessiter de motion capture ou de production interne ; le style « Souls-like » correspond bien à l'ambiance de combat recherchée pour l'arène, et le suivi actif du package est un gage de fiabilité pour la durée du projet.

---

## 6. Effets sonores (SFX)

Cette catégorie est considérée comme un **bonus** : elle n'est pas indispensable à la validation du POC, mais elle enrichirait significativement l'immersion sonore recherchée (cf. « sons et sensations » dans la vision du projet).

### 6.1 Voix de chevalier — Référence / bonus

| Champ | Détail |
|---|---|
| **Asset** | Medieval Knight Male Voice Pack |
| **Éditeur** | Stormwave Audio |
| **Prix** | 4,99 $ |
| **Lien** | [Voir sur l'Asset Store](https://assetstore.unity.com/packages/audio/sound-fx/voices/medieval-knight-male-voice-pack-115745) |
| **Compatibilité** | Built-in, URP et HDRP (Unity 2021.3.34f1) |

**Description :** Pack de voix masculines à thématique « chevalier médiéval » (cris d'effort, répliques de combat) destiné à sonoriser un personnage ou un PNJ.

**Pourquoi ce choix :** référence de qualité professionnelle pour calibrer le ton et la diversité de répliques attendus, à un coût symbolique. Sert avant tout de point de comparaison : l'objectif est d'explorer la possibilité de générer des voix similaires via une IA de synthèse vocale, ce qui offrirait plus de flexibilité (texte dynamique, personnages multiples) qu'un pack figé.

### 6.2 Piste à creuser : voix générées par IA

Plutôt que d'acheter plusieurs packs de voix figées pour chaque type de PNJ, une piste à approfondir consiste à **générer des voix médiévales similaires via une IA de synthèse vocale** (text-to-speech). Cette approche permettrait de produire dynamiquement des répliques pour un nombre illimité de PNJ sans dépendre d'un enregistrement studio, au prix d'un travail de recherche supplémentaire sur les outils disponibles, leur qualité de rendu « médiéval » et leur compatibilité avec une intégration Unity en temps réel ou pré-générée.

---

## 7. Synthèse des assets retenus pour le POC

| Catégorie | Asset | Éditeur | Prix |
|---|---|---|---|
| Environnement | Medieval Castle – Modular | Advance Studios | Gratuit |
| Environnement | Medieval Village Environment | Asset Maiden | 16,49 $ |
| Environnement | RPG Medieval Props Pack 01 | Astra Forge | Gratuit |
| Armes | Free pack of medieval weapons | Osmanov | Gratuit |
| Personnages | *Aucun asset retenu — à creuser* | — | — |
| Animations | RPG_Animations_Pack_FREE | DoubleL | Gratuit |
| SFX (bonus) | Medieval Knight Male Voice Pack | Stormwave Audio | 4,99 $ |

**Coût total estimé pour le socle d'assets retenus : environ 21,48 $ (hors taxes)**, pour l'essentiel concentré sur l'environnement du village.

---

## 8. Conclusion et prochaines étapes

Cette recherche a permis d'identifier un socle d'assets gratuits ou peu coûteux couvrant l'environnement, les armes et les animations de base nécessaires au POC de Crown & Quest, en cohérence avec l'esthétique médiévale modulaire visée par le projet.

- **Personnages** : poursuivre la recherche de packs de personnages (ennemis, PNJ, MC) compatibles avec le rig des animations retenues, en élargissant éventuellement le budget.
- **SFX** : évaluer des solutions de synthèse vocale par IA pour générer des voix médiévales sur mesure, en complément ou remplacement de packs figés.
- **Compatibilité** : valider l'import de chaque asset dans la version actuelle du moteur (Unity 6 LTS) avant intégration définitive, certains packages ayant été publiés sur des versions plus anciennes de Unity.
