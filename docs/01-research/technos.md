# Crown & Quest — Choix Technologiques

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

## 4. Retour haptique — bHaptics SDK

### 4.1 Présentation

**bHaptics** est une entreprise spécialisée dans les solutions de retour haptique pour la réalité virtuelle. Leur gamme de produits comprend :

- **TactSuit X40 / X16** : veste haptique avec actuateurs sur le torse et le dos
- **TactGlove** : gants haptiques pour les mains
- **TactVisor** : vibrateurs intégrés dans le casque (face / tempes)
- **TactShoe** : retour haptique au niveau des pieds

Le **bHaptics SDK** est le kit de développement officiel permettant de piloter ces dispositifs depuis une application Unity.

### 4.2 Fonctionnement

Le SDK expose une API C# permettant de :
- Déclencher des patterns haptiques prédéfinis (`.tact` files)
- Créer des retours haptiques dynamiques et paramétrables
- Cibler précisément les zones du corps (position, intensité, durée)
- Réagir à des événements de jeu en temps réel (impacts, magie, environnement)

La communication avec les dispositifs se fait en Bluetooth ou via le logiciel **bHaptics Player** installé sur l'ordinateur hôte.

### 4.3 Alternatives étudiées

| Solution | Points forts | Raisons d'exclusion |
|----------|-------------|---------------------|
| **OWO Suit** | Retour haptique musculaire (électrostimulation) | API moins mature, coût élevé, contraintes de sécurité |
| **Subpac** | Retour haptique basse fréquence (basses) | Pas d'API de développement, usage passif |
| **HaptX Gloves** | Très haute précision tactile | Coût prohibitif (usage industriel) |
| **Haptic solution maison** | Personnalisable | Développement matériel hors périmètre du projet |

### 4.4 Justification du choix

bHaptics est retenu pour les raisons suivantes :

- **SDK Unity officiel** disponible gratuitement sur l'Asset Store
- **Documentation complète** avec exemples Unity prêts à l'emploi
- **Gamme de dispositifs** couvrant l'ensemble du corps pour une immersion totale
- **Latence faible** pour des retours synchronisés aux événements VR
- **Fichiers `.tact`** permettant de designer les patterns haptiques visuellement (via bHaptics Designer)
- **Compatibilité OpenXR** : fonctionne avec les principaux casques VR

---

## 5. Architecture d'intégration Unity + bHaptics

### 5.1 Flux général

```
Événement de jeu (Unity)
    → Script C# (GameEvent)
        → bHaptics SDK API
            → bHaptics Player (daemon)
                → Dispositif haptique (Bluetooth)
```

### 5.2 Cas d'usage haptiques prévus

| Événement en jeu | Retour haptique |
|-----------------|-----------------|
| Réception d'un coup | Impact localisé sur le torse (TactSuit) |
| Utilisation de magie | Vibration diffuse sur les mains (TactGlove) |
| Explosion à proximité | Onde de choc sur le torse et le dos |
| Interaction avec objet | Retour doux sur les doigts |
| Ambiance (vent, froid) | Pattern lent et continu sur le corps |

### 5.3 Organisation du code

Les retours haptiques seront centralisés dans un **HapticsManager** singleton, abonné aux événements du système de jeu. Ce manager traduit les événements logiques en appels SDK, garantissant un découplage entre la logique de jeu et la couche haptique.

```csharp
// Exemple simplifié
public class HapticsManager : MonoBehaviour
{
    public static HapticsManager Instance { get; private set; }

    public void PlayImpact(BodySide side, float intensity)
    {
        // Appel bHaptics SDK
        BhapticsLibrary.Play(side == BodySide.Left ? "impact_left" : "impact_right", intensity);
    }
}
```

---

## 6. Autres technologies associées

| Rôle | Technologie retenue | Justification |
|------|--------------------|-----------   |
| Casque VR cible | Meta Quest 3 / Valve Index | Disponibilité, OpenXR support |
| Tracking des mains | OpenXR Hand Tracking | Standard ouvert, intégré à Unity XR Toolkit |
| Backend | API REST (modular monolith) | Voir [recherche backend](./backend.md) |
| IoT & capteurs | Protocole MQTT / HTTP | Voir [recherche IoT](./IoT_api.md) |
| Gestion de version | Git + GitHub | Standard équipe |

---

## 7. Conclusion

L'association **Unity + bHaptics SDK** constitue le socle technologique principal de Crown & Quest.

- **Unity** offre un environnement de développement VR mature, productif et gratuit pour ce contexte académique.
- **bHaptics** permet d'intégrer un retour haptique complet et sur-mesure, renforçant significativement l'immersion de la simulation médiévale.

Ces deux technologies sont compatibles, bien documentées, et supportées par des communautés actives, ce qui minimise les risques techniques tout en maximisant le potentiel d'expérience utilisateur.
