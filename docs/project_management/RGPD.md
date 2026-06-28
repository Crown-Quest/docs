# Politique de Protection des Données Personnelles — RGPD

> **Crown & Quest** — Projet académique EPITECH (T-ESP-700)  
> Version 1.0 — Juin 2026

---

## 1. Introduction

Le projet **Crown & Quest** est une simulation médiévale immersive combinant la réalité virtuelle (VR), l'intelligence artificielle et les technologies IoT. Dans ce cadre, l'application est amenée à collecter, traiter et stocker des données personnelles relatives à ses utilisateurs (joueurs).

L'équipe Crown & Quest s'engage à respecter le **Règlement Général sur la Protection des Données (RGPD — Règlement UE 2016/679)** ainsi que la loi française **Informatique et Libertés** dans sa version consolidée.

Ce document a pour objectif de décrire de manière transparente :

- les données collectées et leur nature,
- les finalités et bases légales des traitements,
- les durées de conservation,
- les droits des utilisateurs et la manière de les exercer,
- les mesures de sécurité mises en place.

---

## 2. Responsable du traitement

| Champ | Information |
|---|---|
| **Entité** | Équipe Crown & Quest — Projet académique EPITECH |
| **Référents** | Maïva Magnifouet, Quentin Faivret, Geoffrey Mairesse |
| **Email de contact** | À définir par l'équipe |
| **Cadre** | Projet pédagogique — T-ESP-700, EPITECH |

> Dans le cadre académique de ce projet, les trois membres fondateurs de l'équipe sont conjointement responsables du traitement des données au sens du RGPD.

---

## 3. Données collectées

### 3.1 Données d'identification et de compte

| Donnée | Description | Obligatoire |
|---|---|---|
| Nom d'utilisateur (pseudo) | Identifiant public du joueur | Oui |
| Adresse e-mail | Utilisée pour l'authentification et les communications | Oui |
| Mot de passe | Stocké sous forme hachée (non réversible) | Oui |
| Date de création du compte | Horodatage d'inscription | Oui |

### 3.2 Données de profil et de progression

| Donnée | Description |
|---|---|
| Personnage et avatar | Apparence et nom du personnage dans le jeu |
| Niveau et statistiques | Progression, points d'expérience, attributs de jeu |
| Inventaire | Objets, équipements et ressources du joueur |
| Préférences de jeu | Paramètres graphiques, audio, accessibilité |

### 3.3 Données comportementales VR

Ces données sont collectées en temps réel pendant les sessions de jeu en réalité virtuelle.

| Donnée | Description | Sensibilité |
|---|---|---|
| Position spatiale | Localisation du joueur dans l'environnement virtuel | Modérée |
| Mouvements des mains | Tracking gestuel via OpenXR Hand Tracking (Meta Quest 3) | Modérée |
| Orientation de la tête | Direction du regard du joueur (casque VR) | Modérée |
| Patterns de déplacement | Analyse des habitudes de mouvement dans le jeu | Modérée |

> **Note importante :** Ces données de tracking VR peuvent être considérées comme des **données biométriques comportementales**. Elles ne sont utilisées qu'à des fins de jeu et ne sont pas partagées avec des tiers à des fins commerciales.

### 3.4 Données haptiques IoT (gilet haptique DIY)

Le gilet haptique connecté (basé sur un microcontrôleur ESP32) génère et reçoit des données relatives aux interactions physiques.

| Donnée | Description | Sensibilité |
|---|---|---|
| Zones haptiques activées | Identification des zones du gilet déclenchées (poitrine, épaules) | Faible |
| Intensité des vibrations | Paramètres d'intensité transmis via BLE | Faible |
| Patterns d'activation | Séquences haptiques jouées (choc, pluie, vent, etc.) | Faible |
| Logs de communication BLE | Horodatage des échanges entre Unity et l'ESP32 | Faible |

> Ces données transitent localement via Bluetooth Low Energy (BLE) entre le casque Meta Quest 3 et le gilet ESP32. Elles ne sont pas transmises au serveur backend sauf à des fins de débogage ou de télémétrie.

### 3.5 Données de session et multijoueur

| Donnée | Description |
|---|---|
| Dates et heures de connexion | Horodatage des sessions de jeu |
| Durée des sessions | Temps passé en jeu |
| Lobbies et parties | Participation à des sessions multijoueurs |
| Présence des joueurs | État de connexion des joueurs dans une partie |

### 3.6 Données techniques et de télémétrie

