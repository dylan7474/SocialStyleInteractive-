# Social Style Preferences Interactive Assessment

A lightweight, single-page web app for running a **Social Style Preferences** self-assessment based on the Bolton & Bolton model. Participants rank behavioral traits across five sets to reveal their dominant communication style across four quadrants:

- **Driver**
- **Expressive**
- **Amiable**
- **Analytical**

The app calculates totals in real time, visualizes outcomes, and provides profile guidance for interpreting and applying the results.

## What this application is

This project is a browser-based assessment tool intended for coaching, team development, and personal reflection. It is designed to be simple to run (no build step required) and easy to share as a static HTML file.

## Build / Run Instructions

Because this project is static HTML/CSS/JS, there is no package install or compilation required.

### Option 1: Open directly
1. Clone this repository.
2. Open `index.html` in a modern browser.

### Option 2: Serve locally (recommended)
Using Python:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Basic Controls

- **Rank buttons (1–4):** For each row, assign each rank exactly once across the four traits.
- **Total Scores:** Auto-updates as you complete each set.
- **Export:** Saves your current assessment responses to a local JSON file.
- **Import:** Restores responses from a previously exported JSON file.
- **Cloud Save / Load:** Available when Firebase config is present.
- **Reset:** Clears all responses and starts over.
- **Print:** Use the browser print dialog to generate a printable version of results.

## Roadmap

Short-term ideas for improving this app:

1. Add per-style development tips and suggested next actions.
2. Improve accessibility (keyboard navigation + ARIA labels for rank buttons).
3. Add multi-assessment comparison (before/after coaching snapshots).
4. Add optional report export (PDF summary with chart and key takeaways).
5. Add basic test coverage for score calculation and import/export validation.

## License

This project is licensed under the MIT License. See [LICENSE](./LICENSE) for details.
