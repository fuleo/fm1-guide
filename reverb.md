---
layout: page
title: Reverb after V15
permalink: /reverb.html
---

**The symptom:** after updating from V14 to V15, the reverb's long fade-out seems to be gone.

**The cause:** V15 changed effect (and envelope) parameters from a **0–10** scale to **0–100**, and kept the stored numbers as they were. A decay of 8, which was near the top on V14, is now 8 out of 100, and that rings for about half a second.

**The fix:** set reverb **Decay to 80–100**. On our unit, decay 100 brought the long fade straight back.

## On the synth

1. Press **FX**. The screen shows the six effects (Filter, Reverb, Delay, Distortion, Chorus, Phaser). A bright box means the effect is on, a dim box means it is off.
2. Turn **SELECT** to put the blinking dot under **Reverb**.
3. **Knob 4** switches it on. **Knob 1** picks the type (Room / Hall / Plate), **knob 2** sets the mix, and **knob 3** sets the **decay**: turn it all the way up.
4. **Save the voice** if you want to keep the setting.

## Over MIDI

Send these on the **Effect Channel** (default **channel 2**). The values follow Baud Girl's [FM-1 MIDI guide](https://m-vave-fm1-midi-guide.up.railway.app/) and M-VAVE's CC table.

| CC | Reverb parameter | Values |
|---|---|---|
| 4 | On/off | 0 off, anything else on |
| 5 | Type | 0 Room, 1 Hall, 2 Plate |
| 6 | Decay | 0–100 |
| 7 | Mix | 0–100 |

**CC 7 is reverb mix, not volume.** If a DAW sends CC 7 for track volume on channel 2, it changes the reverb mix instead.

## Measurements (V15)

This was measured on one unit over USB:
- Reverb was set by CC, then a 300 ms C4 note was played at velocity 110.
- The FM-1's own USB audio output was recorded.
- Each figure is the time for the sound to fall **40 dB** after the key was released.

| Setting (mix 60) | Time to fall 40 dB |
|---|---|
| Reverb off | 0.08 s |
| Hall, decay 5 | 0.40 s |
| Hall, decay 8 | 0.50 s |
| Hall, decay 10 | 0.72 s |
| Hall, decay 25 | 1.5 s |
| Hall, decay 50 | 2.3 s |
| Hall, decay 75 | 3.7 s |
| **Hall, decay 100** | **≈ 5 s** (full fade ≈ 7 s) |
| Room, decay 100 | 3.7 s |
| Plate, decay 100 | 4.3 s |

The **envelopes** changed scale too. If old V14 sounds feel shorter or snappier, raise their attack and release values.

## Measure it yourself (Linux)

The FM-1 shows up as a USB audio device. Its capture format is 24-bit packed (S24_3LE), stereo, 44.1 kHz, so record through ALSA's converting device:

```bash
ffmpeg -f alsa -sample_rate 44100 -channels 2 -i plughw:FM1 -c:a pcm_s16le -t 7 take.wav
```

(`hw:FM1` fails, because ffmpeg cannot open the 3-byte format directly.) The sweep script is [`reverb_sweep.py`](https://github.com/fuleo/fm1-linux-update/blob/main/reverb_sweep.py): it sets the reverb by CC, plays a note, records it and times the tail.

**Battery note:** on battery, a loud held high note with a long reverb can make the battery bar drop briefly. That is most likely the voltage dipping under the speaker's load. Check whether it recovers after a minute of silence.
