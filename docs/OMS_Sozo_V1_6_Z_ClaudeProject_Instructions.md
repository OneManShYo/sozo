# ONEMANSHYO Sozo [Beta V1_6_0] - CLAUDE PROJECT INSTRUCTIONS

**Version:** Beta V1_6_0  
**Date:** August 28, 2026  
**License:** GPL-3.0 (software)  
**Document Purpose:** Working protocols and project context for Claude development

---

## PROJECT

OMS Sozo is a single-file HTML visualizer for Apple Music Understanding analysis, companion to OMS Dojo. Built solo by Wes Smith (ONEMANSHYO). GPL-3.0 software. Not a commercial product.

## PRINCIPLES

- **Single-file philosophy** — no external dependencies, no build step, no frameworks. Chrome-targeted.
- **Dojo-exact audio model** — `new Audio()` + `createMediaElementSource`, `decodeAudioData` waveform, playhead via rAF.
- **AMU JSON is the contract** — the sidecar schema is versioned and first-class; both `omsanalyze` and the renderer depend on it.
- **Never "VJ"** — it's "DJing with live reactive visuals."
- **Analysis is Apple-only; the viewer runs anywhere.** Never imply the browser can run Music Understanding.
- **Audio is an external reference, not part of the app.** No music-legal carve-out language; a plain copyright credit only.

## VERSION DISCIPLINE

- Format `V#_#_#`, underscores everywhere. Keep the "Beta" label.
- Each iteration: edit → validate JS → bump filename → sync into repo → re-zip → present HTML + repo zip.
- New version files for iterations; bug fixes edit in place.

## BUILD PROTOCOL

- Make surgical changes; don't touch unrelated code.
- Validate the single `<script>` block parses before shipping.
- For large base64-containing edits, prefer Python over sed/str_replace.

## PUBLISH (matches Dojo)

- Repo `sozo` under the `onemanshyo` org, public. Pages from `master`, root.
- `index.html` + named build copy + `CNAME` (sozo.onemanshyo.com) + `.gitignore`.
- GPL-3.0 header comment; keep the "Beta" version label in title/header.
- Scrub any legacy names from contents, not just filenames.

---

**END OF CLAUDE PROJECT INSTRUCTIONS**
