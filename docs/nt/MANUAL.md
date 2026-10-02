# Haar for disting NT: User Manual

*Ormer Modular, made in Guernsey.*

Haar is the sea fog that swallows the Channel Islands in an afternoon. The reverb of the same name is a lush stereo algorithmic tail with that weather baked in: **highs die into the murk, lows bloom.** Three knobs do almost everything. **FOG** is how much weather, **GLOW** is the lamp warming through it, **DRIFT** is how much the world moves.

This is the manual for the Expert Sleepers disting NT plug-in. The VCV Rack module has its own manual in [`docs/vcv`](../vcv/MANUAL.md).

## Contents

1. [The screen](#the-screen)
2. [The three knobs](#the-three-knobs)
3. [Other controls](#other-controls)
4. [On the disting NT](#on-the-disting-nt)
5. [Field notes](#field-notes)
6. [Troubleshooting](#troubleshooting)
7. [Specifications](#specifications)

## The screen

The display is a live scene of a lighthouse on the sea, and it answers the three knobs.

- **Fog** thickens with FOG, and the stars fade behind it.
- The **lamp** and its halo heat up with GLOW.
- DRIFT is the weather. **Swell** rolls through the sea, the **beam** speeds up and hunts, and past halfway the tape brings **grain, dropouts and a slow weave** of the whole picture.
- The spray sparkle follows the actual wet level.

The three labels along the bottom sit above the three pots, each with a level bar, and always name what the pots do right now.

## The three knobs

Under the knobs is a full algorithmic plate: predelay, drive, a diffusion tank with split high and low damping, a tilt EQ and a tape stage. You never meet those parameters raw. Each knob is a **macro**, a curated path through the engine, tuned by ear against a low foghorn tone.

```
IN → PREDELAY → DRIVE → DIFFUSION TANK → TILT EQ → TAPE / LO-FI → MIX → OUT
```

### FOG: how much weather

Size, decay and diffusion ride together. The tail is fully smeared by 30%, because Haar has no interest in discrete early reflections, and noon is already a proper hall, around five to six seconds. Size glides rather than jumps, so riding FOG bends the tail's pitch tape-style. The damping asymmetry (aggressive on top, light below) is the fixed character, deepening slightly with size the way air eats treble over distance.

**The last few degrees are freeze.** Above roughly 85% the loop gain ramps to unity: the lows hold and bloom indefinitely while the high damping keeps eating the top, so a frozen chord slowly sinks into the murk instead of ringing static.

### GLOW: the lamp

Drive into the tank, with a darkening tilt EQ riding alongside so the saturation thickens instead of turning harsh. The distortion is asymmetric, which gives even harmonics and warmth rather than buzz. The loop's own saturation deepens with it, so the tail itself compresses and warms, not just the signal entering it.

### DRIFT: how much the world moves

Still water at zero, though a whisper of motion is always on because nothing analog is pitch-perfect. The lower half brings up four sine LFOs into a slow lush chorus, deepest around 45%. From there genuine random wander takes over and **the tape comes in**: wow first, then flutter and deeper saturation past 60%, and a real top-end rolloff that pulls the tail down toward 2 kHz at full. The sine chorus recedes as the weather worsens but never leaves.

> **Feel:** big DRIFT moves settle over a fraction of a second. Weather changes, it doesn't switch. As the tape engages you may hear a brief pitch swoop while the tape distance stretches in. Both are deliberate. With GLOW and DRIFT both near full the tape layer and the drive stack up and the tail turns dirty on purpose: that corner is heavy weather.

## Other controls

| Control | Range | What it does |
|---|---|---|
| Input | 0 to 100% | Level into the tank. Interacts with GLOW: a hotter input drives harder. To keep the tank clean, pull Input and GLOW back and make the level up with Wet level. |
| Mix | 0 to 100% | Equal-power dry/wet. 100% is the classic send-return wash. |
| Predelay | 0 to 500 ms | Space before the fog arrives. It glides when changed, bending pitch tape-style rather than clicking. |
| Filter HP | 0 to 100% | High-pass on the wet path, sweeping up to about 900 Hz. Thin the fog, keep the shimmer. Exactly open at 0, click-free at any sweep speed. |
| Filter LP | 0 to 100% | Low-pass on the wet path, sweeping down to about 900 Hz. Sink the tail below the mix. Independent of HP: both together leave a band of fog. |
| Shimmer | 0 to 100% | Pitch-shifted regeneration: a shifted tap of the tail feeds back into the tank, so each pass climbs (or falls). Haar's high damping eats every generation, so the voices bloom, then sink into the murk. Safe with freeze: it holds and glows rather than running away. |
| Shim tune | -24 to +24 st | The shimmer interval, default +12 (octave up). -12 is the sleeper: the fog deepening instead of glowing. Retuning a ringing tail bends it varispeed-style. Octaves stay in key through every generation; other intervals stack as they recirculate (a fifth blooms into a spiral of fifths). That wander is the weather, not a fault. |
| Wet level | 0.0 to 12.0 dB | Make-up gain on the wet path, after the tank and before the mix. Pull Input and GLOW back to keep the tank clean and give it headroom, then push the tail back up here. At 0 dB (the default) Haar sounds exactly as it always did, and the dry signal is never touched. It has no pot: set it from the parameter page, or map it. |

## On the disting NT

### Installing

Haar needs [disting NT firmware 1.19 or newer](https://www.expert-sleepers.co.uk/distingNTfirmwareupdates.html).

1. Download `haar-plugin.zip` and unzip it. Copy `haar.o` into `programs/plug-ins/` on the MicroSD card.
2. Restart the module (or rescan plug-ins from the settings menu).
3. Add an algorithm, then choose **Haar** (tagged Effect and Reverb).

### The pots: three pages

The three pots always do exactly three things, and which three depends on the page. **Pushing the centre pot steps to the next page.** The label strip along the bottom of the screen always names what the pots do right now.

| Page | Left pot | Centre pot | Right pot |
|---|---|---|---|
| **1. The macros**: where Haar lives, the sound in three moves | **FOG**: the weather, size and decay, freeze at the top | **GLOW**: the lamp, drive and warmth | **DRIFT**: the motion, chorus into tape |
| **2. The filter and shimmer**: performance shaping of the wet tail | **HP**: thin the fog from below | **SHIMMER**: octave-up bloom | **LP**: sink the tail into the dark |
| **3. The levels**: set when patching, then leave | **INPUT**: level into the tank | **PREDELAY**: 0 to 500 ms before the fog | **MIX**: equal-power dry/wet |

Push the centre pot on page 1 for page 2, on page 2 for page 3, and on page 3 to return to page 1.

**Nothing ever jumps.** After a page change, each pot stays silent until you turn it to the value it now owns (the NT's soft takeover). Flip pages freely mid-performance. Wet level has no pot, so it is not on any page: set it from the parameter page.

### Automation and CV

Every parameter, the three macros included, is a normal NT parameter, so all of it can be mapped to CV, MIDI or i2c and automated through the module's own **Mappings** system, exactly like a built-in algorithm. The macros run at 0.1% resolution and every audible target glides inside the engine, so mapped steps and fast automation stay clean.

### Routing

| Signal | Default | Notes |
|---|---|---|
| Left input | Input 1 | |
| Right input | Input 2 | Set to **None** for mono: left feeds both sides. |
| Left output | Output 1 | Mode defaults to **Replace**: Mix already carries your dry signal. Use **Add** only to sum onto a busy bus, with Mix at 100% wet. |
| Right output | Output 2 | As the left output. |

## Field notes

Starting points. Values are percentages.

**Foghorn.** The reference patch. A low, slow drone becomes a coastline.
FOG 65, GLOW 40, DRIFT 15, MIX 60. Feed it anything dark and sustained; let the asymmetric damping do the arranging.

**Held light.** Freeze as an instrument. Catch a chord, then play against the fog.
FOG 100, GLOW 25, DRIFT 10, MIX 100. Map FOG to a CV source and drop it from 100 to about 70 to let the frozen tail exhale.

**Worn tape.** The full weather: wow, flutter, grain, the top gone soft.
FOG 55, GLOW 60, DRIFT 85, MIX 70. Best on melodic loops: the wander detunes the tail against the dry.

**Undertow.** Down-shimmer: the tail keeps sinking an octave into the murk.
FOG 70, SHIMMER 55, Shim tune -12, MIX 70. Slow melodic lines grow a seabed. Try Shim tune -7 for something stranger.

**Lantern choir.** Shimmer through fog: octaves that bloom above a drone and sink back into it.
FOG 75, GLOW 30, DRIFT 10, SHIMMER 60, MIX 80. Push FOG to the top mid-swell and the choir hangs in the frozen fog.

**Harbour room.** Short, warm, barely moving. Haar as a mixer's space rather than an effect.
FOG 20, GLOW 30, DRIFT 0, MIX 25. Add 40 to 80 ms of predelay to keep transients ahead of the wash.

## Troubleshooting

**Haar doesn't appear in the NT's algorithm list.** Update the module's firmware (Haar needs 1.19 or newer) and check `haar.o` really is inside `programs/plug-ins/`.

**I hear the dry signal twice.** The output mode is set to Add while Mix is below 100%. Either keep the default Replace, or run Mix fully wet when summing onto a bus.

**The tail pitch-bends when I move FOG.** That's the size glide: the tank physically stretches, like varispeed on tape. Ride it slowly for a chorus-like bloom, or park it before a take.

**Frozen tails eventually go dark.** By design. Freeze holds the lows at unity while high damping keeps working, so a frozen chord sinks into the murk rather than ringing static.

## Specifications

| | | |
|---|---|---|
| Engine | stereo algorithmic plate | 4 input allpasses into two cross-fed branches; split high/low damping; 4 modulators (sine plus random wander per pair); tilt EQ; tape wow/flutter stage |
| Size range | 0.25x to 2.25x | of the base plate lengths, glided |
| Predelay | 0 to 500 ms | glided, interpolated |
| Freeze | FOG above about 85% | lows sustain indefinitely; the top keeps damping |
| disting NT | firmware 1.19 or newer | 48 kHz, about 19 KB code, about 497 KB of DRAM; pots are the macros, everything CV-mappable |
| Parameters | 17 | 11 on the Haar page and 6 on the Routing page |

The tank topology and base delay lengths are adapted from Mutable Instruments Rings (MIT licence, copyright Emilie Gillet; the notice is preserved in the source). Everything else, including the runtime-sized rebuild, split damping, modulators, tape stage and the macro curves, is original. Haar is closed-source and proprietary.

*Haar. Ormer Modular. Made in Guernsey.*
*Copyright 2026 Ormer Modular. All rights reserved.*
