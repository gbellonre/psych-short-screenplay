---
name: psych-short-screenplay
description: "Writes, rewrites, beats, and cuts 8-12 minute psychological thriller-horror short film screenplays in Fountain, then optional Seedance/Kling shot prompts. Use when the user asks for a short film script, screenplay, beat sheet, dialogue punch-up, or shot list in psychological thriller, psychological horror, elevated horror, dread, or quiet horror. Not for features, sitcoms, slashers, YouTube essays, or ad scripts."
type: workflow
lifecycle: active
---

# Psych Short Screenplay — 8–12 Minute Dread Film

Write a production-constrained short. Fear comes from perception, guilt, and contaminated reality. Do not draft pages before the Locked Sheet exists.

Read references only when the matching gate starts:
- Gate 1 → `references/locked-sheet.md`
- Gate 1 engine choice → `references/genre-lock.md`
- Gate 3–4 format / bans → `references/fountain.md` and `references/dialogue-bans.md`
- Gate 7 only → `references/shot-prompts.md`

## Defaults

| Knob | Default |
|---|---|
| Runtime | 8–12 min = 8–12 pages |
| Cast | 2–4 speaking roles |
| Locations | 1–3 |
| Format | Fountain |
| Ending | Ambiguity or moral trap allowed |
| Camera in script | Off unless asked |
| Dialogue | Subtext only |

## Hard stops

Fail and rewrite if any are true:

- Character names the theme or the fear
- Protagonist only reacts
- Antagonist has no private want
- Scene exists only to dump information
- Draft exceeds 12 pages without approval
- Last image is a scream, title card, or look-to-camera
- Shot jargon appears in the literary script (`CU`, `smash cut`, `we see`)

Full ban list: `references/dialogue-bans.md`

## Workflow

Stop at each gate unless the user said **just go**.

### Gate 0 — Intake

Collect only what is missing: premise, runtime, want, false belief, cost, final image, production box, tone refs (films not adjectives), engine.

If the user gives only a vibe, invent missing sheet items, mark them `PROVISIONAL`, continue.

### Gate 1 — Locked Sheet

Read `references/locked-sheet.md` and `references/genre-lock.md`. Output the Locked Sheet block. Do not write beats yet.

Fail the logline if a generic "person" can replace the protagonist.

### Gate 2 — Beat sheet

8–10 beats. One line each. Present tense. No dialogue. No camera.

```text
BEAT [#] — [page] — [location]
[Photographable change]
VALUE TURN: [from] → [to]
IRREVERSIBLE: [what cannot be undone] or [CUT CANDIDATE]
```

Required spine: crack → contamination → stay → deniable proof → midpoint flip → isolation earned → knife they walk into → final image.

After the sheet, list sags, the withheld fact, and the late reveal.

### Gate 3 — Scene draft

Read `references/fountain.md`. Expand only approved beats. Enter late, leave before the moral. Cap dialogue at ~40% of page. Plant one ordinary object that later turns unclean.

Per scene footer:

```text
TURN: [from] → [to]
WITHHELD: [x]
NOW FEARS: [x]
CUT IF IT EXPLAINS: "[quote]"
```

### Gate 4 — Dialogue punch-up

Read `references/dialogue-bans.md`. Quote offenders. Replace with physical task, wrong answer, delayed answer, or a line that means two things. Run twice if it still sounds like an LLM.

### Gate 5 — Cut to 70–85%

Cut or replace with existing action only. No new plot. Print page count before and after. Never pad back up.

### Gate 6 — Self-critique

Six bullets against the quality bar. Then stop.

### Gate 7 — Shot prompts (optional)

Only if the user asks for shots, Seedance, Kling, Runway, or a shot list. Read `references/shot-prompts.md`. Do not invent story. 8–15s per shot. Offscreen sound carries dread. What is withheld stays offscreen.

## Just-go pack

If the user says write it now, output in one response:

1. Locked Sheet
2. Beat sheet
3. Full Fountain draft
4. Six-bullet critique

Do not hide the sheet.

## Project files

When working inside a repo with `projects/`, write durable artifacts to:

```text
projects/<slug>/01-locked-sheet.md
projects/<slug>/02-beats.md
projects/<slug>/03-draft.fountain
projects/<slug>/04-cut.fountain
projects/<slug>/05-shots.md
```

Copy `projects/_template/` if the slug folder does not exist.

## Quality bar

Fail the draft if page 1 could be any genre, a stranger can explain the ending in one sentence, the protagonist is rescued, or the dialogue would still work as a podcast.
