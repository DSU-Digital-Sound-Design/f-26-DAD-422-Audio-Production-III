---
title: "Dolby Atmos with Logic Pro"
---

## Overview

Logic Pro includes a built-in Dolby Atmos renderer, so you can author, monitor, and export ADM without a separate app. Pro Tools also now includes an integrated renderer (in addition to workflows that use the external Dolby Atmos Renderer), so the main difference is workflow, not capability.

Logic routes bed tracks to one shared bus, selectable as 5.1, 7.1, or 7.1.2. We will use 7.1.2. Object tracks send separate audio and position metadata directly to the renderer. At 48 kHz, a ten-channel bed leaves up to 118 mono object inputs within the 128-channel budget; a stereo object track uses two inputs.

## Setup in Logic Pro

- File → Project Settings → Audio
- Sample Rate: 48kHz (standard for video/film)
- Spatial Audio: Dolby Atmos
- Bed format: 7.1.2. Monitoring format should match your room (e.g., 7.1, 7.1.4) or Binaural on headphones.
- On each track, choose the panner you need:
  - Surround Panner = feeds the bed.
  - 3D Object Panner = routes as an object. Dolby binaural render modes are Off, Near, Mid, and Far; they do not affect the Apple Renderer.

## Mono Components vs. Stereo Components

![](../mono-vs-stereo.png)

## Output Routing

![](../output-routing.png)

These menus are dynamic and change depending on what audio interface you're connected to.

![](../output-routing-2.png)

## Surround Formats

![](../surround-format.png)

Changing the format here affects what each plugin and panner can do. When you set the project to a surround format (e.g., 7.1.2), the Surround Panner updates its speaker layout to match.

## I/O Assignments (Output/Speakers)

![](../io-assignments.png)

## Master Channel Strip

Enabling Atmos and switching tracks to surround/object updates the master channel strip and inserts the Dolby Atmos controls.

![](../surround-mode.png)

## Beds vs. Objects (Music Mixing)

Choose a path for the routing and spatial control you need. Both bed and object tracks can be stationary or automated; movement alone does not determine the choice. Typical uses in music:

### Bed tracks (7.1.2)

- Foundation and stability for the mix; great for elements that should downmix predictably.
- Use the Surround Panner to place bed elements in the 7.1.2 field.
- Common bed candidates: drums, bass, main keys, pads, background vocals, FX beds.

### Object tracks

- Discrete position and movement anywhere in 3D space via the 3D Object Panner.
- Per-object Dolby binaural settings (Off/Near/Mid/Far); compare the result over headphones.
- Useful for lead elements, featured instruments, ad-libs, ear-candy, and moments that move.

Notes

- Keep critical anchors (kick, bass, lead vocal) either in the bed or as carefully managed objects to ensure downmixes remain solid.
- A 7.1.2 bed has one top-middle pair. Use objects for independent front-to-back height positioning. The renderer maps bed and object audio to the monitoring layout; the number of physical height speakers does not change the bed format.
- Total budget: 128 channels max (10 bed + up to 118 objects).

## Bounce and Delivery

- Choose **File > Export > Project as Spatial Audio**, then **Dolby Atmos ADM BWF**. The monitoring format does not change this master export. Reopen it in a new project to verify the mix.
- Optionally also bounce a stereo downmix for reference. The renderer’s downmix may differ from a dedicated stereo mix.

## References

- [Apple: bed tracks and object tracks](https://support.apple.com/en-au/guide/logicpro/lgcp73f9b9ac/mac)
- [Apple: export an Atmos master](https://support.apple.com/en-au/guide/logicpro/lgcp258ed132/mac)
