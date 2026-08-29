# ONEMANSHYO Sozo [Beta V1_6_0] - USER GUIDE

**Version:** Beta V1_6_0  
**Date:** August 28, 2026  
**License:** GPL-3.0 (software)  
**Document Purpose:** Complete user guide for V1_6_0

---

## 1. WHAT SOZO IS

Sozo is a visualizer for **Apple Music Understanding** (AMU). AMU is an Apple framework (macOS 26+ / iOS 26+) that analyzes a track entirely on-device and returns six time-aligned dimensions in a single `SessionResult`: rhythm (beats, bars, BPM), key (as ranges that can change across a track), structure (sections / segments / phrases), loudness (LUFS), pace, and instrument activity.

Sozo doesn't run the analysis — it *shows* it. You analyze a track once with the companion `omsanalyze` CLI to produce a JSON sidecar, then Sozo plays that sidecar back against the audio so you can see and hear exactly what Apple's analysis found.

## 2. THE TABS

- **TRACKS** — the main view: track selector pills, cover + info, the reactive visual, transport, the ANALYSIS stats, the STRUCTURE timeline, and the RHYTHM counts.
- **JSON** — the raw Music Understanding `SessionResult`, syntax-highlighted, copy/download.
- **SUPPORT** — how it works, requirements, and why it can't analyze arbitrary audio live in the browser.
- **ABOUT** — background on the tool, AMU, and the ONEMANSHYO project.

## 3. LOADING A TRACK

On the published web version, the page auto-loads the selected track's analysis and audio. Locally (opened as a file) or to use your own material, click **load audio** and **load .json**.

## 4. THE STRUCTURE TIMELINE

The timeline stacks: waveform, sections, segments, phrases, bars/beats, loudness, and the playhead. Hover to inspect. Click any section, segment, or phrase block to lock and highlight it — and to seek there. This makes the visual an authoring surface: point at a moment, name what should happen.

## 5. REQUIREMENTS

- **To analyze a track:** a Mac or iPhone/iPad on macOS 26+ / iOS 26+, plus the `omsanalyze` CLI. Run once per track; it writes a portable JSON sidecar.
- **To view / perform:** any modern browser (Chrome recommended), any OS.

## 6. CAN IT ANALYZE ANY SONG LIVE?

Not in the browser. Music Understanding isn't reachable from JavaScript on any platform — not even Safari on a Mac — so Sozo reads analysis produced ahead of time. The upside: that analysis ships as open, portable JSON anyone can use.

---

## APPENDIX A — MUSIC & COPYRIGHT

The demonstration track "Ain't No Trick" (Wes Smith & BumpR StickR, Juice Night Out, JNO2408) is an externally referenced audio file, not part of the software. Copyright © 1997–2026 Juice Night Out. The GPL-3.0 license applies to the software only.

---

**END OF USER GUIDE**
