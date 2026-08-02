---
title: "Higher-Order Ambisonics (HOA) Workflow in REAPER"
date: 2024-03-15T10:00:00-05:00
draft: false
---


This guide outlines the setup and processing chain I use for working with higher-order ambisonics (HOA) in REAPER—from encoding to transformation and decoding. It’s meant as a practical reference for sound artists, composers, and spatial audio researchers.

---

## 1. Setup

Before diving into ambisonic processing, start with this excellent introduction to REAPER routing for multichannel audio:

* [Tutorial: Basic Routing in REAPER](https://plugins.iem.at/docs/tutorial_basicrouting/)

---

## 2. Plugins

I use several plugin suites to **encode, transform, decode, and visualize** ambisonic material. Each suite has unique strengths for different stages of the workflow.

### Encoding and Visualization Tools

* [**Harpex**](https://harpex.net/index.html) – Great for spatial visualization (demo mode works fine).
* **VVOctoEncode** – Encodes 8-channel ambisonic recordings into 2nd-order B-format. Calibration files and plugin are available on my OneDrive.

### Core Ambisonic Plugin Suites

* [**SPARTA Suite**](https://leomccormack.github.io/sparta-site/docs/plugins/sparta-suite/#ambidrc) – Excellent for a wide range of HOA processes.
* [**IEM Plug-in Suite**](https://plugins.iem.at/) – My go-to for many HOA workflows.
* [**ambiX v0.3.0**](https://www.matthiaskronlachner.com/?p=2015) – Older, but still includes several valuable tools.
* [**mcfx v0.6.0**](https://www.matthiaskronlachner.com/?p=1910) – Solid for multichannel audio processing.
* [**WigWare**](https://www.brucewiggins.co.uk/?page_id=78) – Contains some experimental and creative spatial tools.

---

## 3. Encoding

Use **VVOctoEncode** first in your signal chain to convert raw recordings into 2nd-order ambisonic B-format.

### Calibration Notes (from VVAudio)

> When encoding very quiet sound sources, use **Option 1** as the default.
> For louder sources, consider **Options 2 or 3**.

---

## 4. Transforming the Soundfield

Once encoded, you can creatively manipulate the ambisonic field.
Be cautious with stereo-only plugins—they’ll collapse your project to two channels.

Here are categories of transformations that preserve ambisonic integrity.

### Soundfield Manipulation

* **ambix_directional_loudness** – Emphasize or attenuate specific regions of the sphere.
* **ambix_mirror** – Mirror across the X/Y/Z axes.
* **ambix_rotator / ambix_rotator_z** – Rotate the field in 3D or around the Z-axis.
* **ambix_vmic** – Virtual microphone approach for isolating parts of the field.
* **ambix_warp** – Warp the soundfield toward poles, equator, front, or back.
* **ambix_widening** – Frequency-dependent rotation; great for diffusion or widening.
  * Reference: [DepositOnce article](http://dx.doi.org/10.14279/depositonce-12)
  
### Dynamic Processing

* [Directional Compressor](https://plugins.iem.at/docs/plugindescriptions/#directionalcompressor)
* [Multiband Compressor](https://plugins.iem.at/docs/plugindescriptions/#multibandcompressor)
* [Omni Compressor](https://plugins.iem.at/docs/plugindescriptions/#omnicompressor) – Uses the W (omni) channel; can double as a limiter.

### EQ and Filtering

* [MultiEQ](https://plugins.iem.at/docs/plugindescriptions/#multieq) – Multiband equalizer.
* **mcfx_filter** – Single-band filters for precise control.

### Reverb

* [FDN Reverb](https://plugins.iem.at/docs/plugindescriptions/#fdnreverb) – Smooth, natural sound.
* **AmbiXFreeverb 2** (WigWare) – Includes a creative freeze mode.

### Delay and Modulation

* [Dual Delay](https://plugins.iem.at/docs/plugindescriptions/#dualdelay) – Adds delay with spatial rotation.

### Experimental Tools

* [Granular Encoder](https://plugins.iem.at/docs/granularencoder/) – Dramatically alters spatialization.
* [Directivity Shaper](https://plugins.iem.at/docs/directivityshaper/) – Advanced spatial filtering for unique effects.

---

## 5. Decoding

Once your mix is spatially sculpted, decode for your playback environment:

* [**SPARTA AmbiDec**](https://leomccormack.github.io/sparta-site/docs/plugins/sparta-suite/#ambidec) – For decoding to 7.1 (Studio B setup).
* [**IEM Binaural Decoder**](https://plugins.iem.at/docs/plugindescriptions/#binauraldecoder) – For headphone or stereo playback.

---

## Closing Thoughts

HOA workflows can feel complex, but with these plugins and routing strategies, you can sculpt immersive, transportive soundfields that retain spatial fidelity. Experimentation is key—each plugin suite offers distinct creative pathways for spatial sound design.

