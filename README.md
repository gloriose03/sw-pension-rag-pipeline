# Scottish Widows Fund RAG

A personal research project to extract, analyse and compare Scottish Widows pension fund factsheets using Python and RAG.

## 1. Project Setup

### Git and GitHub

- `main` — Production branch.
- `test` — Testing branch.
- `feature/*` — Development branches.
- All changes go through pull requests: `feature → test → main`.

### Python Environment

We use `uv` to manage Python versions, virtual environments and dependencies.

Install uv on macOS:

```bash
brew install uv
```

Initialise a project:

```bash
uv init --bare --python 3.12
uv python install 3.12
uv python pin 3.12
```

This allows the project to use Python 3.12 without replacing the Python version installed on the laptop.

### Dependencies

Install project dependencies:

```bash
uv add requests beautifulsoup4 pdfplumber pandas pydantic python-dotenv
uv add --dev pytest
```

Important files:

- `.python-version` — Specifies the Python version.
- `pyproject.toml` — Stores project configuration and dependencies.
- `uv.lock` — Locks dependency versions for reproducibility.
- `.venv/` — Isolates the project environment.

We commit the first three files to GitHub but exclude `.venv/`.

### Folder Structure

- `data/raw/pdfs/` — Original PDF factsheets.
- `data/processed/` — Extracted and processed data.
- `data/database/` — Local database.
- `src/ingestion/` — Data downloading.
- `src/extraction/` — PDF parsing.
- `src/database/` — Database operations.
- `src/screening/` — Fund filtering.
- `src/rag/` — Retrieval and AI generation.
- `tests/` — Automated testing.
- `notebooks/` — Experimentation.
- `.github/workflows/` — CI/CD automation.
- `app.py` — Application entry point.

### Environment Variables

- `.env` — Local configuration and secrets.
- `.env.example` — Shareable configuration template.
- `.gitignore` — Prevents secrets, generated data and virtual environments from being committed.
- `.gitkeep` — Allows empty directories to be tracked by Git.

## 2. Recreate the Environment

After cloning the repository, install uv and run:

```bash
uv sync --locked
cp .env.example .env
```

Verify the environment:

```bash
uv run python --version
uv pip check
```

Run Python scripts:

```bash
uv run python app.py
```

No manual virtual environment activation is required.

## 3. Project Progress

- [x] Phase 1 — Project setup
- [ ] Phase 2 — Data ingestion
- [ ] Phase 3 — Data extraction
- [ ] Phase 4 — Structured database
- [ ] Phase 5 — Fund screening
- [ ] Phase 6 — RAG pipeline
- [ ] Phase 7 — Application
- [ ]
