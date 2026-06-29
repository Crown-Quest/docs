# Crown & Quest — Documentation

**Crown & Quest** est un projet académique EPITECH (T-ESP-700) visant à créer une simulation médiévale immersive combinant :

- **Réalité Virtuelle (VR)** — Unity 6 LTS + Meta Quest 3, hand tracking via OpenXR
- **Intelligence Artificielle** — PNJ adaptatifs, arbres de dialogue
- **IoT haptique** — Gilet DIY (ESP32 + moteurs vibrants), communication BLE avec Unity

L'objectif est d'offrir une expérience où le joueur **incarne réellement son avatar** dans un univers médiéval vivant, avec des retours physiques synchronisés aux événements du jeu.

> Équipe fondatrice : Maïva Magnifouet · Quentin Faivret · Geoffrey Mairesse

---

## Accès à la documentation

### Site en ligne (GitHub Pages)

La documentation est déployée automatiquement sur GitHub Pages à chaque push sur `main` :

```
https://crown-quest.github.io/docs/
```

### Running the docs site in dev mode

1. Install uv package manager
    ```bash
    curl -LsSf https://astral.sh/uv/install.sh | sh
    ```
2. Install dependencies
    ```bash
    uv sync
   ```
3. Run site locally
    ```bash
    uv run zensical serve
   ```

### Building the site

1. Build with uv
    ```bash
    uv run zensical build --clean
    ```
2. Deploy with the docker compose
    ```bash
    docker compose up -d
    ```

---

## Structure du projet

```
.
├── conf/                        # Configuration du serveur web (Caddyfile)
├── docs/                        # Sources de la documentation
│   ├── Architecture/            # Gantt, roadmap projet
│   ├── Contribution/            # Guide de contribution
│   ├── Human_ressources/        # Annonces de recrutement
│   ├── Project_management/      # Conventions, gestion d'équipe, RGPD
│   ├── Recherche/               # Études techniques (VR, IoT, backend, IA)
│   ├── WBS/                     # Work Breakdown Structure
│   └── css/                     # Styles personnalisés du site de docs
├── meetings/                    # Comptes-rendus de réunions (PDF)
├── site/                        # Site généré par Zensical (build output)
├── docker-compose.yaml          # Déploiement Caddy
├── pyproject.toml               # Configuration Python / uv
├── zensical.toml                # Configuration du site de documentation
└── mise.toml                    # Gestionnaire de versions d'outils
```

## Contribuer

Voir [CONTRIBUTING.md](./CONTRIBUTING.md) pour les conventions de commits, branches et pull requests.
