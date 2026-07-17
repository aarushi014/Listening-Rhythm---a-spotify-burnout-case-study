# Listening Rhythm
### A UX/Product Case Study: Listener Burnout Detection for Spotify
**Aarushi Singh**
*Concept case study — not an official Spotify product*

---

## 1. Executive Summary

No — or maybe one or two — published case studies currently document Spotify detecting **listener burnout** specifically. The closest real research is the University of Bristol's *Mood Music* study, which linked Spotify streaming history to depression, anxiety, and wellbeing scores across 171 students — but nothing brings this out as an in-app feature.

This case study is meant to fill that gap. It proposes **Listening Rhythm**, a passive, opt-in wellbeing signal built entirely from listening *behavior* (not lyrics analysis, not self-report, not biometric data) that surfaces gentle, non-diagnostic nudges when a user's patterns resemble burnout: late-night binge sessions, rising skip rates, narrowing genre diversity, and looping the same tracks — often ones that are low in energy or fall under a slow, sad genre.

The design is built around one single hard constraint: **a music app should never play therapist — it should be there to make a user feel light-hearted.** Every decision below — copy, visual language, escalation path — is shaped by that constraint.

---

## 2. Problem Framing

### Why this belongs on a music platform
People already use music as an unconscious mood regulator. Research on stress recovery has shown that self-selected music listening after stressful events groups into different patterns — calmer, sadder, more minor-key tracks — that differ measurably from baseline listening. Spotify already has this signal for every user, but beyond recommendations, it doesn't do anything with it.

### Why "burnout," specifically
Burnout is behavioral before it's clinical. It shows up as:
- **Escape-listening** — long, late-night sessions with minimal engagement (no skips, no searches, just letting it run)
- **Numbing loops** — repeating the same 3–5 tracks for days
- **Energy collapse** — a sustained drop in tempo/energy/valence of chosen tracks
- **Fragmented attention** — rising skip rate, shorter session length, more genre-switching

None of these prove burnout on their own. But as a **pattern**, they're a legitimate, non-invasive signal — closer to how a smartwatch flags irregular sleep than to a diagnosis.

### The trap to avoid
The obvious failure mode is a feature that says "You seem depressed" — presumptuous, clinical, creepy, and panic-inducing at platform scale. The design must earn trust by staying **descriptive, not diagnostic** — reflecting listening patterns back to the user, never naming a mental state for them.

---

## 3. Research Grounding

| Source | Relevance |
|---|---|
| **Mood Music** (University of Bristol, EMA + Spotify streaming history + PHQ-9/GAD-7/SWEMWBS, n=171) | Confirms streaming metadata correlates with real-time mood; supports using listening data as a *proxy signal*, not a diagnostic tool |
| Stress-recovery listening studies | Shows audio-feature shifts (energy, valence, tempo) are a measurable, real phenomenon post-stress — the technical basis for a "rhythm" signal |
| Public playlist analysis (search terms like "burnout," "overthinking," "de-stress") | Confirms users already self-label listening by emotional state, suggesting language like "decompress" and "reset" will feel native rather than clinical |

**Design implication:** the feature should read signals people are already using implicitly (they already build "de-stress" playlists) rather than inventing a new clinical term.

---

## 4. Persona

**Priya, 29, product designer.**
A Premium user who listens to music for 3+ hours a day. For the last few weeks she's been going to bed later, her "Discover Weekly" engagement has dropped, and she's been replaying the same lo-fi playlist every night instead of skipping through it like she used to. She hasn't consciously noticed any of this. She would be irritated by a pop-up asking "Are you okay?" — but might appreciate a quiet, optional insight, on her own terms, that she can dismiss in one tap.

Priya is the target: **not someone in crisis**, but someone in a slow behavioral drift who has no reason to notice it herself — or who is somehow, knowingly, avoiding noticing this shift in her own pattern.

---

## 5. Ethical Guardrails (non-negotiable constraints on the design)

