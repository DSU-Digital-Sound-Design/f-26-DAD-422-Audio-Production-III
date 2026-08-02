---
title: "Setting Up Ambisonics in Reaper with the Ambisonic Toolkit (ATK)"
---

# Ambisonics in Reaper with the Ambisonic Toolkit (ATK)

Ambisonics gives you a way to compose and deliver a full‑sphere soundfield that can be decoded for many playback targets—headphones, 5.0/7.0 arrays, octagons, and more—without committing to a single loudspeaker layout during production. The Ambisonic Toolkit for Reaper (ATK) wraps that approach into a clear, three‑stage workflow: author (encode), image (transform), and monitor (decode). That separation is the reason ATK feels musical in practice: you shape a coherent soundfield first, then audition it through whatever decoder makes sense today. ([Ambisonic Toolkit][1])

---

## Listen First: Play the Example Recordings

Begin with the ATK example recordings. They’re short (≈30‑second) excerpts in multiple formats—A‑format, B‑format, UHJ, stereo, and even Zoom H2 quad—curated specifically to test encoders, transformers, and decoders. Drop a few into a fresh Reaper session and simply listen; then you’ll have neutral material ready when you start encoding and decoding. ([Ambisonic Toolkit][2])

Audition a B‑format example through a binaural decode on headphones, then switch to a stereo or UHJ excerpt to hear how different sources and encodings translate. The example pack is linked directly from ATK’s site. ([Ambisonic Toolkit][3])

---

## Why Use ATK Inside Reaper

ATK for Reaper is a set of JSFX plug‑ins designed around ambisonic practice—encoders for common source types, field‑aware transformers with visual GUIs, and a family of decoders (stereo, UHJ, multichannel, binaural). Because they’re JSFX, they run on all platforms Reaper supports; with ReaJS, parts of the set can also be used in other Windows DAWs. The design emphasis is ergonomic: ATK exposes ambisonic moves (rotate, focus/zoom, dominance, mirroring, proximity, etc.) as musical controls. ([Ambisonic Toolkit][4])

Conceptually, ATK’s workflow keeps authoring, imaging, and monitoring distinct. You encode sources to B‑format, transform the soundfield as a whole, and only then decode for the current monitoring target. Keeping those layers separate is what makes ambisonic sessions highly portable across playback contexts. ([Ambisonic Toolkit][1])

---

## Install ATK and Verify It’s Ready

ATK’s current public release for Reaper is Version 1.0 beta 11 (released November 4, 2021). It requires Reaper 5.0 or newer. On macOS, you run an installer that places everything in your home folder; on Windows you unzip an archive and copy the contents into Reaper’s resource path (Options → Show REAPER resource path), then restart. The installers include convolution kernels and matrices—no separate downloads required. After installation, open Reaper’s FX browser and search for “ATK” under JS effects. ([Ambisonic Toolkit][3])

If you want ready‑made material to try the plug‑ins, ATK’s example sound files are linked from the same download page. ([Ambisonic Toolkit][3])


---

## A Minimal, Reliable Session Layout

Ambisonics thrives when routing is clean. In Reaper, set up a compact template that separates encoding, transforming, and monitoring:

1. Create a B‑format bus (a folder track) with four channels for first‑order Ambisonics (W, X, Y, Z). Route all encoded sources into this bus. ([DXARTS][5])
2. Create one or more decoder tracks fed from the B‑format bus. Put the decoders (UHJ, 5.0, binaural, etc.) here; route each decoder to the appropriate hardware outputs. This lets you A/B multiple decodes and render stems per target later. ([DXARTS][5])
3. Avoid Reaper’s regular stereo pan/width on ambisonic tracks—use ATK encoders and transforms instead, and let the decoders handle panning to speakers or headphones. ([DXARTS][5])

This folder/decoder‑track pattern preserves a clean B‑format “master” you can re‑decode for future deliverables without re‑mixing. ([DXARTS][5])

---

## Step 1: Encode Your Sources to B‑Format

ATK’s encoders map common source situations into B‑format. For mono, the core options are:

* Planewave: a directional point source where you set azimuth and elevation.
* Omni: an omnidirectional point source for non‑localized energy beds.
* Spreader: frequency‑dependent rotation to widen a source.
* Diffuse: randomizes phase to create a gentle, enveloping field. ([Ambisonic Toolkit][4])

Rule of thumb: start Planewave for focused objects, widen with Spreader if needed, switch to Omni for neutral beds, and use Diffuse when you want motionless but spacious texture.

For stereo, use Stereo (two parameterized planewaves) or SuperStereo (classic method), and if you work with legacy UHJ material, ATK includes a UHJ stereo encoder. Example Reaper projects demonstrate these exact cases and match the tutorials. ([Ambisonic Toolkit][6])

ATK also provides tools for multichannel situations (planewave transcoders for 5.0/7.0, and A‑to‑B workflows) if you’re synthesizing or mic‑array authoring more complex fields. ([Ambisonic Toolkit][4])

