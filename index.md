---
layout: home
title: Home
---

Practical notes for the **M-VAVE FM-1**, the pocket 6-operator FM synth. Written while learning one unit on stock firmware **V15**.

## Tutorials

- **[Using the sequencer](sequencer.html):** record patterns, long notes, pattern length, Chain and voice binding, plus a 3-pattern song to build.
- **[Getting the long reverb back after V15](reverb.html):** why the reverb tail seems to vanish after updating, and the measurements that show it.
- **[Updating V14 → V15 from Linux](linux-update.html):** no Windows or macOS app needed.

## What V15 changed (2026-07-30)

From M-VAVE's own release note, linked from [m-vave.com/download](https://www.m-vave.com/download):

| Area | Change |
|---|---|
| Display | Brighter base LED backlight |
| Global | **Voice reset** per bank (A–D); **Glide** 0–1 s (mono voices only, GLOB page 2) |
| Sequencer | **Long notes**, **Step** count, **Chain** 1–16 (SEQ page 1); **voice binding** per pattern (SEQ page 2) |
| Edit | **Init voice**, **rename**, **copy & replace** (EDIT → GLOBE sub-page, page 2: K1 / K2 / K3); long-press an **OP** button to mute it |
| FX & ENV | Ranges went from 0–10 to **0–100**. Old values are not converted, see [the reverb page](reverb.html) |
| MIDI | Note-on with velocity 0 now counts as note-off. Effect CCs use the 0–100 scale |

Earlier versions:
- **V13** (2026-07-03):
  - ARP and the sequencer sync to the BPM.
  - The sequencer can transpose.
  - Global velocity setting.
  - The MIDI channel defaults to ALL.
  - Program Change selects voices.
  - ARP rates 1/1 and 1/2 added.
- **V09** (2026-06-24):
  - ENV on/off switch.
  - Rests and note replacement in the sequencer.

## Custom firmware

Two community firmwares need stock V15 first:
- [Baud Girl FM-1+VA](https://baudgirl.com/work/FM-1+VA) adds a virtual-analog engine and a 64-step sequencer.
- [Felucca](https://github.com/hugelton/Felucca) by Hügelton Instruments is a multi-engine groovebox, currently in beta.

---

<small>Not affiliated with M-VAVE, Baud Girl or Hügelton Instruments. M-VAVE and FM-1 are trademarks of their owners. Corrections welcome via [issues](https://github.com/fuleo/fm1-guide/issues).</small>
