# Cowork protocol

How a human and Claude should share a short so the skill does not collapse into "just write a spooky script."

## Roles

**Human (writer / director)**
- Owns premise, tone refs, production box, and every gate sign-off
- Cuts lines the model is proud of
- Decides the final image and the forbidden explanation
- Never lets the model invent story at Gate 7

**Agent (Claude with this skill)**
- Fills worksheets before pages
- Enforces bans, page count, and value turns
- Quotes bad dialogue instead of quietly polishing it
- Writes files into `projects/<slug>/`

## One film = one folder

```bash
cp -R projects/_template projects/<slug>
```

`<slug>` is lowercase, hyphenated, stable. Example: `night-log`.

Do not start a second film in the same folder.

## Session start

The human pastes this (edit the slug):

```text
/psych-short-screenplay
Project: projects/<slug>/
Read 00-intake.md and any later files that exist.
Tell me which gate we are on. Do not skip ahead.
```

If files already exist, the agent continues from the first unsigned gate. It does not regenerate a signed sheet unless asked.

## Gate contract

Each gate has a **deliverable**, a **stop rule**, and a **sign-off line** the human writes into the file.

### Gate 0 — Intake
- Deliverable: `00-intake.md`
- Stop: missing production box or premise is fine; agent may propose, must mark `PROVISIONAL`
- Sign-off: `SIGNED Gate 0 — YYYY-MM-DD — <name>`

### Gate 1 — Locked Sheet
- Deliverable: `01-locked-sheet.md`
- Stop: no beats until signed
- Fail tests: generic logline, antagonist whose only job is fear, no clock
- Sign-off: `SIGNED Gate 1 — YYYY-MM-DD — <name>`

### Gate 2 — Beats
- Deliverable: `02-beats.md`
- Stop: no scene draft until signed
- Fail tests: a beat with no irreversible change, more than 10 beats, feature-shaped B-story
- Sign-off: `SIGNED Gate 2 — YYYY-MM-DD — <name>`

### Gate 3 — Draft
- Deliverable: `03-draft.fountain`
- Stop: agent may ask about one stuck scene; it does not rewrite the sheet
- Fail tests: >12 pages, theme said aloud, shot jargon in action lines
- Sign-off: `SIGNED Gate 3 — YYYY-MM-DD — <name>`

### Gate 4 — Punch-up
- Deliverable: updated `03-draft.fountain` plus a short offender list in `notes.md`
- Stop: two passes max unless human asks for a third
- Sign-off: `SIGNED Gate 4 — YYYY-MM-DD — <name>`

### Gate 5 — Cut
- Deliverable: `04-cut.fountain`
- Rule: no new plot. Print page count before / after
- Sign-off: `SIGNED Gate 5 — YYYY-MM-DD — <name>`

### Gate 6 — Critique
- Deliverable: six bullets in `notes.md` against the quality bar
- Human chooses: another cut, a targeted rewrite, or lock
- Sign-off: `LOCKED SCRIPT — YYYY-MM-DD — <name>` before Gate 7

### Gate 7 — Shots (optional)
- Deliverable: `05-shots.md`
- Rule: continuity header on every shot. No new story. 8–15s.
- Sign-off: `SIGNED Gate 7 — YYYY-MM-DD — <name>`

## Just-go mode

The human may say `just go` once. The agent then runs Gates 1–3 + 6 in one reply **and still writes the files**. The human must still sign before Gate 7.

## Revision rules

- "Make it scarier" is not a note. Translate it into a withhold, a clock, or a corrupted procedure.
- "Add a monster" is a genre change. Re-run Gate 1.
- "Add a location" needs a production-box update first.
- If the human pastes a scene, punch it in place. Do not regenerate the film around it.

## What not to do together

- Do not brainstorm 12 loglines after a sheet is signed
- Do not mix Fountain and shot prompts in the same pass
- Do not use the agent as a coverage service and a writer in the same message without saying which hat
- Do not store secrets, cast personal data, or unreleased partner scripts in this public repo

## Suggested loop

1. Human: intake + tone refs (films, not adjectives)
2. Agent: Locked Sheet
3. Human: kill one field, keep the rest
4. Agent: 8–10 beats
5. Human: mark `CUT CANDIDATE` beats
6. Agent: draft
7. Human: read aloud
8. Agent: punch-up + cut
9. Human: lock
10. Agent: shot pack only if you are going to generate picture