---

## Step 2: Transform the Soundfield

Place transformers on the B‑format bus to manipulate the entire soundfield coherently:

* Rotate/Tilt/Tumble for multi‑axis rotations (camera‑like moves).
* Focus/Press/Push/Zoom to emphasize or collapse energy toward a direction of interest.
* Dominance to weight the scene toward or away from a target region.
* Mirror/MirrorO for symmetry‑based morphs.
* Proximity/Nearfield to add or remove near‑field effects musically.

Many transformers include GUIs that visualize what you’re doing, which makes automation intuitive. ([Ambisonic Toolkit][4])

---

## Step 3: Decode for Monitoring and Delivery

On your decoder tracks, pick the decoder that matches your current listening or export target:

* Binaural for headphones.
* Stereo or UHJ for two‑channel speaker playback.
* Quad, 5.0, 7.0, or polygonal arrays for multichannel rooms.

Because decoding is separate from authoring and imaging, you can keep multiple decoder tracks active and monitor different targets with solos, or render stems per target without touching the B‑format bus. ATK’s decoder set covers virtual microphones, stereophony (including UHJ), multichannel arrays, and a dedicated binaural decoder. ([Ambisonic Toolkit][4])

---

## Exporting Without Painting Yourself Into a Corner

When it’s time to deliver, render stems from your decoder tracks (stereo/UHJ/binaural/5.0, etc.) while also keeping a clean B‑format master for future re‑decoding. Reaper’s stem‑rendering workflow and track‑based decoders make this straightforward—even at higher channel counts—without re‑wiring the session. ([DXARTS][5])

---

## Common Pitfalls (And How ATK’s Design Avoids Them)

* Treating pan pots like spatialization: in ambisonics, panning happens at the decode. Use encoders for placement and width, and avoid Reaper’s standard pan/width on multichannel ambisonic tracks. ([DXARTS][5])
* Baking the decoder into your only mix: keep the B‑format bus “dry,” and do decoding on separate tracks so you can monitor and render multiple targets. ([DXARTS][5])
* Skipping the imaging stage: many toolchains only offer encode/decode. ATK’s imaging transforms are where a lot of the artistry lives—don’t miss them. ([Ambisonic Toolkit][1])

---

## Where To Go Next

ATK’s Reaper tutorials walk you through encoding mono and stereo sources step‑by‑step, with matching example projects you can open and inspect. If you want an extended, practical walkthrough of multichannel routing, decoder tracks, and rendering, the DXARTS guide linked from the tutorials page is an excellent companion. ([Ambisonic Toolkit][6])

---

## Optional Tools For Visualization

- Harpex (paid): high‑quality B‑format decoding with helpful soundfield visualization. ([Harpex][7])
- Matthias Kronlachner’s ambiX/multichannel tools (free): useful complements for routing, analysis, and ambisonic utilities. ([ambiX][8])

---

## References

* Example recordings (A‑format, B‑format, UHJ, stereo, quad), with notes on using them in Reaper. ([Ambisonic Toolkit][2])
* ATK for Reaper download page (version, requirements, installers, included kernels/matrices, install steps). ([Ambisonic Toolkit][3])
* ATK for Reaper documentation (JSFX basis, GUIs, full list of encoders, transformers, decoders, including binaural). ([Ambisonic Toolkit][4])
* Tutorials overview (encode to B‑format; mono/stereo workflows; links to example projects). ([Ambisonic Toolkit][6])
* Introduction to the ATK workflow (author/image/monitor; soundfield‑kernel model). ([Ambisonic Toolkit][1])
* Ambisonic mixing in Reaper (decoder tracks, rendering stems, multichannel routing tips). ([DXARTS][5])

---

[1]: https://www.ambisonictoolkit.net/documentation/workflow/ "Introduction - The Ambisonic Toolkit Workflow"
[2]: https://www.ambisonictoolkit.net/download/recordings/ "Example Sound Files - A number of 30 second extracts from published and unpublished recordings"
[3]: https://www.ambisonictoolkit.net/download/reaper/ "Download ATK for Reaper - A set of JSFX plugins for the Reaper DAW"
[4]: https://www.ambisonictoolkit.net/documentation/reaper/ "ATK for Reaper"
[5]: https://dxarts.washington.edu/wiki/ambisonic-mixing-reaper "Ambisonic Mixing in Reaper | DXARTS: Digital Arts & Experimental Media | University of Washington"
[6]: https://www.ambisonictoolkit.net/documentation/reaper/tutorials/ "Tutorials - Ambisonic Toolkit for Reaper"
[7]: https://www.harpex.net "Harpex - B-Format Decoder"
[8]: https://www.matthiaskronlachner.com/?p=2015 "ambiX - Ambisonics Plugin Suite by Matthias Kronlachner"
