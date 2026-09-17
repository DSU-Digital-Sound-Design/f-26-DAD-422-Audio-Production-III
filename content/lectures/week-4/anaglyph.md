---
title: "Anaglyph: Binaural Spatialization"
summary: "Install Anaglyph, position a sound over headphones, and automate its movement, with a reference to the plugin controls."
tags: [binaural, anaglyph, spatial audio, HRTF, SOFA, reaper]
---

In [Binaural audio and recording](/lectures/week-4/binaural-recording/), you
heard how recordings can preserve the cues that help us locate sounds over
headphones. Anaglyph lets you add those cues to a mono recording and choose
where the sound appears to be.

Anaglyph positions a single mono source around your head. It uses filters based
on measurements of a head and ears to make the sound appear to come from a
chosen direction, including above, below, or behind you. How convincingly you
hear that position depends partly on how well the filters match your hearing.

You will use Anaglyph for the individual sources in
[Project 2](/projects/stereo/). Keep the project's stereo microphone recording
and Zoom H3-VR binaural recording on their own tracks. Those recordings already
contain spatial information; downmixing them through Anaglyph would turn each
into a single source.

Start by installing the plugin and positioning one sound. Then automate a move.
The control reference below explains the settings you can explore afterward.

> Listen on headphones. Binaural processing sends different cues to the left and
> right ears. Over speakers, each ear hears both channels, so the intended
> spatial effect may not hold.

## Installing

