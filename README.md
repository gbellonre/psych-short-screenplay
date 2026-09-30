# psych-short-screenplay

Claude skill pack for **8–12 minute psychological thriller-horror short films**.

It forces a Locked Sheet and beat sheet before pages, keeps the draft inside a production box (few actors, few rooms), bans on-the-nose dialogue, then optionally turns the approved script into Seedance / Kling shot prompts.

Repo: https://github.com/gbellonre/psych-short-screenplay

## What you get

- A Claude Code / Claude.ai **skill** (`skills/psych-short-screenplay/`)
- A **cowork protocol** so a human and an agent do not skip gates
- A **project template** for each short you write
- Optional **Gate 7** video prompts that must not invent new plot

This is a literary-first pack. It is not a vertical-drama factory and not a slasher generator.

## Folder structure

```text
psych-short-screenplay/
├── README.md
├── COWORK.md
├── LICENSE
├── .claude-plugin/plugin.json
├── skills/psych-short-screenplay/
│   ├── SKILL.md                 # agent instructions
│   ├── CHANGELOG.md
│   ├── evals/
│   ├── references/              # loaded per gate
│   ├── examples/
│   └── assets/                  # copy-paste templates
└── projects/
    └── _template/               # duplicate per film
        ├── 00-intake.md
        ├── 01-locked-sheet.md
        ├── 02-beats.md
        ├── 03-draft.fountain
        ├── 04-cut.fountain
        ├── 05-shots.md
        └── notes.md
```

## Setup

### 1. Clone

```bash
git clone https://github.com/gbellonre/psych-short-screenplay.git
cd psych-short-screenplay
```

### 2. Install the skill — Claude Code

**This repo as a plugin (recommended)**

From Claude Code:

```text
/plugin marketplace add gbellonre/psych-short-screenplay
/plugin install psych-short-screenplay@psych-short-screenplay
```

If marketplace install fails, copy the skill into your user skills folder:

```bash
mkdir -p ~/.claude/skills
cp -R skills/psych-short-screenplay ~/.claude/skills/psych-short-screenplay
```

Restart Claude Code. Check with `/skills`. Invoke with `/psych-short-screenplay`.

**Project-only install** (does not affect other repos):

```bash
mkdir -p .claude/skills
cp -R skills/psych-short-screenplay .claude/skills/psych-short-screenplay
```

### 3. Install the skill — Claude.ai desktop

1. Zip the inner skill folder (not the whole repo):

```bash
cd skills
zip -r psych-short-screenplay.skill.zip psych-short-screenplay
```

2. Claude desktop → **Customize → Skills** → upload the zip.
3. Enable code execution / skills if your plan requires it.

### 4. Start a film

```bash
slug=night-log
cp -R projects/_template "projects/$slug"
```

Open `projects/$slug/00-intake.md`, fill what you know, then in Claude:

```text
/psych-short-screenplay
Read projects/night-log/00-intake.md and run Gate 1 only.
```

Full gate order and roles: [COWORK.md](COWORK.md)

## First prompt

```text
/psych-short-screenplay

8–10 minute hybrid psychological thriller-horror short.
Production box: 2 actors, 1 interior, night, contemporary.
Tone refs: A Ghost Story (quiet), The Invitation (social pressure),
The Killing of a Sacred Deer (moral trap). No jump scares.

Premise: [one sentence]
Wait after the Locked Sheet unless I say just go.
```

## Gates

| Gate | File | Who signs off |
|---|---|---|
| 0 Intake | `00-intake.md` | Human |
| 1 Locked Sheet | `01-locked-sheet.md` | Human |
| 2 Beats | `02-beats.md` | Human |
| 3 Draft | `03-draft.fountain` | Human + agent |
| 4 Punch-up | same draft | Agent, human spots lines |
| 5 Cut | `04-cut.fountain` | Human |
| 6 Critique | `notes.md` | Human decides next pass |
| 7 Shots (optional) | `05-shots.md` | Only after cut is locked |

## Pairing with other packs

Optional: install [jtydhr88/screenwriting-skills](https://github.com/jtydhr88/screenwriting-skills) beside this skill for extra dramaturgy (`sw-dialogue`, `sw-scene-craft`, `sw-genre-anatomy`). This pack stays the short-film runtime leash and psych-horror engine.

## License

MIT. Use it, fork it, steal the Locked Sheet.
