---
layout: page
title: Felucca for beginners
permalink: /felucca.html
---

[Felucca](https://github.com/hugelton/Felucca) by Hügelton Instruments is a free, open-source firmware for the FM-1. It turns the FM-1 into a **4-track synth and sequencer** with 13 sound engines. It can do a lot, but it has no manual, and the panel's printed labels mean something else under Felucca. This page gets you from "what do these buttons do" to a short song.

> **Version:** written for **Felucca 1.5.1**. Each step was checked against the 1.5.1 README, its release notes and the firmware source (including its on-screen help text). Videos made for 1.0.x show an **older page layout**: version 1.4 moved the pages around, so menus in those videos won't match. If something here doesn't match your FM-1, please [open an issue](https://github.com/fuleo/fm1-guide/issues).
>
> **No FM-1 handy?** [Felucca in your browser](https://hugelton.github.io/Felucca/webapp/try/) runs the same firmware with the panel on screen. Everything below works there too.

## 1. Four rules that explain most of it

1. **Tap a button for its page, and tap it again for the next page.** HOME, for example, cycles through HOME → MIXER → CLOCK.
2. **Hold a button for its *layer*,** a temporary map of the keys and knobs. Let go and the layer closes. **Double-tap** the button to keep the layer open, and tap it again to close it.
3. **OCT+ means "OK, do it"** and **OCT− means "back / cancel"** on action pages and in dialogs.
4. **Hold SAVE to undo** the last edit. Hold **HOME** for the menu.

Two knobs work on every page:

| Knob | What it does |
|---|---|
| **ALGORITHM** | picks the **track** (1–4) you're working on |
| **PRESETS** | changes the selected track's **sound** (on any page that isn't a list) |
| **SELECT** | the **tempo** (unless MENU → BPM LOCK is on) |

The header at the top shows the track, the play state and the tempo.

**Turn on the hints.** Hold **HOME** for the menu, turn **ALGORITHM** to the **SYSTEM** tab, turn **PRESETS** to **HELP**, set it **ON** with OCT+, then press **HOME** to close. Each page now shows a two-second hint when it opens, such as "[PRESETS] SOUND  [HOME] HOLD: MENU".

## 2. The buttons

| Button | Tap cycles through | Hold |
|---|---|---|
| **HOME** | HOME, MIXER, CLOCK (BPM, swing, clock source) | the menu |
| **SEQ** | STEP (piano roll or drum grid), DETAIL, AUTOMATION | **SEQ TOOLS** (on every page) |
| **GLO** | SONG | mutes, solos, levels, TAP tempo |
| **SAVE** | USER, PRESETS, PHRASES, PROJECT, TOOLS | undo |
| **EDIT** | the sound pages of the track's engine | **pick an engine** |
| **ENV, LFO, ARP, SCL, FX** | their pages | FX and SCL: their layers. LFO: a temporary knob change |
| **REC** | arms the track for recording | the REC layer: CLEAR, CLICK, COUNT-IN |
| **PLAY** | start and stop | |

## 3. Your first sound

1. Turn **ALGORITHM** to **track 1**.
2. Turn **PRESETS** and play the keys. Each click is another factory sound.
3. To change the **engine** (ANALOG, FM6, SAMPLE, PHYS, DRUM…), **hold EDIT** and turn **KNOB 1** (ENGINE), then **KNOB 2** (SOUND).
4. To browse sounds by **category** (BASS, LEAD, PAD, KEYS, DRUM…), tap **SAVE twice** for the **PRESETS** page. KNOB 2 there is the engine, and **KNOB 4 (LIST)** shows one category at a time.
5. To shape the sound, tap **EDIT** for its main knobs, **ENV** for attack, decay, sustain and release, and **FX** for the effect sends.

**Save a sound you like:** stop playback, tap **SAVE**, pick a user slot with **KNOB 1**, then press **OCT+** and **OCT+** again. The second OCT+ is on the name screen, where the keys type a name if you want one.

## 4. Your first beat (drum track)

1. Turn **ALGORITHM** to **track 4**, hold **EDIT**, and turn KNOB 1 to **DRUM**. KNOB 2 picks the kit: STD, 80, 10, 66, 55 or 77.
2. Tap **SEQ** for the **drum grid**. Here the **white keys are the 16 steps** and the **black keys are the 8 lanes** (kick, snare, clap, closed hat, open hat, tom, rim, bell). **KNOB 2** also picks the lane.
3. Pick the **kick** lane, then press white keys **1, 5, 9 and 13**. Those steps glow a little brighter as a visual guide.
4. Pick the **snare** lane and press **5 and 13**. Pick the **closed hat** and press every other key.
5. Press **PLAY**.

**Cheat:** hold **SEQ** for **SEQ TOOLS**. On a drum track its keys include **BEAT**, which writes a beat for you, plus **RANDOM**, and **COOK**, which changes the pattern a little on each press. Each tool is one undo (hold SAVE).

## 5. Your first melody (synth track)

There are two ways to get notes in.

**Step recording** (easiest, one step at a time):
1. Turn **ALGORITHM** to **track 1** and tap **SEQ** for the **STEP** page, a piano roll.
2. **While stopped, tap REC.** The screen says "KEYS WRITE STEPS".
3. Play a key or a chord. It's written into the step under the cursor, and **letting go moves the cursor on**.
4. **KNOB 1** moves the cursor, so you can skip a step to leave a rest.
5. On a step that holds a note, **KNOB 3 is its length (LEN)**. Turn right to make the note last over the next steps.
6. Tap **REC** again to stop writing, then press **PLAY**.

**Live recording** (play it in real time):
1. Tap **REC** to arm the track, then press **PLAY**. It loops, and each pass adds what you play (overdub).
2. For a click track and a count-in, **hold REC** to open the REC layer: KNOB 1 CLICK, KNOB 2 COUNT-IN.
3. Your timing is kept. Set **QUANTIZE** (on **SEQ → AUTOMATION**) to **ON** to play everything on the grid (the default), or **OFF** to hear exactly how you played.

**Too many wrong notes?** Tap **SCL**, set **SCALE** with KNOB 2, and set **QNT** (KNOB 3) to **WHITE**. Now the white keys play only notes of the scale, and the black keys are silent.

**Pattern settings:** hold **SEQ** for SEQ TOOLS. KNOB 1 is **LENGTH**, KNOB 2 **DIVISION**, KNOB 3 **SWING** and KNOB 4 **GATE**.

## 6. Mix it

- Tap **HOME** twice for the **MIXER**: level, pan, reverb send and mute per track (ALGORITHM picks the track).
- Or show all four tracks on the home screen: MENU → DISPLAY → **HOME → LEVELS**. Then **KNOB 1–4 are the four track levels**.
- **Hold GLO** for quick **mutes and solos** while playing.

## 7. Save your work as a project

A **project** holds all four tracks: sounds, patterns and mix. There are four project slots, **A–D**.

1. **Stop** playback. Saving needs it, and otherwise the screen says "STOP TO SAVE".
2. Tap **SAVE** until the **PROJECT** page.
3. Turn **KNOB 1** to choose the slot.
4. Turn **KNOB 4 (SAVE)** to the right to pick the action, then press **OCT+**. On the name screen, press **OCT+** again to save. Saving over a used slot asks first.
5. To **load** a project, turn **KNOB 3 (LOAD)** to the right instead, then press **OCT+**.

Your music also survives a power-off without saving: **MENU → RESTORE LAST** is on by default.

## 8. Make a song

A song is a list of up to **16 sections**. Each section says which **project slot's pattern** each track plays (A–D, or "-" to rest that track), and how many times it repeats. A song plays the patterns of saved projects, with **the sounds you have now**.

**Get the patterns ready:**
1. Make a verse: drums, bass and a chord part. **Save it as project A** (section 7).
2. Change the patterns for a chorus, for example busier drums and a new melody. **Save as project B**.

**Arrange them:**
1. Tap **GLO** for the **SONG** page. It shows the song as a timeline with one lane per track.
2. **KNOB 1** picks a **section**, **KNOB 2** a **track**, **KNOB 3** the slot it plays (**A–D or -**) and **KNOB 4** the **repeats**.
3. Shortcut: on SONG, the white keys **A3, B3, C4 and D4** set the selected cell to slot A, B, C or D. They don't make a sound on this page. Turning KNOB 1 past the last section gives **+ ADD**, and pressing one of those keys there adds a new section, copied from the one before it.
4. Try this: section 1 is all tracks on **A** ×2; section 2 is the same, but with the lead track on "-" for a breakdown; section 3 is all tracks on **B** ×2.
5. Press **PLAY** on the SONG page to play the **song** from the start. PLAY on other pages plays only the current patterns.

Edit the song while it's stopped. While it plays, the screen says "STOP TO EDIT".

## 9. Effects worth knowing

| Do this | You get |
|---|---|
| **FX** pages → **REVERB**, TYPE **HALL** | a smooth reverb that rings for up to about 4.5 s. It's the default on a fresh start |
| **Hold FX** | live effects on the keys: repeat, reverse, filter sweeps, tape stop, freeze, flanger, phaser |
| Hold FX, then **D5 / E5** | **REV THROW / ECHO THROW**: every track's reverb or delay fully up while held, and the tail rings out after |
| Double-tap **FX** | keeps the FX layer open, so both hands are free |
| In the FX layer, hold a white key and turn **PRESETS** | puts any of the 12 effects on that key |
| **Hold LFO** and turn a knob | a temporary change: let go of LFO and the value jumps back |

## 10. Next steps

- **SEQ → DETAIL:** the cursor step's **CHANCE**, **RATCHET** (×2–×4 repeats), **NUDGE** and **VELOCITY** on KNOB 1–4.
- **Parameter locks:** on SEQ → STEP, hold a step and turn a knob to change that parameter on that one step. **SEQ → AUTOMATION** lists everything like this.
- **The web editor** ([hugelton.github.io/Felucca/webapp/editor](https://hugelton.github.io/Felucca/webapp/editor/), Chrome or Edge over USB) edits every parameter, makes **full backups**, and loads your own samples and DX7 .syx banks.
- **The full reference** is the [Felucca README](https://github.com/hugelton/Felucca#controls) (Controls, Menu, Engines), and the [release notes](https://github.com/hugelton/Felucca/releases) explain each feature in detail.

## Going back to stock

The [web installer](https://hugelton.github.io/Felucca/) has **Return to official V15**. From Linux, see [Updating from Linux](linux-update.html). Projects made in Felucca stay in Felucca's own storage and don't carry over to the stock firmware.

---

<small>Not affiliated with M-VAVE or Hügelton Instruments. Felucca is GPL-3.0 software by Leo Kuroshita / Hügelton Instruments.</small>
