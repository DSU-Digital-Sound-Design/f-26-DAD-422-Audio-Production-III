+++
title = "Foundations of Sound"
outputs = ["Reveal"]
[reveal_hugo]
margin = 0.2
+++

## Course overview

- We'll begin with acoustics and psychoacoustics because binaural audio, ambisonics, and Dolby Atmos all depend on how sound behaves and how we perceive it.
- Over the semester, we'll work with stereo, binaural audio, ambisonics, 5.1, and Dolby Atmos.
- Today's class ends with a listening session that compares these formats.

{{% note %}}
- Everything that follows depends on the physics of sound and how we perceive it. In week 9, Atmos's binaural renderer will ask you to choose a Near, Mid, or Far setting. That choice draws on the material from today's third slide.
{{%/ note %}}

---

## Fundamentals of sound

{{< slide-split
  src="https://web.archive.org/web/20251116163351if_/https://www.healthyhearing.com/uploads/images/the-basics-of-hearing-hh19.jpg"
  alt="Diagram showing how sound travels through the outer, middle, and inner ear"
>}}
- We can study sound in three ways: as physical vibrations and waves, as activity in the ear, and as a perceptual experience.
- Sound, noise, and music are contextual labels. The same signal may fit any of them, depending on its purpose and setting.
{{< /slide-split >}}

{{% note %}}
- These three perspectives organize the course. The recording weeks focus on physical acoustics, the psychoacoustics weeks cover physiology and perception, and every mix raises questions about what listeners hear.
- Context matters in immersive work because deciding what counts as noise is a design choice.
{{%/ note %}}

---

{{< slide class="compact" >}}

## How you locate a sound

- According to Rayleigh's duplex theory from 1907, interaural time differences help us locate low frequencies, while interaural level differences help us locate high frequencies.
- The maximum time difference across a human head is about 650 microseconds.
- The head shadow depends on frequency. For a sound 90 degrees to one side, the shadow measures about 10 dB at 3 kHz, 20 dB at 6 kHz, and 35 dB at 10 kHz. Below roughly 2 kHz, sound waves bend around the head and weaken this cue. That is why hearing relies on both time and level differences.

{{% note %}}
- These figures come from chapter 1 of *Immersive Sound*, written by Wenzel, Begault, and Godfroy-Cooper. The chapter also provides the material for the next slide.
- The week 3 psychoacoustics lecture examines each point in detail. Today is only an introduction.
{{%/ note %}}

---

{{< slide-split
  src="image.png"
  alt="Diagrams showing cone-of-confusion positions that produce identical localization cues"
  compact="true"
>}}
## The cone of confusion

- Sounds arriving from several directions can produce identical time and level differences. Those two cues alone cannot distinguish front from back or up from down.
- The pinna resolves elevation with a spectral notch that slides from about 5 kHz for sounds straight ahead to about 10 kHz for sounds overhead.
- Head movement provides more information. When you turn your head, both cues change and help reveal the sound's direction.

{{< /slide-split >}}

{{% note %}}
- This slide explains why headphone Atmos needs HRTFs and why VR needs head tracking. A renderer must simulate the filtering of the pinna and account for the listener's head movements.
- Source: *Immersive Sound*, ch. 1.
{{%/ note %}}

---

## How you judge distance

- In a free field, the sound level falls by 6 dB each time the distance doubles. To make a sound seem half as far away, however, its level must increase by about 10 dB.
- Indoors, the strongest cue is the ratio of reverberant to direct sound.
- Familiar sounds can override these cues. A shout tends to sound far away, while a whisper tends to sound close, regardless of playback level.

{{% note %}}
- You will often adjust the ratio of reverberant to direct sound when mixing. In stereo, you can change it with reverb sends. In Atmos, you can change an object's perceived distance.
- Source: *Immersive Sound*, ch. 1. The week 2 auditory distance lecture covers the research in detail.
{{%/ note %}}

---

## Immersive audio technologies

{{< slide-columns >}}
{{< slide-column title="Dolby Atmos" >}}
Atmos is an object-based format. Sounds carry position metadata, and a renderer maps them to the available speakers.
{{< /slide-column >}}
{{< slide-column title="Ambisonics" >}}
Ambisonics is a scene-based format. It uses spherical harmonics to encode a full sphere of sound, which can then be decoded for different speaker layouts.
{{< /slide-column >}}
{{< /slide-columns >}}

{{% note %}}
- Today provides a brief introduction and a first chance to listen. We will spend most of the semester working with these two formats.
- For now, focus on the difference between scenes and objects. Ambisonics captures a sound field that a system decodes for a given speaker layout. Atmos assigns positions to individual sounds, then lets the renderer map them to the speakers.
{{%/ note %}}

---

## Listening session

- We'll listen to some 5.1 mixes with the time we have left.

{{% note %}}
- Listen for how each format changes your sense of space and placement instead of counting speakers.
- Ask students where they heard specific sounds. Their answers may differ, which previews the HRTF discussion in week 3.
{{%/ note %}}

---

## Source

The localization and distance material comes from Elizabeth Wenzel, Durand Begault, and Martine Godfroy-Cooper, "Perception of Spatial Sound," ch. 1 of Agnieszka Roginska and Paul Geluso, eds., *Immersive Sound* (Routledge, 2017).