Download the release for your platform from the
[Anaglyph site](https://anaglyph.dalembert.upmc.fr/) and unzip it. On Windows, copy
`Anaglyph.vst3` into `C:\Program Files\Common Files\VST3\`. On macOS, copy
`Anaglyph.vst3` to `~/Library/Audio/Plug-Ins/VST3/` or `Anaglyph.component` to
`~/Library/Audio/Plug-Ins/Components/`. Rescan under Options, Preferences,
Plug-ins, VST.

The plugin ships filters computed at 44.1 kHz and 48 kHz. Run your project at
one of those rates or download the extra sample-rate package, or you will get
file-loading errors.

## Setting it up in REAPER

1. Put a mono recording on its own track. Use a separate track and Anaglyph
   instance for each source you want to position independently.
2. Set the track pan to center and leave it there. Anaglyph does the
   positioning. Use its controls to move the sound.
3. Add Anaglyph to the track's FX chain. Leave the track at two channels so the
   plugin can output separate left- and right-ear signals.
4. Set **INPUT CHANNEL MAPPING** to Stereo Downmix so a stereo file is summed
   into one source. This instance of Anaglyph positions that source at a single
   point. 
5. Put on headphones and drag the ball in the display before you automate
   anything.

In Top view, the display on the left shows the scene from above, with your
head at the center. **Top** and **Rear** switch the viewpoint and **ZOOM** changes the scale
of the view.

## First listening exercise

Loop a short mono recording, such as a voice or a sound effect. Keep **WET MIX**
at 100% so you hear the processed signal.

1. In Top view, drag the source to one side of the head, then the other. Watch
   **AZIMUTH**, the angle around your head, change as you move it. Use the display
   to check which side corresponds to positive and negative values.
2. Move the source in front of you and then behind you. Does it sound as though
   it stays behind you, or does it seem to move back to the front?
3. Change **DISTANCE**, measured in meters, while keeping the direction fixed.
   Listen for changes in level and in the sense of how close the sound is.
4. Change **ELEVATION**, the angle above or below ear level. Return it to 0°
   before trying another movement.

If front and back are hard to distinguish, try several options under
**CURRENTLY ACTIVE HRIR**. Each set contains a different listener's measured
filters. Keep the one where sounds behind you stay behind you. The
personalization section below explains these filters in more detail.

## Automating a move

Project 2 asks for at least two automation moves. Open the track's automation
envelope window and show the Anaglyph parameter you want to automate. An envelope changes a
parameter over time: draw points on it to set where the sound should be at
different moments.

**Fly-by.** Automate AZIMUTH from one side to the other and DISTANCE to dip to
the shortest distance you want at the moment of closest approach. The change
in distance helps the sound seem to approach and pass you. Leave the near-field
enhancements active for this exercise; their controls are explained below.

**Circle.** Sweep AZIMUTH through a full turn at constant DISTANCE. Listen for whether
the source stays behind you as it passes through the rear half of the circle.
If it seems to jump to the front, try another HRIR set or enable
**MICRO OSCILLATIONS**, which adds a small movement to help stabilize the
perceived position.

Automate ELEVATION on its own before you combine it with anything else. Elevation
can be difficult to judge and varies between listeners.

## Using Anaglyph in your mix

The DISTANCE control changes level and near-field filtering. To place a source
in a particular room or environment, you may also need reverb that matches the
space. Put that reverb after Anaglyph, or on a separate bus, so you are not
spatializing a reverb tail to a single point.

For Project 2, use Anaglyph to position individual sources alongside your stereo
and binaural recordings. Check the combined mix over headphones and listen for
whether the sources seem to belong in the same space.

## Control reference

You do not need to adjust every control to position a sound. Start with AZIMUTH,
ELEVATION, and DISTANCE, then use the sections below to address what you hear.
The **INFO** button in the lower right corner of the plugin opens its built-in
control descriptions.

### Source position

| Control | What it does |
| --- | --- |
| ELEVATION (deg) | Height of the source. 0° is level with your ears; positive values are above and negative values are below. |
| AZIMUTH (deg) | Angle around you. 0° is directly in front. Move the source in Top view to check the angle for each side. |
| DISTANCE (m) | How far away the source is, in meters. |
| MIN / MAX ATTEN. DIST. | The near and far bounds of the distance attenuation model. Inside the minimum and beyond the maximum, gain stops changing. |

Automate AZIMUTH, ELEVATION, and DISTANCE to move the source. MIN / MAX ATTEN.
DIST. sets the range over which distance changes affect its level.

### Distance attenuation

Gain falls off as `1 / distance ^ ATTEN. EXP.`

| Control | What it does |
| --- | --- |
| ATTEN. EXP. | The exponent in that formula. 1.0 is the physical inverse-distance law. Higher values make distance more dramatic. |
| BYPASS DIST ATTENUATION | Turns the level-versus-distance model off, leaving only the filtering cues. |

### Personalization

Binaural rendering filters with a head-related impulse response, an HRIR,
measured on a head. An HRIR is the time-domain representation of a
head-related transfer function, or HRTF. Both describe how sound changes on its
way to the ears from a particular direction.

Your ears may differ from those used for the measurements, which is one reason
the same filters work better for some listeners than others.

| Control | What it does |
| --- | --- |
| CURRENTLY ACTIVE HRIR | The HRIR set in use. The bundled choices include sets from the LISTEN database, such as `listen_irc_1008`. Try several and keep the one where sounds behind you stay behind you. |
| CUSTOM ITD | Replaces the measured interaural time difference, the difference in arrival time between the ears, with one modeled from your own head size. |
| HEAD CIRCUM. | Your head circumference in millimeters, used by that model. Measure with a tape above your ears. |
| BYPASS HRIR | Turns the ear filtering off. Useful for A/B: everything collapses back toward ordinary panning. |
| IR XFADE DUR. | Crossfade time between impulse responses when the source moves, in seconds. Low values like 0.05 stay responsive; high values like 0.4 remove zipper noise on fast moves. |
| NO INTERP. | Turns off interpolation between measured positions. Leave it off unless you are testing. |

If you automate a fast fly-by and hear stepping or zipper noise, IR XFADE DUR.
is the control to reach for.

### Near-field enhancements

These improve the sense of distance for sources close to the head.

| Control | What it does |
| --- | --- |
| BYPASS PARALLAX | Parallax picks the HRIR by the direction the sound actually arrives from at each ear, rather than from the center of the head. It matters most within arm's reach. |
| BYPASS ILD | The near-field interaural level difference model adjusts left and right levels by frequency to account for head shadowing, mostly by lowering the far ear rather than raising the near one. |

Leave both enhancements active for nearby sources, with their BYPASS controls
off. Enable each bypass in turn to compare the sound with and without that
enhancement.

### Externalization booster (STUDIO)

Over headphones, sounds often sit inside your head. This module adds the subtle
cues of hearing a monitor system in a treated studio, which pushes the image
outside. It is not a reverb plugin and not a substitute for your own sends.

| Control | What it does |
| --- | --- |
| CURRENTLY ACTIVE STUDIO | Which studio response is used: `room_01_studio_foley`, `room_02_studio_dry`, or `room_03_studio_warm`. |
| GAIN STUDIO | Level of the booster, independent of the direct binaural signal. |
| H / M / L | High-, mid-, and low-frequency EQ for the booster only. These controls do not change the direct sound. |
| SPATIAL DETAIL | The spatial detail of the studio response. OMNI has no directional detail; 2D adds horizontal directions; the 3D settings include height. Higher settings use more CPU. Leave this at its default for now; we will cover the underlying ambisonic format later. |
| BYPASS STUDIO | Turns the booster off. |
| STUDIO ONLY | Mutes the direct binaural sound and leaves only the booster. For testing. |

### Stabilization

| Control | What it does |
| --- | --- |
| MICRO OSCILLATIONS | Varies the rendered position very slightly. With a static source and no head tracking, the brain has trouble telling front from back; the small movement adds redundant cues and reduces that confusion. |

If a sound that should be behind you keeps jumping to the front even after you
choose an HRIR set, try enabling MICRO OSCILLATIONS.

### Output

| Control | What it does |
| --- | --- |
| GAIN | Overall plugin gain. |
| WET MIX | Blend of spatialized and raw signal: `out = wet × spatialized + (1 − wet) × raw`. Keep it at 100% for a full effect, lower it to pull a sound partly back toward the original. |
| BYPASS ALL | Passes the input through untouched. |
| CLIP | Turns red when the output has clipped. Click it to reset. |

Alt-click or double-click any control to return it to its default.

## Optional: loading other HRTFs

Start with the bundled HRIR sets. For a further comparison, you can load other
measurements stored in SOFA, a file format for spatial acoustic data. Files are
available from the [SOFA conventions
collection](https://www.sofaconventions.org/mediawiki/index.php/Files). They have
to be preprocessed first; the
[tutorials page](https://anaglyph.dalembert.upmc.fr/page-tutorials.html) links
the `anaglyph-hrtf-preprocess` Matlab package that does it, and the processed
files go into the plugin's resources alongside the ones that shipped with it.

Compare two HRTF sets on the same recording and at the same source position.
Listen for changes in tone and in how clearly you can locate the sound.

## Documentation and further examples

The website has a feature overview but no parameter manual. The reference is
built into the plugin: **the INFO button in the lower right corner opens a panel
describing every module and every control in alphabetical order.** Click it when
you are unsure what a knob does.

Beyond that:

- [anaglyph.dalembert.upmc.fr](https://anaglyph.dalembert.upmc.fr/) has the
  download, the About section, and release notes.
- The [tutorials page](https://anaglyph.dalembert.upmc.fr/page-tutorials.html)
  covers importing your own SOFA HRTF files, the Max control messages, and the
  Unity package.
- The [misc page](https://anaglyph.dalembert.upmc.fr/page-misc.html) lists DAW
  compatibility and known issues. Pro Tools is not supported on any platform;
  REAPER is fine.
- The [gallery](https://anaglyph.dalembert.upmc.fr/page-gallery.html) collects
  projects made with it, which is where to go for making-of material.
- The AES e-brief
  [*The Anaglyph Binaural Audio Engine*](http://www.aes.org/e-lib/browse.cfm?elib=19544)
  by Poirier-Quinot and Katz is the academic write-up.