| Donnée | Description |
|---|---|
| Logs d'événements | Actions significatives dans le jeu |
| Logs d'erreurs | Erreurs techniques et crashs |
| Statistiques de performance | Framerate, latence réseau (à des fins d'optimisation) |
| Adresse IP | Collectée lors des connexions au serveur (module backend) |

---

## 4. Finalités du traitement

| Finalité | Données concernées | Base légale |
|---|---|---|
| Gestion des comptes et authentification | Identification, email, mot de passe | Exécution du contrat (CGU) |
| Fonctionnement du jeu | Progression, inventaire, préférences | Exécution du contrat (CGU) |
| Synchronisation multijoueur | Sessions, présence, événements temps réel | Exécution du contrat (CGU) |
| Retour haptique et immersion IoT | Données haptiques, patterns | Exécution du contrat (CGU) |
| Sécurité et anti-triche | Logs serveur, validation des actions | Intérêt légitime |
| Amélioration du jeu (R&D académique) | Télémétrie, statistiques anonymisées | Intérêt légitime |
| Débogage et support | Logs d'erreurs, données de session | Intérêt légitime |
| Conformité légale | Toutes catégories si nécessaire | Obligation légale |

---

## 5. Bases légales du traitement

Conformément à l'article 6 du RGPD, les traitements reposent sur les bases suivantes :

- **Exécution du contrat** (art. 6.1.b) : traitements nécessaires au fonctionnement de l'application et à la fourniture du service de jeu.
- **Intérêt légitime** (art. 6.1.f) : sécurité du système, prévention de la fraude, amélioration du service, débogage.
- **Consentement** (art. 6.1.a) : lorsque des données supplémentaires sont collectées à des fins d'analyse ou de recherche académique.
- **Obligation légale** (art. 6.1.c) : si requis par la législation applicable.

> Dans le cas de données biométriques comportementales (tracking VR), le traitement repose sur le **consentement explicite** de l'utilisateur, recueilli lors de l'inscription ou du premier lancement de l'application.

---

## 6. Durée de conservation

| Catégorie de données | Durée de conservation |
|---|---|
| Données de compte (actif) | Durée de vie du compte + 30 jours après suppression |
| Données de progression et inventaire | Durée de vie du compte |
| Données comportementales VR (sessions) | 90 jours glissants |
| Données haptiques IoT (logs) | 30 jours glissants |
| Logs techniques et télémétrie | 30 jours glissants |
| Logs de sécurité | 12 mois |
| Données après suppression de compte | Suppression définitive sous 30 jours |

> Dans le contexte académique du projet, ces durées peuvent être adaptées aux besoins de recherche, sous réserve d'anonymisation préalable des données.

---

## 7. Partage et destinataires des données

### 7.1 Pas de vente de données

**Crown & Quest ne vend aucune donnée personnelle à des tiers.**

### 7.2 Accès interne à l'équipe

Les données sont accessibles aux membres de l'équipe Crown & Quest dans le strict cadre de leurs responsabilités :

| Membre | Rôle | Accès aux données |
|---|---|---|
| Responsables fondateurs | Chef de projet, architecture | Accès complet (administration) |
| Développeurs Unity | Développement VR et gameplay | Données de jeu et haptiques |
| Développeur Backend | Infrastructure et API | Données techniques, comptes (hashés) |
| Développeur IA | Systèmes d'IA des PNJ | Données comportementales anonymisées |

### 7.3 Sous-traitants et services tiers

Dans le cadre du projet académique, aucun service tiers payant n'est utilisé. Les éventuelles dépendances techniques sont :

| Service | Données transmises | Localisation |
|---|---|---|
| GitHub (hébergement du code) | Code source uniquement, pas de données joueurs | UE/International |
| Meta Quest 3 (SDK XR) | Données de tracking traitées localement sur le casque | Appareil local |
| ESP32 (IoT) | Données haptiques via BLE local uniquement | Appareil local |

### 7.4 Transferts hors UE

Dans le cadre actuel du projet, **aucun transfert de données personnelles hors de l'Union Européenne n'est effectué** intentionnellement.

---

## 8. Droits des utilisateurs

Conformément aux articles 15 à 22 du RGPD, chaque utilisateur dispose des droits suivants :

| Droit | Description | Comment l'exercer |
|---|---|---|
| **Droit d'accès** (art. 15) | Obtenir une copie de toutes les données vous concernant | Contacter l'équipe par email |
| **Droit de rectification** (art. 16) | Corriger des données inexactes ou incomplètes | Via les paramètres du compte ou par email |
| **Droit à l'effacement** (art. 17) | Supprimer votre compte et toutes les données associées | Via les paramètres du compte ou par email |
| **Droit à la limitation** (art. 18) | Suspendre temporairement le traitement de vos données | Contacter l'équipe par email |
| **Droit à la portabilité** (art. 20) | Recevoir vos données dans un format structuré et lisible | Contacter l'équipe par email |
| **Droit d'opposition** (art. 21) | Vous opposer au traitement basé sur l'intérêt légitime | Contacter l'équipe par email |
| **Droit de retirer le consentement** (art. 7.3) | Révoquer un consentement donné à tout moment | Via les paramètres ou par email |

### 8.1 Délais de réponse

L'équipe s'engage à répondre à toute demande relative à l'exercice de ces droits dans un délai de **30 jours calendaires** à compter de la réception de la demande.

### 8.2 Droit de réclamation

En cas de non-réponse ou de réponse insatisfaisante, l'utilisateur peut introduire une réclamation auprès de la **CNIL** (Commission Nationale de l'Informatique et des Libertés) :

