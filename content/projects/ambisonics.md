---
title: "Ambisonics"
number: "03"
weight: 3
week: 6
assigned: "2026-09-30"
due: "2026-10-19"
summary: "An original first-order ambisonic piece, or an ambisonic mix of a 20-plus track multitrack session. Ambisonic Toolkit throughout."
tools: ["REAPER", "Ambisonic Toolkit", "Zoom H3-VR"]
# the brief in the body already spells out deliverables and grading
rubric: false
---

## Project Overview

For this assignment, you have two options to choose from, both involving ambisonic techniques. See the quick checklist and due date below to align expectations.

### Requirements at a Glance

- Due: Monday 10/19
- Mix format: First‑order ambisonics (FOA) throughout
- Automation: At least two meaningful spatial automation moves total
- Tools: Reaper with Ambisonic Toolkit (ATK)
- Minimum render to submit: binaural stereo WAV (48 kHz, 24‑bit)
- Deliverables: render(s), consolidated Reaper project, 2‑paragraph reflection

### Project A: Original Ambisonic Work

Create an original 1–3 minute ambisonic music, sound design, or narrative fiction piece. Thoughtfully spatialize sources in FOA, considering front‑to‑back depth, height, and immersion. Your work should include:

- Ambisonic Recording: Use the Zoom H3‑VR in Ambisonic mode for one recording.
- Stereo Recording: Include one stereo technique (XY/ORTF/MS) and document it.
- Mono Sources: Allowed; encode to FOA before spatial transforms.
- Automation: Include at least two meaningful spatial automation moves total. These should support the narrative/arc and be visible as automation lanes.

Use the [Ambisonic Toolkit for Reaper](https://www.ambisonictoolkit.net/download/reaper/) plugins to mix your project.

### Project B: Multitrack Ambisonic Mixing

Alternatively, mix a session from [Mike Senior's multitrack library](https://www.cambridge-mt.com/ms/mtk/) that includes at least 20 tracks in the source session. You do not need to use all tracks; identify 2–3 focal elements and use spatialization to support them.

- Ambisonic Mix: Encode stereo/mono items to FOA and spatialize within an ambisonic field.
- Automation: Include at least two meaningful spatial automation moves total.
- Performance: Freeze/print heavy FX chains if CPU becomes a problem.

Use the Ambisonic Toolkit plugins to mix the project and document how each tool impacted your creative decisions.

## Spatialization Expectations

“Thoughtful spatialization” means:

- Panning and movement choices are purposeful, not random or distracting.
- Spatial decisions contribute to immersion, narrative clarity, or creative intent.
- Depth, height, and rotation enhance rather than overwhelm the listening experience.

## Project Setup

For both projects, encode all non‑ambisonic sources to first‑order ambisonics (FOA) B‑format. Then apply ambisonic transforms/panners for spatialization. Finally, decode to your listening environment (binaural, stereo UHJ, or 7.1) on a bus or the master.

FOA format consistency:

- Zoom H3‑VR typically exports AmbiX (ACN/SN3D). ATK tools operate in FuMa (WXYZ) convention.
- Use an AmbiX↔FuMa converter on FOA tracks as needed so encoders, processors, and decoders all match format and normalization.

Reaper routing reminder:

- FOA tracks carry 4 channels. Place encoders on mono/stereo items → FOA transform/panners → send to a master with a decoder.
- Put the decoder on the master (or dedicated ambisonic bus), not per‑track.
- Set master track channel count to 2 for binaural renders, or 8 for 7.1.

![](https://depts.washington.edu/dxscdoc/Help/Tutorials/atknetwork.png)

## Rendering

Render one binaural (for grading) and one 7.1 version of your mix (for us to listen to in class). 

## Submission Requirements

Submit the following:

1. Render(s): Binaural WAV (48 kHz, 24‑bit) and 7.1 render.
2. Reaper Project: Use “Save As… → Copy all media into project directory” to consolidate. Zip the folder.
   - Naming: `lastname_firstname_ambisonics_v1.zip`
3. Written Reflection: ~250–400 words addressing some or all of the prompts below. Include at least one screenshot of your session routing/automation and, for Project A, a photo of the stereo mic setup.
   - Stereo Recording Technique: Which technique did you use (XY/ORTF/MS)? What was the source? Include a photo.
   - Zoom H3‑VR Recording: What did you record and why?
   - Automation: Which spatial parameters did you automate and why?
   - Plugin Usage: How did ATK (and any converter) shape your decisions? Be specific.
   - Challenges & Solutions: What issues arose? How did you solve them?
   - Creative Process: How does spatialization serve the piece’s intent?

## Common Pitfalls

- Mismatched AmbiX/FuMa order/normalization causing rotated/tilted scenes.
- Placing decoders on individual tracks instead of the master/bus.
- Master channel count left at 2 while auditioning 7.1.
- Skipping FOA encoding for stereo items before spatial transforms.