1. **Opt-in only**, off by default. No passive shipping of a "we noticed you seem stressed" feature to 600M+ users without consent — this could create panic among users.
2. **Never name a clinical state.** No "depression," "burnout," or "anxiety" labels attached to the user. Only describe *behavior* ("your late-night sessions are up") and let the user draw their own conclusion — this may also help them realize what they've been doing over the past few days.
3. **No push notifications for this.** It lives in-app, checked only when the user opens the app — never an interruption.
4. **One-tap exit at every step.** Dismiss, mute for 30 days, or turn off entirely — always visible, never hidden in settings or behind multiple three-dot menus.
5. **A support resource is offered, never forced.** If a user chooses to dig deeper, options like grounding exercises or, if they ask, professional resources are one tap away — but never inserted automatically or repeatedly. Let users be their own guardians.
6. **No data leaves the feature.** Not shared with advertisers, not used to target ads — stated explicitly in the opt-in screen, since trust is the entire foundation for this feature.

---

## 6. The Feature: "Listening Rhythm"

A single visual metaphor carries the whole feature: **your listening as a rhythm/pulse.** Steady, evenly-spaced pulses = a stable pattern. Clustered, late, erratic pulses = a shifting one. It's the same metaphor on every screen, so the feature never needs to explain itself twice.

### Signals tracked (all passive, all already-collected metadata)
- Session start times (late-night clustering)
- Skip rate trend (7-day rolling average vs. personal baseline)
- Repeat-track ratio (same track/playlist looped vs. personal baseline)
- Audio-feature drift (average energy/valence/tempo of chosen tracks vs. personal baseline)

Everything is **relative to the user's own baseline** — never compared to other users. This avoids both the creepiness of population-level profiling and the inaccuracy of one-size-fits-all thresholds.

### User Flow

```
Discover tab (existing)
      │
      ▼
[Opt-in card, shown once] ── "Not now" ──▶ never shown again unless user seeks it out
      │ "Try it"
      ▼
Passive tracking begins (invisible, no UI change)
      │
      ▼
Pattern shift detected over rolling window
      │
      ▼
[Quiet insight card] appears at bottom of Home feed (not a notification)
      │
      ├── "Not now" ──▶ dismissed, resurfaces no sooner than +14 days
      ├── "Tell me more" ──▶ Weekly Rhythm report
      └── (ignored) ──▶ disappears after this session, no nagging
                              │
                              ▼
                  Weekly Rhythm report (opt-in deep dive)
                              │
                              ├── "Reset playlist" (mood-lift suggestions)
                              ├── "Just data, thanks" (closes, no action)
                              └── "I'd like support resources" ──▶ optional, user-initiated only
```

---

## 7. Key Screens

See the accompanying interactive mockup for the four core screens:
1. **Opt-in card** — plain-language consent, states exactly what is and isn't tracked
2. **Home feed insight card** — one line, one visual, two buttons, easily ignorable
3. **Weekly Rhythm report** — the full behavioral picture, framed as data, not diagnosis
4. **Reset playlist** — the one actionable output, turning every insight into something useful immediately

---

## 8. Success Metrics

| Metric | What it tells us |
|---|---|
| Opt-in rate | Whether the concept is trusted enough to try |
| Dismiss-without-return rate | Whether the insight card feels like nagging |
| "Reset playlist" save rate | Whether the feature offers real value, not just surveillance |
| Opt-out rate after first insight | The clearest signal of whether tone/trust failed |
| Session length *after* engaging with a Reset playlist | Whether the feature actually helps, however loosely defined |

We deliberately exclude clinical detection "accuracy" as a success metric. The feature is intended to help users reflect on their listening patterns and overall wellbeing, not to provide medical assessments or burnout diagnoses.

---

## 9. Risks & Open Questions

- **False positives at scale**: a user who has simply started a new night-shift job will trigger the same signals as someone withdrawing. The copy must stay behavioral ("your listening times have shifted") rather than interpretive ("you seem burnt out") so a wrong guess doesn't feel invasive.
- **Regulatory exposure**: even non-clinical wellbeing inference from behavioral data increasingly draws scrutiny (EU AI Act "emotion inference" provisions, for one). This would need real legal review before ship.
- **Trust is the whole product.** If this ever feels like it's profiling users for ad targeting — even by rumor — the feature dies overnight. The "no data leaves this feature" guarantee has to be real and independently auditable, not just a line of copy.

---

## 10. Why This Belongs in a Portfolio

This case study deliberately treats the hardest part of the problem — ethics — as the core design challenge, rather than an afterthought. A simpler approach might be to recommend a mood-boosting playlist whenever a user feels sad or emotional. But the real challenge here is to design a feature that genuinely supports users instead of making Spotify feel like it's making assumptions about someone's mental health. Handling that balance is what makes this a meaningful product.
