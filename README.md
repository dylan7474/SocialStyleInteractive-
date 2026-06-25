# Social Style Preferences Interactive Assessment

A lightweight, single-page web app for running a **Social Style Preferences** self-assessment based on the Bolton & Bolton model. Participants rank behavioral traits across five sets to reveal their dominant communication style across four quadrants:

- **Driver**
- **Expressive**
- **Amiable**
- **Analytical**

The app calculates totals in real time, visualizes outcomes, and provides profile guidance for interpreting and applying the results.

## Application variants

This repository includes the following static HTML entry points:

- **`index.html`**: core individual self-assessment flow (single participant).
- **`profile.html`**: individual self-assessment with the optional Extended Deep-Dive from `team.html`, including 10-set scoring, core/extended score breakdowns, stability, context-shift, and adaptability insights.
- **`profiler.html`**: individual extended-only profile deep-dive with all 10 ranking sets always enabled and no Extended Deep-Dive toggle.
- **`profile-ai.html`**: AI-enabled profile deep-dive that adds optional on-device coaching feedback through Chrome's built-in Prompt API / Gemini Nano when available, with generated Markdown rendered into styled report sections and a copyable fallback prompt for unsupported browsers.
- **`team.html`**: expanded “Social Style Pro” experience with tabs for:
  - individual assessment,
  - team dashboard (multi-file upload and aggregate view),
  - interaction lab,
  - peer-to-peer synergy analysis.
- **`team-ai.html`**: AI-enabled team experience that keeps the `team.html` workflow and adds an executive-style AI Commentary report for generated member leadership notes and team dynamics commentary using Chrome's built-in Prompt API / Gemini Nano when available, with a copyable AI prompt fallback for unsupported browsers.
- **`TeamPro-ai.html`**: AI-enabled extended team lab with all 10 Assessment rows always shown, individual AI Coaching Feedback on the Assessment tab, and team AI Commentary / executive reporting for uploaded profile JSON files.
- **`TeamPro.html`**: cloned from `TeamPro-ai.html` for the TeamPro workflow, with enhanced AI team reporting that adds a dedicated interaction map, collaboration strengths, weaknesses/blind spots, potential conflict patterns, and conflict-prevention recommendations.

Use whichever file best matches your facilitation context.

## Build / Run Instructions

Because this project is static HTML/CSS/JS, there is no package install or compilation required.

### Option 1: Open directly
1. Clone this repository.
2. Open `index.html`, `profile.html`, `profiler.html`, `profile-ai.html`, `team.html`, `team-ai.html`, or `TeamPro-ai.html` in a modern browser.

### Option 2: Serve locally (recommended)
Using Python:

```bash
python3 -m http.server 8000
```

Then open one of:

```text
http://localhost:8000/index.html
http://localhost:8000/profile.html
http://localhost:8000/profiler.html
http://localhost:8000/profile-ai.html
http://localhost:8000/team.html
http://localhost:8000/team-ai.html
http://localhost:8000/TeamPro-ai.html
http://localhost:8000/TeamPro.html
```

## Basic controls

### Individual assessment (`index.html`, `profile.html`, `profiler.html`, and `profile-ai.html`)

- **Rank buttons (1–4):** For each row, assign each rank exactly once across the four traits.
- **Total Scores:** Auto-updates as you complete each set.
- **Export:** Saves your current assessment responses to a local JSON file. In `profile.html`, `profiler.html`, and `profile-ai.html`, add your name before exporting to include a sanitized version of it in the filename.
- **Import:** Restores responses from a previously exported JSON file.
- **Reset:** Clears all responses and starts over.
- **Print:** Use the browser print dialog to generate a printable version of results. In `profile-ai.html`, the print report is formatted as a compact business-ready report with deliberate page breaks so the profile overview, AI Coaching Feedback, and style reference sections each start on their own page and avoid mid-section splits when printed.

### Profile Deep-Dive controls (`profile.html`, `profiler.html`, and `profile-ai.html`)

- **Enable Extended Deep-Dive:** In `profile.html` and `profile-ai.html`, adds 5 more ranking sets (10 total) while preserving any existing core answers. In `profiler.html`, Extended Deep-Dive is always on and the toggle is removed.
- **Core / Extended score breakdown:** Results separate the baseline 5-set score from the extended 5-set score.
- **Extended Signal Insights:** Shows the most stable style signal, biggest context shift, and an adaptability range percentage after analysis.
- **Extended import detection:** Importing a JSON file with rows 06–10 automatically enables Extended Deep-Dive mode in toggle-based profile pages. `profiler.html` always imports into the 10-set extended flow.

### AI profile controls (`profile-ai.html`, `TeamPro-ai.html`, and `TeamPro.html` Assessment tab)

