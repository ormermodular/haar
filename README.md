<p align="center">
  <img src="docs/images/haar-banner.svg" alt="Haar by Ormer Modular" width="100%">
</p>

<p align="center">
  <img alt="Licence: proprietary" src="https://img.shields.io/badge/licence-proprietary-lightgrey">
  <img alt="VCV Rack 2 version coming soon" src="https://img.shields.io/badge/VCV%20Rack%202-coming%20soon-e2a24a">
  <img alt="disting NT firmware 1.19 or newer" src="https://img.shields.io/badge/disting%20NT-firmware%201.19%2B-e2a24a">
</p>

<p align="center"><strong>A reverb that sounds like sea fog: the highs die into the murk and the lows bloom.</strong></p>

Haar is named for the cold sea fog that swallows the Channel Islands in an afternoon. The reverb is built around that idea: a lush, smeared stereo tail that goes dark and warm on top while the low end keeps blooming underneath. There are no discrete early reflections, only one continuous, enveloping wash.

Three knobs do almost everything. **FOG** is how much weather: size, decay and diffusion ride together, and the last few degrees freeze the tail. **GLOW** is the lamp warming through it: drive and a darkening tilt. **DRIFT** is how much the world moves, from still water through a slow chorus into random wander with tape wow, flutter and grain. Underneath sit a wet high-pass and low-pass, a tunable shimmer, predelay and a clear-tail control.

A small living scene of a lighthouse on the sea sits on the screen and answers the knobs. Haar is made by Ormer Modular in Guernsey, for the disting NT, with a VCV Rack version coming soon.

[disting NT manual](https://ormermodular.github.io/haar/nt/) · [VCV Rack manual](https://ormermodular.github.io/haar/vcv/) · [Releases](../../releases)

## Installing

**disting NT** (firmware 1.19 or newer): download `haar-plugin.zip` from the [Releases](../../releases) page, unzip it onto the root of the MicroSD card (it puts `haar.o` in `programs/plug-ins/ormermodular/`). Restart the module, then add the **Haar** algorithm. The [manual](docs/nt/MANUAL.md) covers the pots and pages.

**VCV Rack:** a VCV Rack version is coming soon.

## Credits

The tank topology and base delay lengths are adapted from Mutable Instruments Rings, and the shimmer follows the Clouds pitch-shifter scheme. Both are MIT licensed, copyright Emilie Gillet. Everything else is original work.

## Licence

Copyright 2026 Ormer Modular. All rights reserved. Haar is proprietary, closed-source software. No licence is granted to copy, modify or redistribute it. The MIT licence applies only to the adapted Mutable Instruments portions, whose notice is preserved in the source.
