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

## CI/CD and Deployment Workflow
We use GitHub Actions to automate our testing and deployment process. We maintain two branches:
- `main` (Integration/Testing): All feature pull requests merge here first. It acts as our staging environment.
- `prod` (Production/Live): The branch that reflects what is currently live on the website.

### Continuous Integration (Testing)
When a pull request (PR) is opened against the `main` or `prod` branch, our CI pipeline runs a strict build test (`mkdocs build --strict`). If there are any dead links, missing images, or critical warnings, the build fails and blocks the PR from being merged.

### Continuous Deployment (Publishing)
Merging code into `main` does not update the live site.

To publish updates to the live site, a PR must be opened from `main` into `prod`. Once code is officially merged into `prod`, the CD pipeline compiles the site and automatically pushes it to the `gh-pages` hosting branch, which instantly updates the live URL.
