# Repository Guidelines

## Project Structure & Module Organization
- `agents/`, `chat-langchain/`, `embeddings/`, `rag/`, `semantic-search/`, `structured-output/`, `tool-calling/`, `workflows/`: Topic-focused Jupyter notebooks. Open them to run code step by step.
- `rag/data/`: Sample documents and resources for RAG.
- `semantic-search/chroma_db/`: Local vector DB artifacts (safe to delete/rebuild).
- `images/`: Static assets used in docs.
- Per-folder `.env`: API keys and config used by notebooks (do not commit real secrets).

## Build, Test, and Development Commands
- Set up environment: `python -m venv .venv && source .venv/bin/activate`
- Jupyter tooling: `pip install -U jupyter ipykernel`
- Common libs (install as needed per notebook): `pip install -U openai langchain chromadb`
- Run locally: `jupyter lab` (or open notebooks in VS Code).
- Reset state: remove `semantic-search/chroma_db/` to rebuild indexes on next run.

## Coding Style & Naming Conventions
- Python: PEP 8, 4-space indentation, `snake_case` for variables/functions, `PascalCase` for classes.
- Notebooks: concise cells, clear markdown headings, keep examples runnable end-to-end.
- Filenames: prefer short, descriptive notebook names (use hyphens, e.g., `langchain-tool-call.ipynb`). For Python utilities, use `snake_case.py`.

## Testing Guidelines
- No central test suite. If adding Python helpers, add `tests/` and use `pytest` (`pip install -U pytest`).
- For notebooks, include a quick “sanity check” cell (e.g., small inference run) and seed randomness where possible.
- Aim to keep examples deterministic and under a few minutes per run.

## Commit & Pull Request Guidelines
- Commits: imperative mood, short and focused (e.g., `workflows: add web search demo`). English or Spanish is fine; keep <72 chars in subject.
- PRs: include purpose, affected folders, setup steps, and screenshots or sample outputs when relevant. Link related issues.
- Checklist: notebooks run top-to-bottom, no secrets, `.env` documented, large artifacts excluded.

## Security & Configuration Tips
- Required env vars vary by notebook; commonly `OPENAI_API_KEY` and, for web search flows, `TAVILY_API_KEY`.
- Use per-folder `.env` files and `python-dotenv` patterns if scripting; never commit real keys. Rotate any exposed credentials immediately.
