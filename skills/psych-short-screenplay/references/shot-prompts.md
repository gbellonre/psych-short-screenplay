---
description: "Gate 7 shot notes and Seedance/Kling prompt packs. Read only when the user asks for shots or video prompts."
---

# Shot Prompts

Do not run this gate during the literary draft. No new plot. No explaining the ending in a prompt.

## Shot note

```text
SHOT [#] — [8-15s] — [INT/EXT] [PLACE] — [DAY/NIGHT]
IMAGE: [one frame; no camera brand]
MOTION: [one simple move or locked off]
SOUND: [what we hear that the picture does not show]
WITHHOLD: [what stays offscreen]
NEGATIVE: [gore, text, extra faces, jump scare, title card]
PROMPT: [single paragraph for the video model]
```

Cap shots so total time ≈ script runtime. A 10-minute short is not 80 shots. Prefer 25–45.

## Prompt rules

- One subject, one space, one action.
- Continuity anchors: wardrobe, practical light, era, weather.
- Dread = duration + offscreen sound + a small wrong detail.
- Do not write "scary" or "cinematic masterpiece."
- Do not put the Forbidden Explanation in the prompt.

## Model notes

**Seedance / similar text-to-video**
- 5–15 seconds. Locked-off or slow push. Practical interiors.
- End frame must be usable as the next shot's start.

**Kling**
- Same continuity sentence at the start of every prompt in a sequence.
- Avoid crowded faces. Two people max unless the script requires more.

**Shared continuity header** (repeat on every shot in a sequence):

```text
Continuity: [era], [location], [wardrobe], [key practical light], [unclean object state]
```

## Output files

Write `projects/<slug>/05-shots.md` as a numbered pack. Optionally add a plain list of `PROMPT` paragraphs only at the bottom for copy-paste into a model UI.
