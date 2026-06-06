# Sakto User Documentation Site

## Local Development Setup

1. Clone the repository.
2. To avoid conflict with system packages, it's recommended to create and use a Python virtual environment:

    **For macOS/Linux:**
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    ```

    **For Windows (Command Prompt/PowerShell):**
    ```cmd
    python -m venv .venv
    .venv\\Scripts\\activate
    ```

3. Install the required dependencies:
    ```bash
    pip install mkdocs mkdocs-material
    ```

4. Start the development server:
    ```bash
    mkdocs serve
    ```