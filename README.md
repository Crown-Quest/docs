# T-ESP-700-CrownQuest
Documentation repository for the T-ESP project CrownQuest

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