- **Generate AI Feedback:** After generating the standard kite analysis, checks for Chrome's built-in Prompt API and uses an on-device language model to draft concise coaching feedback from the completed scores. Generated Markdown is rendered into styled report sections so headings, bullets, numbered actions, and emphasis match the rest of the results page and printed business report.
- **Copy AI Prompt fallback:** If the Prompt API is unavailable, cannot be checked, or on-device generation fails, the same button changes to **Copy AI Prompt** and displays an AI-ready prompt that can be pasted into another AI tool. The fallback prompt is shown as plain text to make copying easy.
- **Privacy note:** AI feedback runs in the browser through Chrome/Gemini Nano when supported; this page does not send the assessment to an app server or require an API key. The fallback prompt is only copied/displayed locally until the user pastes it elsewhere.
- **Availability note:** If Chrome reports the model as downloadable or downloading, the Generate AI Feedback button stays enabled and shows download progress while Gemini Nano is installed.
- **TeamPro Assessment note:** `TeamPro-ai.html` keeps the Assessment tab in always-on 10-row Extended Deep-Dive mode without showing the previous always-enabled notice, then uses the same AI feedback flow after analysis.

### Team-specific controls (`team.html`, `team-ai.html`, and `TeamPro-ai.html`)

- **Upload Team Profiles:** Import multiple participant JSON files at once.
- **Team Dashboard:** Review member distribution and aggregate style balance.
- **Interaction Lab:** Review recommendations based on team composition.
- **Team Synergy:** Compare any two members and inspect likely collaboration/tension patterns.
- **Extended Deep-Dive:** Add 5 extra ranking sets in `team.html` or `team-ai.html` to compare baseline style signals vs contextual style shifts. `TeamPro-ai.html` always shows all 10 Assessment rows.
- **Reset Form (team assessment):** Clears all ranked rows and hides current analysis results. In `team.html` and `team-ai.html`, reset returns to baseline 5-row mode; in `TeamPro-ai.html` and `TeamPro.html`, reset keeps the 10-row Assessment visible.

### AI team commentary controls (`team-ai.html`, `TeamPro-ai.html`, and `TeamPro.html`)

- **Generate AI Commentary:** After uploading team profile JSON files, creates individual member profile notes plus overall team dynamics commentary. In `TeamPro.html`, the generated prompt/report also requests a team interaction map, collaboration strengths, weaknesses/blind spots, potential conflict patterns, and conflict-prevention recommendations, with interaction and conflict commentary framed around named team members and working pairs rather than generic style-only descriptions.
- **Copy AI Prompt fallback:** If Chrome Prompt API/Gemini Nano is unavailable, the same control displays an AI-ready prompt that can be copied into another AI tool.
- **Privacy note:** Supported Chrome builds run the commentary in-browser with the built-in on-device model; this repository does not send team data to an app server or require an API key.
- **Print Executive Report:** The AI Commentary tab uses a boardroom-ready report layout with an executive cover band, summary metric cards, facilitator guidance, styled Markdown output, and print-specific formatting that hides controls and avoids awkward section splits.

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
- (`team.html`, `team-ai.html`, `TeamPro-ai.html`, and `TeamPro.html`) Multi-file upload works and team/synergy tabs populate correctly.
- (`profile.html`, `profile-ai.html`, `team.html`, and `team-ai.html`) Extended mode can be toggled on/off and shows additional insight cards after analysis. (`profiler.html`, `TeamPro-ai.html`, and `TeamPro.html`) Extended mode is always active, shows all 10 rows immediately, and has no Extended Deep-Dive toggle.
- (`profile-ai.html`, `TeamPro-ai.html`, and `TeamPro.html` Assessment tab) Chrome Prompt API availability status appears after analysis, AI feedback can be generated in a supported Chrome desktop browser, and unsupported browsers show the copyable fallback prompt.
- (`team-ai.html`, `TeamPro-ai.html`, and `TeamPro.html`) AI Commentary status appears after team upload, executive summary cards populate, generated member profiles/team dynamics commentary renders as a styled executive report in a supported Chrome desktop browser, unsupported browsers show the copyable fallback prompt, and Print Executive Report hides controls with professional pagination.

## Roadmap

Potential improvements and next steps:

1. **Accessibility pass:** Add keyboard-first ranking workflows, ARIA labels/states for rank buttons, focus-visible styling, and a screen-reader-friendly results summary.
2. **Report exports:** Add an optional printable/PDF report template that includes the kite chart, score table, primary style narrative, AI coaching summary when present, and facilitator notes.
3. **Assessment history:** Support local before/after snapshots so individuals and teams can compare coaching progress over time without adding a backend.
4. **Team facilitation depth:** Expand team-level prompts for conflict patterns, decision rituals, meeting norms, onboarding, and manager coaching conversations.
5. **AI experience hardening:** Add clearer browser support guidance for Chrome Prompt API/Gemini Nano, persist the copied fallback prompt state, and consider a non-AI coaching-template mode for locked-down environments.
6. **Data quality checks:** Warn users about incomplete imports, duplicate participant names in team uploads, and unusual score ties before analysis/export.
7. **Lightweight automated tests:** Add dependency-light tests for scoring, extended-mode toggles, JSON import/export compatibility, Markdown feedback rendering, and prompt fallback behavior.

## License

This project is licensed under the MIT License. See [LICENSE](./LICENSE) for details.
