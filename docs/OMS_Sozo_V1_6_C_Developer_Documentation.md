# ONEMANSHYO Sozo [Beta V1_6_0] - DEVELOPER DOCUMENTATION

**Version:** Beta V1_6_0  
**Date:** August 28, 2026  
**License:** GPL-3.0 (software)  
**Document Purpose:** Technical implementation reference for V1_6_0

---

## ARCHITECTURE

Single-file HTML application. No build step, no external dependencies, no frameworks. Chrome-targeted. All CSS and JS inline in one document, consistent with the ONEMANSHYO single-file philosophy.

Two cooperating pieces:

1. **`omsanalyze`** (Swift CLI, separate `analyzer/` folder) — runs Apple's Music Understanding framework on an Apple device (macOS 26+ / iOS 26+), producing a JSON analysis sidecar. Not distributable as a running service; Apple's framework only executes on Apple's OS.
2. **Sozo** (this HTML app) — reads that JSON sidecar plus the audio and renders a synchronized timeline. Platform-agnostic; runs in any modern browser.

## DATA MODEL

`applyData(d)` normalizes either a flat sidecar or Apple's nested `SessionResult`. Derived module-level state: `bars`, `secs` (sections), `segs` (segments), `phr` (phrases), `bar` (bar duration in seconds), `len` (track length). Beats are derived from bars (4 subdivisions).

The JSON tab renders the true `SessionResult` shape via `toAppleShape()` with alphabetical field ordering (instrumentActivity, key, loudness, pace, rhythm, structure).

## AUDIO + PLAYBACK

Dojo's exact model: `new Audio()` + `URL.createObjectURL` + `createMediaElementSource → destination`; `decodeAudioData` for the static waveform; playhead read from `audioElement.currentTime` via `requestAnimationFrame`. Waveform uses Dojo's `drawAudioWaveform` RMS-bar algorithm.

## AUTO-LOAD (GitHub Pages)

On `http(s)`, an IIFE fetches the active track's co-located `./examples/{stem}.json` and `./examples/{stem}.mp3` and streams them automatically. On `file://`, fetch is blocked, so it falls back to the load buttons.

## TRACK REGISTRY (V1_6_0)

`TRACKS` is an array of track objects (`id`, `name`, `stem`, `meta`). `renderTrackPills()` builds the selector; `selectTrack(id)` swaps analysis + audio. Adding a track = add one object + drop its `.json`/`.mp3` in `examples/`.

## TIMELINE

Single canvas, lane layout: waveform, sections, segments, phrases, bars/beats, loudness, playhead. Sections/segments/phrases are clickable — `laneAt(y)` selects the lane, `find()` the block; selection locks + highlights and seeks.

## DEMO SYNTH (disabled)

A Web-Audio oscillator engine that sonifies markers when no audio is loaded, gated behind `DEMO_ENABLED=false` and a hidden `#demoSynthWrap`. Retained for future use.

---

**END OF DEVELOPER DOCUMENTATION**
