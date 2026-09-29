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

ATK transformers take four-channel FuMa B-format in and return four-channel
FuMa B-format. Put one after an encoder on an individual source to move that
source. Put it on the B-format bus to change the whole scene. In either case,
keep the transformer before the binaural or speaker decoder.

* **RotateTiltTumble** rotates the field around three axes. `Rotate` moves
  directions around the listener; `Tilt` and `Tumble` turn the field through
  vertical planes. The code leaves W unchanged and rotates X, Y, and Z.
  Automate `Rotate` for a source circling the listener, or put the plug-in on
  the bus when the entire scene should turn.
* **FocusPressPushZoom** aims a change at an `Azimuth` and `Elevation`. Set
  `Degree of transformation` to 0° for no change; at 90° all four modes pull
  the field to the chosen direction. What differs is how they get there:
  * **Focus** favors sounds already near that direction by reducing the
    opposite side. It keeps the sound directly at the target at roughly its
    original level.
  * **Zoom** also favors the target, but raises its level while keeping sounds
    at right angles closer to their original level. Check the meter when
    switching from Focus to Zoom.
  * **Press** shifts sounds from across the field toward the target without
    strongly favoring the level of sounds that started there. At partial
    settings it retains more of the side and vertical directional components.
  * **Push** gathers the field toward the same target more strongly at partial
    settings. In the code, Press scales the side and vertical components by
    the cosine of the angle; Push scales them by its square, so those
    components shrink faster as you raise the control.

  Use Focus or Zoom to draw attention to a region; use Press or Push when you
  want the whole field to converge toward it. Compare all four at the same
  angle through a decoder. ([ATK's explanation of these transforms](https://www.ambisonictoolkit.net/assets/files/2014-ICMC-ATK-Reaper.pdf))
* **Dominate** emphasizes a chosen azimuth and elevation. Its `Gain increase`
  control runs from 0 to 24 dB. At 0 dB the transform is unchanged; higher
  values can raise peaks, so watch the output meter. Use it to draw attention
  to a region of an already mixed field.
* **Mirror** reflects the field across a plane you set with azimuth and
  elevation. **MirrorO** has no controls: it keeps W and flips the signs of X,
  Y, and Z, sending each direction to the opposite side of the listener.
  These are distinct from rotation because they reverse the field's geometry.
* **NearfieldProximity** has two modes and a `Distance` control from 0.1 to
  5 meters. `Near Field Compensation` reduces proximity coloration;
  `Introduce Proximity Effect` adds it. The code filters X, Y, and Z while W
  passes unchanged. This changes low-frequency and phase cues, not the
  source's level or reverberation, so listen through the decoder rather than
  treating the distance value as a literal source position.

For a quick check, encode one mono sound to FuMa, put `RotateTiltTumble` after
the encoder, and automate `Rotate` over a short phrase. Listen on headphones
through the binaural decoder. Then move the same transformer to the B-format
bus: every encoded sound should now turn together. ATK's graphics show the
transform, but the decoded sound is the final check. ([Ambisonic Toolkit][4])

---

## Step 3: Decode for Monitoring and Delivery

On your decoder tracks, pick the decoder that matches your current listening or export target:

* Binaural for headphones.
* Stereo or UHJ for two‑channel speaker playback.
* Quad, 5.0, 7.0, or polygonal arrays for multichannel rooms.

Because decoding is separate from authoring and imaging, you can keep multiple decoder tracks active and monitor different targets with solos, or render stems per target without touching the B‑format bus. ATK’s decoder set covers virtual microphones, stereophony (including UHJ), multichannel arrays, and a dedicated binaural decoder. ([Ambisonic Toolkit][4])

---

## Render binaural and surround WAVs

Keep the four-channel FuMa B-format bus undecoded. Make separate tracks for the
headphone and speaker outputs. The [room calibration lesson]({{< rel "lectures/week-7/room-calibration/" >}})
explains the seven speaker positions and the difference between LFE and bass
management.

### Binaural output

Send channels 1–4 of the B-format bus to a four-channel decoder track. Put an
ATK FOA binaural decoder on that track; it turns the four-channel input into a
stereo output on channels 1–2. For a headphone copy, select only this track and
render a stereo WAV at 48 kHz / 24-bit with **Channels** set to **2**.

### Seven main speakers

1. Download the [course FuMa-to-AmbiX converter]({{< rel "downloads/DAD422-FuMa-to-AmbiX.zip" >}}).
   Unzip it. In REAPER, choose **Options → Show REAPER resource path in
   explorer/finder**, place `DAD422-FuMa-to-AmbiX.jsfx` in the `Effects` folder,
   and restart REAPER. The course converter has no external matrix file to go
   missing. Install the [IEM Plug-in Suite](https://plugins.iem.at/) too.
2. Make an eight-channel decoder track. Send channels 1–4 of the undecoded
   FuMa bus to its channels 1–4. Insert **DAD 422 FuMa to AmbiX (ACN SN3D)**,
   followed by **IEM AllRADecoder**. Keep the converter's four inputs and four
   outputs on channels 1–4 in the FX pin connectors.
3. In AllRAD, select **SN3D** input and first-order decoding. [Import the
   classroom 7.1 layout]({{< rel "presets/itu-7.1-0+7+0-allrad-layout.json" >}})
   and click **Calculate Decoder**. Its two imaginary speakers help the decoder
   calculate the layout; they do not feed output channels.

AllRAD sends audio to the seven main-speaker slots. Our eight-channel WAV uses
this order:

| WAV channel | Speaker |
| ---: | --- |
| 1 | Front left |
| 2 | Front right |
| 3 | Center |
| 4 | LFE |
| 5 | Side left |
| 6 | Side right |
| 7 | Rear left |
| 8 | Rear right |

### The LFE channel

Channel 4 is a real, separate LFE channel. AllRAD does not create it from the
ambisonic field. The monitoring system may also send bass from the seven main
channels to the subwoofer through bass management. That playback routing does
not put audio into channel 4 of your WAV. A silent LFE channel is possible in
general, but Project 03 asks you to put a deliberate effect there.

Build the 7.1 render path in REAPER this way:

1. Create a track named `7.1 PRINT` and set its **track channels** to **8**.
   Leave its FX chain empty. This is the track you will render.
2. Open the AllRAD decoder track's routing window. Add a send to `7.1 PRINT`
   with **Audio 1–8 → 1–8**. Turn off **Master/parent send** on the decoder
   track so it reaches the print bus only once.
3. Create a separate track named `LFE EFFECT`, outside the B-format folder.
   Choose one or two sounds that need extra impact. If the source is a mono
   recording, copy its item to `LFE EFFECT`, or make a **Pre-FX** send from its
   source track before the ATK encoder. If the source is already encoded to
   four-channel FuMa, set a send's **Audio** routing to **mono source channel 1
   (W) → mono destination channel 1** on `LFE EFFECT`. W is the
   omnidirectional component. Do not sum W, X, Y, and Z into mono or use the
   whole B-format bus as an automatic LFE feed. Low-pass `LFE EFFECT` at or
   below 120 Hz.
   Keep the original source in the main mix so the LFE augments rather than
   replaces its bass.
4. Open `LFE EFFECT`'s routing window and add a send to `7.1 PRINT`. Change
   the send's **Audio** routing from its default stereo pair to **mono source
   channel 1 → mono destination channel 4**. A mono item may appear on both
   channels 1 and 2 of a REAPER track; selecting source channel 1 avoids
   sending two copies. Turn off **Master/parent send** on `LFE EFFECT`.
5. Keep `LFE EFFECT` out of the FuMa bus and the AllRAD input. A send into the
   decoder track before AllRAD may be replaced when the plug-in writes its
   speaker feeds. A direct hardware output to the subwoofer lets you monitor
   it, but does not put that signal into the rendered WAV. The send to channel
   4 of `7.1 PRINT` does.

To listen, keep both the AllRAD decoder track and `LFE EFFECT` **unmuted**.
Turning off **Master/parent send** prevents them from reaching the master
directly; it does not silence their sends to `7.1 PRINT`. Monitor through
`7.1 PRINT`, routed to the room's calibrated eight-channel output path. Use
only one monitoring path so you do not hear a second copy through the stereo
master. That hardware routing lets you listen; the WAV still comes from
rendering `7.1 PRINT`.

Keep essential bass in the main-speaker mix. The room's LFE calibration handles
the playback level; do not add a 10 dB boost to the LFE track to imitate it.

### Export and check

Select only `7.1 PRINT` and choose **Stems (selected tracks)** in REAPER's
Render window. Enable **Multichannel tracks to multichannel files**, set
**Channels** to **8**, and
choose WAV at 48 kHz / 24-bit. This creates one eight-channel interleaved file.
Reimport a short test render and inspect all eight waveforms. Check that the
seven main channels carry audio, channel 4 contains only your intended LFE
effect, and the file has eight channels. Listen to the binaural render on
headphones. Audition the 7.1 file on the calibrated classroom system.

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
