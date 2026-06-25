# Social Style Preferences Interactive Assessment

A lightweight, static web app repository for running **Social Style Preferences** assessments based on the Bolton & Bolton model. Participants rank behavioral traits to reveal their dominant communication style across four quadrants:

- **Driver**
- **Expressive**
- **Amiable**
- **Analytical**

The project has been simplified to two application files only: one individual profiler and one team/facilitator experience. There is no framework, package install, build step, or backend service required.

## Applications

This repository now includes two static HTML entry points:

- **`Profiler.html`**: individual Social Style Profiler Extended Deep-Dive. This is the participant-facing assessment with all 10 ranking rows enabled, core/extended score breakdowns, style insights, JSON import/export, and printable results.
- **`TeamPro.html`**: facilitator/team workflow for collecting individual assessments, uploading multiple profile JSON files, viewing team composition, comparing member synergy, and generating AI-assisted coaching/commentary where supported by the browser.

Use `Profiler.html` for individual assessment and profile export. Use `TeamPro.html` when facilitating a team session or reviewing multiple participant profiles together.

## Build / run instructions

Because this project is static HTML/CSS/JavaScript, there is no package install or compilation required.

### Option 1: Open directly

1. Clone or download this repository.
2. Open `Profiler.html` or `TeamPro.html` in a modern browser.

### Option 2: Serve locally (recommended)

From the repository root, run:

```bash
python3 -m http.server 8000
```

Then open one of:

```text
http://localhost:8000/Profiler.html
http://localhost:8000/TeamPro.html
```

## Profiler controls (`Profiler.html`)

- **Rank buttons (1–4):** For each row, assign each rank exactly once across the four traits.
- **Total Scores:** Updates as responses are completed.
- **Extended Deep-Dive:** All 10 ranking rows are always enabled for a deeper comparison of core and extended style signals.
- **Core / Extended score breakdown:** Results separate the baseline 5-row score from the extended 5-row score.
- **Extended Signal Insights:** Shows stability, context-shift, and adaptability indicators after analysis.
- **Export:** Saves the participant's assessment responses to a local JSON file. Add a participant name before exporting to include a sanitized name in the filename.
- **Import:** Restores responses from a previously exported JSON file.
- **Reset:** Clears all responses and starts over.
- **Print:** Uses the browser print dialog to create a printable version of the results while hiding controls.

## TeamPro controls (`TeamPro.html`)

- **Assessment tab:** Provides the same 10-row extended assessment flow for creating or exporting an individual profile from within the team app.
- **Upload Team Profiles:** Imports multiple participant JSON files exported from the profiler/assessment flow.
- **Team Dashboard:** Shows member distribution and aggregate style balance.
- **Interaction Lab:** Provides team-level recommendations based on uploaded profiles and composition.
- **Team Synergy:** Compares selected members and highlights likely collaboration strengths and tension patterns.
- **AI Coaching Feedback:** After individual analysis, supported Chrome builds can generate browser-based coaching feedback; unsupported browsers display a copyable prompt fallback.
- **AI Team Commentary:** After team upload, supported Chrome builds can generate executive-style team commentary, interaction maps, collaboration strengths, blind spots, conflict patterns, and conflict-prevention recommendations. Unsupported browsers display a copyable prompt fallback.
- **Privacy note:** AI features use the browser's built-in Prompt API/Gemini Nano when available. This repository does not send assessment data to an app server and does not require an API key. If users copy a fallback prompt into another tool, that external tool's privacy terms apply.
- **Print Executive Report:** Produces a boardroom-ready report layout with controls hidden for printing.

## Validation checklist (manual)

When updating either app, run:

```bash
python3 -m http.server 8000
```

Then verify the relevant workflow in a browser:

- Ranking interactions enforce unique values per row.
- Totals update correctly.
- Export/import works for JSON files.
- Results render correctly and print styles hide controls.
- `Profiler.html` shows all 10 rows immediately, has no Extended Deep-Dive toggle, and displays core/extended insights after analysis.
- `TeamPro.html` team upload works, dashboard metrics render, synergy comparisons update for selected members, and the Assessment tab keeps all 10 rows visible after reset.
- In supported Chrome desktop browsers, AI coaching/commentary can be generated; in unsupported browsers, copyable fallback prompts are shown.

## Roadmap

Potential improvements and next steps:

1. **Accessibility pass:** Add keyboard-first ranking workflows, ARIA labels/states for rank buttons, focus-visible styling, and a screen-reader-friendly results summary.
2. **Report exports:** Add optional printable/PDF report templates that include score tables, style narratives, AI coaching summaries when present, and facilitator notes.
3. **Assessment history:** Support local before/after snapshots so individuals and teams can compare coaching progress over time without adding a backend.
4. **Team facilitation depth:** Continue improving team-level prompts for conflict patterns, decision rituals, meeting norms, onboarding, and manager coaching conversations.
5. **AI experience hardening:** Add clearer browser support guidance for Chrome Prompt API/Gemini Nano and consider a non-AI coaching-template mode for locked-down environments.
6. **Data quality checks:** Warn users about incomplete imports, duplicate participant names in team uploads, and unusual score ties before analysis/export.
7. **Lightweight automated tests:** Add dependency-light tests for scoring, JSON import/export compatibility, Markdown feedback rendering, and prompt fallback behavior.

## License

This project is licensed under the MIT License. See [LICENSE](./LICENSE) for details.
