---
layout: page
title: Update from Linux
permalink: /linux-update.html
---

M-VAVE ships its FM-1 updater only for Windows and macOS. This page updates the FM-1 from stock **V14 to V15 on Linux**. Both custom firmwares need V15 first.

> **Tested once:** on 2026-10-03, one FM-1 went from `FM-1_014` to `FM-1_015` on Ubuntu 22.04 (kernel 5.15, Python 3.10), first time. It's unofficial; use at your own risk.

## How it works

- **The protocol.** The FM-1 (JieLi AC791N) updates over plain **USB-MIDI SysEx** in two steps:
  1. The running firmware reads parts of the package, checks it, and restarts into its update loader.
  2. The loader reads the whole package and writes it to flash, then restarts.
- **What the computer does.** The **synth asks** for byte ranges and the **computer answers**. M-VAVE's own loader, shipped inside the package, does all the flash writes. This is the same process M-VAVE's app runs.
- **What Linux needs.** Only the stock `snd-usb-audio` driver, which loads automatically. The SysEx side uses [Felucca's](https://github.com/hugelton/Felucca) `fm1_install.py`, downloaded at a pinned commit and checked by sha256.

## Steps

The scripts are in [fuleo/fm1-linux-update](https://github.com/fuleo/fm1-linux-update).

```bash
git clone https://github.com/fuleo/fm1-linux-update && cd fm1-linux-update
./fm1-update.sh setup     # venv (mido + python-rtmidi), installer, V15 package -- all checked by sha256
./fm1-update.sh info      # read-only: "FM-1_014  [running]"
./fm1-update.sh flash     # asks, then runs in the background; tail -f fm1-update.log
./fm1-update.sh info      # expect "FM-1_015  [running]"
```

Before you start:

- **Switch the FM-1 on**, and use a USB **data** cable. A charge-only cable never shows up.
- `lsusb` should list `4c4a:c755 Jieli Technology USB Composite Device`. After V15 the product name reads `FM-1`.

A good run looks like this:

```
starting the update on FM-1_014
checking the package (9 reads)
switching to update mode
writing ... 100%      <- jumps around: the loader asks for the image from the end backwards
restarting
done: the FM-1 runs FM-1_015
```

**If it stops partway**, the FM-1 stays in its update loader (`info` shows `update loader`). Run `flash` again to finish the write.

## Checks on the package

| Check | Value |
|---|---|
| Source | M-VAVE's file store, `…/software/firmware/FM-1.fwsc` (2026-07-30, 699,956 bytes) |
| sha256 | `db1642b2b6fa5c2cccb11ffd13878068bb28601678d3644049f99dc40e7edb8a` |
| Embedded name | `FM-1_015` |
| 16 KB flash head (bootloader + chip config) | Matches stock V15, the same constant Baud Girl's installer checks |

## Caveats

- **There is no hardware recovery path.** The FM-1 has no debug header and no recovery button. If an update goes badly wrong, the only known recovery is forcing the chip's built-in USB download mode with an RP2040-based dongle.
- **Run it detached** (the script already does), keep the computer awake, and don't unplug during the write.
- **After the update, raise reverb decay and envelope values.** V15's 0–100 scale makes old values short; see [the reverb page](reverb.html).
- **Felucca's installer needs `--force` for stock packages,** because it otherwise accepts only Felucca's own. The script passes it only for the verified stock file.

**Credits:**
- [AL-255/FM-1-RE](https://github.com/AL-255/FM-1-RE): reverse-engineering of the update protocol.
- [Felucca](https://github.com/hugelton/Felucca): the installer.
- [Baud Girl](https://baudgirl.com/work/FM-1+VA): the stock-head check and package-format notes.
- [aroum/fm1-custom-fw](https://github.com/aroum/fm1-custom-fw): the location of the V15 package.
