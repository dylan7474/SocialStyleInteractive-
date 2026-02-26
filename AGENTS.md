# AGENTS.md

Guidance for future AI coding agents working in this repository.

## Project Overview

- This is a static single-page web app.
- Main application logic and UI live in `index.html`.
- There is no framework build pipeline in this repo.

## Working Conventions

1. Keep the project dependency-light; prefer native browser APIs.
2. Favor readable, commented JavaScript over clever abstractions.
3. Preserve the current UX language around Social Style quadrants.
4. Do not add heavyweight tooling unless explicitly requested.

## Validation Checklist

When making changes, run at least:

```bash
python3 -m http.server 8000
```

Then manually verify in a browser:

- Ranking interactions still enforce unique values per row.
- Totals update correctly.
- Import/export still works for JSON files.
- Results render correctly and print styles still hide controls.

## Documentation Expectations

- Update `README.md` when behavior, controls, or setup steps change.
- Add release notes in PR descriptions for user-facing changes.
- Keep instructions concise and actionable for non-technical users.
