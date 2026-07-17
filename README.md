
# Listening Rhythm
**Author:** Aarushi Singh

**A UX/product case study — listener burnout detection, reimagined for Spotify**

> Concept project. Not affiliated with, endorsed by, or built for Spotify AB. All Spotify names, colors, and UI conventions are referenced for design-critique purposes only.

---

## What this is

No published case study currently documents a real product detecting *listener* burnout from music-streaming behavior. Adjacent academic research exists, but nothing productizes it. This repo is that missing case study: a full problem framing, ethical constraints, feature design, and interactive UI mockups for **Listening Rhythm** — an opt-in, non-diagnostic wellbeing signal built entirely from passive listening behavior.

The design is built around one constraint that shapes every decision in it: **a music app should never play therapist.**

## Contents

| File | Description |
|---|---|
| [`case-study.md`](./case-study-(1).md) | Full write-up: problem framing, research grounding, persona, ethical guardrails, feature spec, user flow, success metrics, risks |
| [`listening-rhythm-mockup.html`](./listening-rhythm-mockup.html) | Self-contained, interactive HTML mockup of the four core screens — open directly in any browser, no build step |
| [`listening-rhythm-case-study.tex`](./listening-rhythm-case-study.tex) | LaTeX source of the case study, ready to paste into Overleaf or compile locally with `pdflatex` |
| [`listening-rhythm-case-study.pdf`](./Case-Study_Spotify-Burnout-Detector.pdf) | Compiled PDF of the above |

## Viewing the mockup

The mockup is a single static HTML file with no dependencies to install.

```bash
open listening-rhythm-mockup.html      # macOS
xdg-open listening-rhythm-mockup.html  # Linux
```

Or just double-click it / drag it into a browser tab. It renders four phone-frame screens side by side: opt-in, in-feed insight, weekly report, and the reset-playlist output — each with a short caption explaining the UX reasoning behind it.

## Compiling the case study PDF locally

```bash
pdflatex listening-rhythm-case-study.tex
pdflatex listening-rhythm-case-study.tex   # run twice to resolve page references
```

No packages beyond a standard TeX Live install are required (`xcolor`, `titlesec`, `enumitem`, `tabularx`, `booktabs`, `hyperref`, `fancyhdr`, `lastpage` — all bundled by default on Overleaf and most local distributions).

## The feature, in one paragraph

**Listening Rhythm** treats a user's own listening history as a rolling personal baseline — session timing, skip rate, repeat-track ratio, and average track energy/valence — and only surfaces a quiet, dismissible insight when that baseline shifts noticeably. It never names a clinical state ("depression," "burnout," "anxiety"); it only describes behavior ("your late-night sessions are up") and lets the user draw their own conclusion. It's opt-in, off by default, never sends a push notification, and offers a one-tap exit at every step.

## Background & research

This concept is grounded in real published research on music-listening behavior as a mental-health proxy, most directly:

- **Mood Music** (University of Bristol) — linked Spotify streaming history + Ecological Momentary Assessment + PHQ-9/GAD-7/SWEMWBS scores across 171 university students, finding streaming metadata correlates with real-time mood
- Stress-recovery listening research showing measurable audio-feature shifts (energy, valence, tempo) in self-selected music after stressful events

Full citations and discussion are in [`case-study.md`](./case-study-(1).md#3-research-grounding).

## Why the ethics section isn't an afterthought

The obvious version of this feature is "detect sad users, show them a mood-boosting playlist." The harder, more interesting design problem is doing that without the platform ever sounding like it's diagnosing you — because the moment a feature like this feels like profiling for ad targeting, even by rumor, it's dead. The [ethical guardrails](./case-study.md#5-ethical-guardrails) section treats that constraint as the actual design brief, not a compliance checkbox at the end.

## License

Case-study content and mockups are original work, shared for portfolio and educational purposes. Feel free to fork, reference, or adapt with attribution. Spotify's name and brand are used descriptively for a design critique and imply no affiliation.
