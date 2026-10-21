---
title: "Atmos Mix"
number: "04"
weight: 4
week: 10
assigned: "2026-10-30"
due: "2026-11-16"
summary: "A Dolby Atmos mix of a song or a film excerpt, using object-based panning and automation in Logic Pro."
tools: ["Logic Pro", "Dolby Atmos Renderer"]
# the brief in the body already spells out deliverables and grading
rubric: false
---

## Project Overview

For this project, you will create a Dolby Atmos mix in Logic Pro. You have two options for source material:

1. [Aiguille Rouge – Bebe Grand](https://cambridge-mt.com/ms/mtk/#BabeGrand)
   1. Or pick a similarly difficult multitrack of your choice.
2. [The Film Lambs](https://dakotastateuniversity-my.sharepoint.com/:u:/g/personal/tate_carson_dsu_edu/EcGU4cdZ10ZNiSfQi1nFA9MBwZY9WMR_pZnY7I5Nv0VkFg?e=NOo8Rt)


Your task is to configure the session for Dolby Atmos, differentiate between bed and object tracks, and produce a technically compliant and creatively engaging immersive mix.

## Learning Objectives

By completing this project, you will:

* Configure Logic Pro for Dolby Atmos mixing at 48 kHz and 24-bit recording. For film, match the project frame rate to the supplied picture.
* Differentiate channel-based bed routing from separate object audio and position metadata, and justify your choices.
* Apply spatialization techniques to enhance immersion, narrative clarity, or musical impact.
* Meet Dolby Atmos loudness and technical delivery standards.
* Deliver a finished mix in both Logic Pro project format and ADM BWF format.

## Creative Expectations

* Allocate tracks intentionally to beds or objects based on their role in the mix.
* Use at least four object tracks with panning automation that includes a variety of movement types (e.g., lateral, vertical, front-to-back).
* Ensure spatial decisions serve the arrangement’s clarity, emotional tone, or storytelling.
* Maintain a cohesive balance between static and moving elements to avoid listener fatigue.

## Project Setup

### Session Configuration

1. **Set Project Audio Format**
   * Set the project sample rate to **48 kHz** in **File > Project Settings > Audio**. Use 24-bit recording for any new audio.
   * For film, set the frame rate in the project synchronization settings to match the picture; 24 fps is not a universal Atmos requirement.
2. **Enable Spatial Audio**
   * Navigate to `Project Settings -> Audio -> General`.
   * Under “Spatial Audio,” select **Dolby Atmos**.
   * Set “Surround Format” to **7.1.2**.
3. **Bed Tracks**
   * Use the Surround Panner when you want tracks to feed the shared channel-based bed. Bed panning can be static or automated.
4. **Object Tracks**
   * Use the 3D Object Panner for independent spatial positioning, size, or binaural settings. Objects may stay in place or move.
   * Automate movement to support creative goals.
5. **Monitoring**
   * In the Dolby Atmos plug-in, select the monitoring format that matches the actual speaker system, or a binaural renderer for headphones. Use 7.1.4 only with the corresponding speaker layout; our 7.1 room has no discrete height outputs.
   * Check placement in the available room and over headphones, including a comparison of the Dolby and Apple renderers.

## Mixing Guidelines

* Use panning automation on at least four object tracks, varying motion type and speed.
* Use the 3D Object Panner for object tracks. A stereo object track is valid and uses two object inputs; use its Spread control deliberately.
* On your Master track, meter **after** the Dolby Atmos Renderer plugin with the plugin's monitoring format set to **5.1** — the spec measures a 5.1 render, not your 7.1.4 monitor mix. For this project, stay at or below **-18 LUFS-I** integrated and **-1 dBTP**; quieter mixes are acceptable. These are music-delivery targets used for this course, not universal targets for all Atmos content. See the [Atmos delivery lesson](/lectures/week-11/atmos-delivery/) for the full QC pass.

## Submission Requirements

Submit the following:

1. Logic Pro project folder with all media included.
2. ADM BWF export of your final mix, verified by re-importing it into an empty project. Use **File > Export > Project as Spatial Audio > Dolby Atmos ADM BWF**; changing the monitoring format does not change the master export.
3. Written reflection (1–2 paragraphs) addressing:
   * Your approach to bed vs. object allocation.
   * The reasoning behind your spatial automation choices.
   * Any technical challenges and how you solved them.

## Grading Rubric (70 points total)

| Criterion | Exemplary | Proficient | Developing | Emerging | Points |
| --- | --- | --- | --- | --- | --- |
| **Bed and Object Use (19 pts)** | Bed and object routing is intentional and explained in the reflection; object placement, size, or metadata serves the mix | Routing works and most choices are explained; one choice needs clearer justification | Routing choices are unexplained, or the required object automation is incomplete | No meaningful distinction | /19 |
| **Spatial Design (16 pts)** | Height and surround placement serve the music or scene rather than demonstrating the format | Placement is effective and mostly purposeful | Elements placed around the field without evident reason | Effectively a stereo mix in an Atmos session | /16 |
| **Mix Balance (14 pts)** | The mix holds together across the bed and objects; nothing masks anything else | Balanced with one or two elements competing | Several elements masked or jumping forward | No balancing attempted | /14 |
| **Loudness and Delivery (12 pts)** | Loudness meets the course targets; the ADM reopens correctly and the project contains all media | On target with a minor delivery deviation | Loudness off target, or the ADM master has problems | Will not render to spec | /12 |
| **Binaural QC (9 pts)** | Checked on headphones; the binaural fold-down holds up with no collapsed or lost elements | Fold-down works with one element weaker than intended | Fold-down noticeably degrades the mix | Not checked | /9 |

**Total: \_\_\_ / 70**
