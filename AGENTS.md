# AGENTS.md

Guidance for future AI coding agents working in this repository.

## Project Overview

- This is a static single-page web app repository with **two** entry points:
  - `Profiler.html` for the individual extended assessment experience.
  - `TeamPro.html` for the team/facilitator workflow (dashboard, interaction lab, synergy tools, and AI-assisted reporting).
- There is no framework build pipeline in this repo.

## Working Conventions

1. Keep the project dependency-light; prefer native browser APIs.
2. Favor readable, commented JavaScript over clever abstractions.
3. Preserve the current UX language around Social Style quadrants.
4. Do not add heavyweight tooling unless explicitly requested.
5. If behavior overlaps across `Profiler.html` and `TeamPro.html`, keep interaction rules consistent unless the feature is intentionally variant-specific.

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
- If `TeamPro.html` is touched: team upload works, dashboard metrics render, synergy comparisons update for selected members, and AI commentary/fallback prompt states can be generated or displayed. `TeamPro.html` keeps Extended Deep-Dive rows always enabled.

## Documentation Expectations

- Update `README.md` when behavior, controls, setup steps, or entry points change.
- Add release notes in PR descriptions for user-facing changes.
- Keep instructions concise and actionable for non-technical users.
