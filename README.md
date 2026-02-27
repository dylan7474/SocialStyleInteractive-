# Social Style Preferences Interactive Assessment

A lightweight, single-page web app for running a **Social Style Preferences** self-assessment based on the Bolton & Bolton model. Participants rank behavioral traits across five sets to reveal their dominant communication style across four quadrants:

- **Driver**
- **Expressive**
- **Amiable**
- **Analytical**

The app calculates totals in real time, visualizes outcomes, and provides profile guidance for interpreting and applying the results.

## Application variants

This repository now includes two static HTML entry points:

- **`index.html`**: core individual self-assessment flow (single participant).
- **`team.html`**: expanded “Social Style Pro” experience with tabs for:
  - individual assessment,
  - team dashboard (multi-file upload and aggregate view),
  - interaction lab,
  - peer-to-peer synergy analysis.

Use whichever file best matches your facilitation context.

## Build / Run Instructions

Because this project is static HTML/CSS/JS, there is no package install or compilation required.

### Option 1: Open directly
1. Clone this repository.
2. Open either `index.html` or `team.html` in a modern browser.

### Option 2: Serve locally (recommended)
Using Python:

```bash
python3 -m http.server 8000
```

Then open one of:

```text
http://localhost:8000/index.html
http://localhost:8000/team.html
```

## Basic controls

### Individual assessment (both versions)

- **Rank buttons (1–4):** For each row, assign each rank exactly once across the four traits.
- **Total Scores:** Auto-updates as you complete each set.
- **Export:** Saves your current assessment responses to a local JSON file.
- **Import:** Restores responses from a previously exported JSON file.
- **Reset:** Clears all responses and starts over.
- **Print:** Use the browser print dialog to generate a printable version of results.

### Team-specific controls (`team.html`)

- **Upload Team Profiles:** Import multiple participant JSON files at once.
- **Team Dashboard:** Review member distribution and aggregate style balance.
- **Interaction Lab:** Review recommendations based on team composition.
- **Team Synergy:** Compare any two members and inspect likely collaboration/tension patterns.
- **Extended Deep-Dive (optional):** Add 5 extra ranking sets in `team.html` to compare baseline style signals vs contextual style shifts.
- **Reset Form (team assessment):** Clears all ranked rows, returns to baseline 5-row mode, and hides current analysis results.

## Validation checklist (manual)

When updating either app, run:

```bash
python3 -m http.server 8000
```

Then verify:

- Ranking interactions enforce unique values per row.
- Totals update correctly.
- Export/import still works for JSON files.
- Results render correctly and print styles hide controls.
- (`team.html`) Multi-file upload works and team/synergy tabs populate correctly.
- (`team.html`) Extended mode can be toggled on/off and shows additional insight cards after analysis.

## Roadmap

Short-term ideas for improving this app:

1. Improve accessibility (keyboard navigation + ARIA labels for rank buttons).
2. Add optional report export (PDF summary with chart and key takeaways).
3. Add multi-assessment history tracking (before/after coaching snapshots).
4. Expand team-level facilitation prompts for conflict and decision rituals.
5. Add lightweight test coverage for score calculation and import/export validation.

## License

This project is licensed under the MIT License. See [LICENSE](./LICENSE) for details.
