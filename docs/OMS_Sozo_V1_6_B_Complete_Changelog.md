# ONEMANSHYO Sozo [Beta V1_6_0] - COMPLETE CHANGELOG

**Version:** Beta V1_6_0  
**Date:** August 28, 2026  
**License:** GPL-3.0 (software)  
**Document Purpose:** Full development history for V1_6_0

---

## V1_6_0 — Track selector + publish prep

- Renamed **TRACK** tab to **TRACKS**.
- Added a track-selector **pill row** above the summary, driven by a `TRACKS` registry. Each analyzed track is one object (name, file stem, metadata); pills render automatically and switch the whole view on click. Scaffolds a small multi-track demo (target 4–5 contrasting tracks) without turning Sozo into a library app.
- Pill shows the track title only.
- Header wordmark finalized to match Dojo: `ONEMANSHYO` (gradient) + `sozo app` (orange, lowercase) + `[Beta V1_6_0]`.

## V1_5_x — Copyright, tabs, demo synth

- Added plain track **copyright** line to the info box (`copyright © 1997–2026 Juice Night Out`).
- Removed music-legal carve-out language from the About tab; audio is treated as an externally referenced file, not part of the app.
- Removed the redundant `analyzed` row from track info; moved AMU/OS attribution into the ANALYSIS section header in light brackets.
- Added (then disabled, retained in code) a **demo synth** device strip — a chiptune stand-in that sonifies the analysis markers when no audio is present. Gated behind `DEMO_ENABLED`.
- Verified auto-load streaming of co-located `examples/` audio + JSON over http(s), matching GitHub Pages behavior.

## V1_4_x — Layout

- Merged cover art + song info into one shared bordered panel; shader canvas in a matching panel. Even 10px inset, symmetrical.
- Added **SUPPORT** tab (how it works / requirements / can it analyze live).

## V1_3_x — Structure interaction + choreography

- Segment and phrase blocks made clickable/lockable/highlightable like sections; click anywhere seeks.
- Strobe refined to fire on the last N beats of flagged phrases using the real beat grid; subtle ramping builds; spanning build across a phrase range with cut on the final beat.
- Outro crew thin-out (`REDUCE`) on section entry.

## V1_2_x — Timeline + stats

- Compressed top rows and RHYTHM; kept STRUCTURE full-height.
- Added ANALYSIS section header; matched ANALYSIS/RHYTHM card heights.
- Folded transport time + bar counter; removed footer status bar.

## V1_1_x — Content

- Multi-smiley spawn/chill/chime reactions driven by structure.
- ABOUT tab; Beatport metadata + embedded cover art; auto-load on Pages.

## V1_0_x — Foundation

- Initial single-file build. Dojo-exact audio model and waveform algorithm.
- AMU JSON tab rendering the true `SessionResult` shape.

---

**END OF CHANGELOG**
