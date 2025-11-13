### Setup virtual environment
1. uv venv
2. uv python pin 3.12
3. uv sync --extra dev --extra docs --upgrade
4. .\.venv\Scripts\Activate
5. uv add --dev pre-commit ruff
6. uv run python --version