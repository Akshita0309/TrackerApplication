# Tracker Apps

Two small, dependency-free web apps. Each is a single HTML file with its CSS and JavaScript inline.

| File | What it does |
|------|--------------|
| `research-tracker.html` | Track multiple projects, each split into sections and topics, with progress bars and notes. |
| `roadmap-builder.html` | Build a Now / Next / Later roadmap with drag-and-drop and a by-stream view. |

## Running

Open either file in a modern browser (double-click it). No build step, server or install is needed.

An internet connection is only used to load the Bricolage Grotesque font from Google Fonts. If it is unavailable, the apps fall back to the system font.

## Research Tracker

- **Projects:** switch from the dropdown at the top. Create one as blank, as a copy of the current project's sections (all topics reset to To do), or from the Gen AI starter plan.
- **Move on:** "Mark complete & move on" closes the current project and opens the next unfinished one. The same button reopens a completed project.
- **Sections and topics:** add, rename and delete both. Click a topic's status button to cycle To do, In progress, Done.
- **Notes:** the "..." button on a topic opens a notes box.
- **Export:** "Copy progress as Markdown" copies a checklist for the open project.
- **Reset:** "Reset to starter plan" replaces the open project's sections with the Gen AI starter plan (asks for a second click).

## Roadmap Builder

- **Items:** title, notes, timeframe (Now, Next, Later), status and stream. Click a card to edit or delete.
- **Drag and drop:** move cards between columns. In "By stream" view, dropping also changes the stream.
- **Streams:** colored workstreams, added from the box under the title. A stream can only be removed when it has no items.
- **Export and import:** "Export JSON" and "Import JSON" back up or share a roadmap. "Copy as Markdown" copies a readable summary.

## Data storage

Data is saved in the browser's `localStorage`, so it stays on your device and browser only. It does not sync across devices, and clearing site data erases it.

| App | localStorage key |
|-----|------------------|
| Research Tracker | `research-tracker-v2` (migrates data from `research-tracker-v1`) |
| Roadmap Builder | `roadmap-builder-v1` |

Note that browsers keep separate storage per location. A file opened from disk and the same file hosted online will not share data.

## Customizing

- **Starter content:** in `research-tracker.html`, edit the `starter()` function. In `roadmap-builder.html`, edit the initial `S` object.
- **Timeframes:** change the `LANES` array in `roadmap-builder.html`. Item lane ids must match.
- **Stream colors:** edit the `COLORS` array in `roadmap-builder.html`.
- **Theme:** colors are CSS variables on `:root` and follow the system light or dark setting.

## Hosting

Upload the HTML files to any static host (GitHub Pages, Netlify, an S3 bucket). Nothing else is required.
