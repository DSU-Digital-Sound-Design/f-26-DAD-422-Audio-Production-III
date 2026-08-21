+++
title = "Foundations of Sound"
outputs = ["Reveal"]
[reveal_hugo]
margin = 0.2
+++

## Course Overview

- We start with acoustics and psychoacoustics, because binaural, ambisonics, and Atmos are all applied versions of both.
- The semester then works through the formats: stereo, binaural, ambisonics, 5.1, and Dolby Atmos.
- Today ends with a listening session in each of those formats.

{{% note %}}
- Everything later depends on the physics and the perception. When Atmos's binaural renderer asks you for a Near, Mid, or Far setting in week 9, it is asking you about the material on today's third slide.
{{%/ note %}}

---

## Fundamentals of Sound

![](https://www.healthyhearing.com/uploads/images/the-basics-of-hearing-hh19.jpg)

- The study of sound links three frames of reference: the physical (vibrations and waves), the physiological (the ear), and the perceptual (what we experience).
- Sound, noise, and music are contextual labels, and the same signal can be any of them depending on intent and situation.

{{% note %}}
- The three frames organize the whole course: physical acoustics in the recording weeks, physiology and perception in the psychoacoustics weeks, and the perceptual questions every time we mix.
- The contextual point gets practical in immersive work, where deciding what counts as noise is a design decision.
{{%/ note %}}

---

## How you locate a sound

- Duplex theory (Rayleigh, 1907): interaural time differences localize low frequencies, and interaural level differences localize highs.
- The maximum time difference across a human head is about 650 microseconds.
- The head shadow depends on frequency. At 90 degrees to the side, it measures about 10 dB at 3 kHz, 20 dB at 6 kHz, and 35 dB at 10 kHz. Below roughly 2 kHz the wave bends around the head and the shadow fails, which is why hearing needs both cues.

{{% note %}}
- These numbers come from Wenzel, Begault, and Godfroy-Cooper's chapter 1 of *Immersive Sound* (Roginska and Geluso, eds.), which is also the source for the next slide.
- The week 3 psychoacoustics lecture expands every item here, so today is a first pass, not a test.
{{%/ note %}}

---

## The cone of confusion

- Whole surfaces of directions produce identical time and level differences, so those two cues alone cannot tell front from back or up from down.
- The pinna resolves elevation with a spectral notch that slides from about 5 kHz for sounds straight ahead to about 10 kHz for sounds overhead.
- Head movement resolves the rest, because turning your head changes both cues in a direction-revealing way.

{{% note %}}
- This slide explains why headphone Atmos needs HRTFs and why VR needs head tracking. Without your pinna's filtering and your head's movement, the renderer has to fake both.
- Source: *Immersive Sound*, ch. 1.
{{%/ note %}}

---

## How you judge distance

- In a free field, level falls 6 dB for each doubling of distance. Perceptually, making a sound feel half as far away takes about 10 dB.
- Indoors, the strongest cue is the ratio of reverberant to direct sound.
- Familiarity biases everything: a shout reads as far away and a whisper reads as close, regardless of playback level.

{{% note %}}
- The reverberant-to-direct ratio is the cue you will manipulate constantly when mixing, from reverb sends in stereo to object distance in Atmos.
- Source: *Immersive Sound*, ch. 1. The week 2 auditory distance lecture covers the research in detail.
{{%/ note %}}

---

## Immersive Audio Technologies

### Dolby Atmos
- Atmos is an object-based format: sounds carry position metadata, and a renderer maps them to whatever speakers exist.

### Ambisonics
- Ambisonics is a scene-based format: it encodes the full sphere of sound with spherical harmonics and decodes to any layout.

{{% note %}}
- Today is just names and a first listen; we spend most of the semester inside these two formats.
- The core distinction to plant now: channels (ambisonics decodes to whatever speakers you have) versus objects (Atmos places sounds and the renderer figures out the speakers).
{{%/ note %}}

---

## Listening session

- 5.1: a Steven Wilson remix from *Hand. Cannot. Erase.* (Blu-ray 5.1), for discrete-channel listening.
- Atmos: The Beatles, *Abbey Road* 2019 Atmos remix on Apple Music, played against the stereo version.
- Binaural: Kraftwerk, *3-D The Catalogue*, the Headphone Surround 3D mix, plus the NPR binaural pieces from the course site.
- Height: Dolby's "Amaze" trailer, played from the downloaded file, since YouTube playback is not actually Atmos.

{{% note %}}
- Listen for how each format changes your sense of space and placement, rather than counting speakers.
- Have students say where specific sounds appeared to be. Disagreement between listeners is part of the lesson, and it previews the HRTF discussion in week 3.
{{%/ note %}}

---

## Source

The localization and distance material comes from Elizabeth Wenzel, Durand Begault, and Martine Godfroy-Cooper, "Perception of Spatial Sound," ch. 1 of Agnieszka Roginska and Paul Geluso, eds., *Immersive Sound* (Routledge, 2017).