- Site web : [www.cnil.fr](https://www.cnil.fr)
- Adresse : 3 Place de Fontenoy — TSA 80715 — 75334 Paris Cedex 07

---

## 9. Données particulièrement sensibles

### 9.1 Données biométriques comportementales (VR)

Le hand tracking et le suivi spatial via Meta Quest 3 génèrent des **données biométriques comportementales** au sens du RGPD (article 9). Ces données permettent potentiellement d'identifier une personne par ses habitudes gestuelles.

**Mesures spécifiques :**
- Traitement strictement local sur l'appareil Meta Quest 3 lorsque possible
- Données de session non stockées au-delà de 90 jours
- Anonymisation des données agrégées avant toute analyse R&D
- Consentement explicite requis avant activation du tracking étendu

### 9.2 Données physiques IoT (gilet haptique)

Le gilet haptique DIY (ESP32 + actionneurs) interagit physiquement avec le corps du joueur. Bien que les données échangées soient de nature technique (intensité, zone, pattern), elles impliquent une **interaction physique directe**.

**Mesures spécifiques :**
- Communication BLE locale uniquement (pas de cloud)
- Aucune donnée biométrique extraite du port haptique (pas de capteur physiologique)
- Les logs de débogage sont supprimés après 30 jours

### 9.3 Protection des mineurs

Crown & Quest est un jeu en réalité virtuelle impliquant un contact physique via le gilet haptique. L'expérience n'est pas recommandée pour les enfants de moins de 13 ans, conformément aux recommandations des fabricants de casques VR.

**Pour les utilisateurs de moins de 16 ans :**
- Le **consentement d'un représentant légal** (parent ou tuteur) est requis pour la création de compte
- Les données des mineurs font l'objet d'une protection renforcée
- Aucune donnée de profil d'un mineur n'est partagée ou utilisée à des fins d'analyse

---

## 10. Sécurité des données

L'équipe Crown & Quest met en œuvre les mesures techniques et organisationnelles suivantes :

### 10.1 Mesures techniques

| Mesure | Description |
|---|---|
| Hachage des mots de passe | Algorithme sécurisé (bcrypt ou Argon2), jamais stocké en clair |
| HTTPS obligatoire | Chiffrement TLS pour toutes les communications backend (Caddy) |
| Validation serveur | Le serveur est la source de vérité (modèle autoritatif) |
| Journalisation des actions sensibles | Logs horodatés et sécurisés |
| Séparation des modules | Architecture Modular Monolith avec modules isolés |
| Communication BLE locale | Les données haptiques ne transitent pas par internet |

### 10.2 Mesures organisationnelles

| Mesure | Description |
|---|---|
| Accès restreint | Principe du moindre privilège — accès limité selon le rôle |
| Revue de code | Toute modification du code backend est revue par au moins un pair |
| Branche main protégée | Aucun push direct sur main sans pull request et approbation |
| Sensibilisation de l'équipe | L'ensemble des membres est sensibilisé aux bonnes pratiques RGPD |

### 10.3 En cas de violation de données

En cas de violation de données personnelles, l'équipe s'engage à :

1. Identifier et contenir la violation dans les plus brefs délais
2. Notifier la **CNIL** dans un délai de **72 heures** si la violation est susceptible d'engendrer un risque pour les droits et libertés des personnes
3. Informer directement les utilisateurs concernés si le risque est élevé

---

## 11. Cookies et stockage local

L'application Crown & Quest (composante web / documentation) peut utiliser des données stockées localement :

| Type | Usage | Base légale |
|---|---|---|
| Cookies de session | Maintien de la connexion utilisateur | Nécessaire au service |
| Préférences d'interface | Mémorisation des paramètres du jeu | Consentement |
| Données de cache | Optimisation des performances | Intérêt légitime |

Aucun cookie publicitaire ou traceur de marketing tiers n'est utilisé.

---

## 12. Modifications de cette politique

Cette politique de protection des données peut être mise à jour pour refléter les évolutions du projet, les nouvelles fonctionnalités ou les changements réglementaires.

En cas de modification substantielle :
- La version et la date de mise à jour seront indiquées en en-tête
- Les utilisateurs actifs seront notifiés par email
- Le consentement sera recueilli à nouveau si la modification affecte les bases légales

---

## 13. Contact et exercice des droits

Pour toute question relative à la protection de vos données ou pour exercer vos droits :

**Équipe Crown & Quest**  
Email : *geoffrey.mairesse@epitech.eu*  
Objet du message : `[RGPD] — Objet de votre demande`

Veuillez joindre à votre demande une copie d'un justificatif d'identité afin de permettre la vérification de votre identité avant traitement.

---

*Document rédigé conformément au RGPD (Règlement UE 2016/679) et à la loi Informatique et Libertés (loi n° 78-17 du 6 janvier 1978 modifiée).*
