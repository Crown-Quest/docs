## 1. Hand Tracking

### 1.1 Librairies disponibles

Actuellement (depuis moins de 2 ans) on peut utiliser du hand tracking très facilement grâce à un nouveau package unity. Cela permet d’intégrer rapidement des interactions naturelles basées sur les mains, sans passer par des contrôleurs physiques.

### 1.2 Principe d’intégration

Une fois le hand tracking ajouté au projet :
- Il suffit de définir des objets comme **"interactable"**
- À ces objets, on peut associer différents types d’actions :
  - **Click**
  - **Grab** (saisir)
  - **Teleport**

Dans le cadre du projet envisagé, **le téléport ne sera probablement pas utilisé**, afin de favoriser des déplacements plus immersifs et cohérents avec le gameplay.

### 1.3 Ressource vidéo

Vidéo de référence expliquant l’intégration et l’utilisation du hand tracking :  
👉 https://www.youtube.com/watch?v=t2leX7LA9JU

---

## 2. Déplacements du joueur

### 2.1 Mouvement par interaction gestuelle

Un exemple intéressant proposé par **Drakheir** montre une alternative au déplacement classique :
- Le joueur **"attrape" l’air devant lui** (grab dans le vide)
- Ce geste permet de **se tirer vers l’avant** et d’avancer

Cette approche renforce l’immersion et limite le motion sickness en évitant les déplacements artificiels via joystick ou téléportation.

On étudie également la possibilité de se déplacer en balançant les bras comme le système de course de blade and sorcery (blade and sorcery utilise le joystick pour le déplacement et le mouvement des bras uniquement pour course/marche).
Mais attention aux risques : possibilité de déclencher un déplacement du joueur alors que celui veut uniquement lever la main ou au contraire si le joueur doit entamer 2 ou 3 mouvements de bras avant de se déplacer en jeu, cela peut vite nuire à son expérience.

Autre Option, tracker le mouvement des jambes et se déplacer à l'aide de mouvements de genoux. Cela nécessiterai probablement des capteurs en plus

---

## 3. Interactions avec les PNJ

### 3.1 Exemple : *Waltz of the Wizard*

Un excellent exemple d’interaction avancée avec un PNJ est visible dans *Waltz of the Wizard* :
- Un **squelette** qui parle au joueur
- Il **répond aux actions et aux paroles** du joueur
- Il **sauvegarde l’état des interactions**
- Il **adapte ses dialogues** en fonction du contexte et de l’historique
- Il **sait quand le joueur s’adresse à lui**

Point important :
- **Aucun LLM n’est utilisé**
- Le système repose uniquement sur un **arbre logique de dialogues**

Ce jeu est également un **très bon exemple de hand tracking bien intégré**, à la fois pour les interactions et la communication avec les PNJ.

---

## 4. Autres références en hand tracking

### 4.1 *Maestro*

*Maestro* est un autre exemple marquant de l’utilisation du hand tracking :
- Précision des gestes
- Interaction fine avec l’environnement
- Exploitation naturelle des mains comme interface principale

---

## Conclusion

Ces différentes références montrent que :
- Le **hand tracking** est aujourd’hui suffisamment mature pour être au cœur du gameplay
- Des **déplacements alternatifs** au téléport sont viables et immersifs
- Des **PNJ crédibles et adaptatifs** peuvent être créés sans intelligence artificielle générative, uniquement via des arbres de décision bien conçus

Ces éléments serviront de base pour la conception et les choix techniques du futur jeu VR.
