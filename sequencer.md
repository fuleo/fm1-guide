---
layout: page
title: Sequencer
permalink: /sequencer.html
---

The FM-1 has **16 patterns of 16 steps**. V15 added long notes, a step count per pattern, **Chain** and **voice binding**. This page covers the basics, then builds a short 3-part song.

> **How sure is this?** M-VAVE has published no V15 manual. Where each V15 feature lives, and how it works, comes from M-VAVE's own release note. The basic buttons (SEQ, PLAY, REC, SELECT) come from the original manual and from owners. If your unit behaves differently, please [open an issue](https://github.com/fuleo/fm1-guide/issues).

## 1. The basics

| Do this | Result |
|---|---|
| Press **SEQ** | Opens the sequencer screen |
| Press **PLAY** | Starts and stops the pattern |
| Press **REC**, then play keys | Step recording: each key fills the current step, then moves to the next |
| Leave a step empty | A **rest** |
| **Hold REC + turn SELECT** | Moves through the steps without playing, so you can replace a step's note carefully |

The sequencer and the arpeggiator share one **BPM**, and you can **transpose** a pattern while it plays.

## 2. Long notes (V15)

A note can last for several steps:

1. Go to the step where the note should **start**.
2. **Hold the key**.
3. **Turn SELECT** to the step where it should **end**.
4. **Release** the key.

Notes already on those steps are kept, not overwritten.

## 3. Pattern length: Step (V15)

**SEQ page 1 → Step** sets how many steps the pattern plays before it loops.

- **16** is a normal 4/4 bar.
- **12** is a bar of 3/4 (waltz).
- **7** or **5** gives odd loops that drift against a steady beat.

## 4. Chain: play patterns in a row (V15)

Normally the sequencer repeats the one pattern you are on. **Chain** (SEQ page 1, 1–16) plays **N patterns in a row, starting from the current one**, then loops back to the start.

| Start on | Chain | Plays |
|---|---|---|
| 1 | 1 | 1 → 1 → 1 … (normal) |
| 1 | 3 | 1 → 2 → 3 → 1 → 2 → 3 … |
| 1 | 4 | 1 → 2 → 3 → 4 → 1 … |
| 5 | 3 | 5 → 6 → 7 → 5 … |

**Why it matters:** a single pattern is only one bar, which gets repetitive. Chaining builds longer music:

- **4-bar phrase:** write one melody across patterns 1–4 and set Chain = 4. That gives one 64-step loop.
- **Song shape:** for verse, verse, chorus, verse, use patterns 1–4 with Chain = 4. Patterns 1, 2 and 4 are copies of the verse; pattern 3 is the chorus.

**Limits:**
- The patterns must be **next to each other**: no 1 → 5 → 2.
- It only runs forward, and at most 16 patterns.
- Each pattern plays once per pass, so to repeat a part, copy it into the next slot.

## 5. Voice binding: a sound per pattern (V15)

**SEQ page 2 → Voice** binds a voice (preset) to the current pattern. Each pattern then plays with its own sound, and inside a chain the sound changes automatically as the patterns change.

While the sequencer screen is open, the **preset knob does nothing**: the pattern chooses the sound.

> **One sound at a time, not layers.** Voice binding changes the sound *between* patterns: pattern 1 can be a piano and pattern 2 a bass, and a chain switches between them as it plays. But only **one pattern plays at a time**, and the FM-1 plays **one voice at a time**. So it cannot play a piano part and a bass part together like tracks in a DAW. It's more like a playlist of one-bar clips, each with its own instrument.
>
> To get layers:
> - Play chords or a melody by hand over a running pattern. Your hands and the sequencer share the same sound.
> - Record each pattern into a DAW and layer the parts there.
> - Use [Felucca](https://github.com/hugelton/Felucca). It has three synth parts plus a drum track playing at the same time, each with its own sound, though it's still in beta.

## 6. Build a 3-part loop

| Pattern | Voice (SEQ page 2) | What to record |
|---|---|---|
| **1** | a bass | A simple bass line. Use **long notes** for the held ones |
| **2** | a pad or bell | Chord roots or a slow melody over the same bass idea |
| **3** | the same bass | A variation of pattern 1, e.g. a few notes higher in the last 4 steps |

Then:

1. Go back to **pattern 1**.
2. **SEQ page 1:** check Step = 16, and set **Chain = 3**.
3. Press **PLAY**. You hear bass → pad → bass variation, then it loops, and the sound switches by itself each bar.
4. Make it longer: copy patterns into 4–6, set **Chain = 6**, and tweak each copy.

**Tips:**
- Turn the reverb **Decay** up for pads, as described on [the reverb page](reverb.html). V15's scale is 0–100, so low numbers are very short.
- Transposing while the chain plays shifts the whole song, which is handy for key changes.

## What stock V15 can't do yet

None of these are in stock V15:
- more than 16 steps per pattern
- per-step ratchet, chance or gate
- several notes on one step
- recording live over a playing loop
- receiving MIDI Clock

[Baud Girl's FM-1+VA](https://baudgirl.com/work/FM-1+VA) adds 64-step patterns with per-step ratchet, chance, gate and up to 9 notes per step.
