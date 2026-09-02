+++
title = "Introduction to Spatial Audio"
outputs = ["Reveal"]
[reveal_hugo]
margin = 0.2
+++

## Introduction to Spatial Audio

---

## Today: from hearing space to reproducing it

- Identify the cues that reveal width, height, and distance.
- Explain how distance, directivity, and reflections change a recording.
- Compare channel-based, object-based, and scene-based audio.

{{% note %}}

- The first half of the class asks how sound behaves in real spaces.
- The second half asks how recording and playback systems preserve or construct those spatial cues.
- By the end, students should be able to connect an acoustic observation to a production decision.

{{%/ note %}}

---

## The Spatial Dimension in Natural Sound

* Width: left to right placement
* Height: perceived vertical position
* Depth: perceived distance from the listener

{{% note %}}

- With two ears, the head, and the outer ears, we estimate direction and distance in three dimensions.
- Spatial hearing helps us locate events outside the field of view.
- Width, height, and depth are perceptual results. The acoustic cues that produce them change with the source, listener, and room.

{{%/ note %}}

---

## Outdoor sound fields

* Diffuse ambience arrives from many directions.
* Discrete events, such as birds or footsteps, remain localizable.
* With few nearby boundaries, reflections are usually weak or delayed.

{{% note %}}

- Wind, distant traffic, and flowing water often merge into background ambience.
- Bird calls, voices, and footsteps remain easier to locate.
- The balance between diffuse ambience and distinct events helps a listener recognize an outdoor space.

{{%/ note %}}


---

## Indoor sound fields

* Direct sound carries the clearest location cue.
* Early reflections reveal nearby boundaries.
* Late reverberation suggests the room's size and absorption.

{{% note %}}

- Walls, floors, ceilings, and objects return delayed copies of the source.
- The delay, level, and spectrum of those reflections help us estimate room size and surface character.
- Strong early reflections can blur localization. A later, dense reverberant field can add spaciousness without pulling the image toward one wall.

{{%/ note %}}

---

## Listening 1: What space is this?

<audio src="cistern.wav" controls></audio>

{{% note %}}

- Recorded inside an old cistern.
- Echoes and reverberation suggest a closed, reflective space.
- Ask for the evidence before revealing the answer: indoor or outdoor, large or small, and which cue decided it?

{{%/ note %}}

---

## Listening 2: What space is this?

<audio src="sea-cave.wav" controls></audio>

{{% note %}}

- Recorded in a sea cave.
- Reverberations from waves and dripping water suggest an enclosed, natural space.
- Ask which cues distinguish the cave from the cistern.

{{%/ note %}}

---

## Listening 3: What space is this?

<audio src="forest-birds.mp3" controls></audio>

{{% note %}}

- Recorded in a forest with birds and wind.
- Open, natural sound with identifiable bird calls suggests an outdoor environment.
- Ask students to separate the diffuse bed from the localizable events.

{{%/ note %}}

---

## Listening 4: What space is this?

<audio src="bathroom-fan.wav" controls></audio>

{{% note %}}

- Recorded with a bathroom fan.
- The mechanical sound and enclosed reverberation suggest an indoor, small reflective space.
- Ask whether the source identity or the room cues provide the stronger answer.

{{%/ note %}}

---

## Listening 5: What space is this?

<audio src="cricket.wav" controls></audio>

{{% note %}}

- Recorded in the Californian desert, featuring a cricket.
- The clear, isolated sound suggests an open outdoor space with little environmental noise.
- Use this as the difficult case. A sparse recording does not reveal distance or enclosure as clearly as the first four examples.

{{%/ note %}}

---

## Level loss in a free field

- Each doubling of distance reduces sound-pressure level by about 6 dB.
- 1 m to 2 m to 4 m is two doublings, for a total drop of about 12 dB.

<img src="free-field.png" alt="Inverse-square spreading from an omnidirectional source" style="display:block;margin:1rem auto 0;max-height:300px;width:auto;">

{{% note %}}

- An omnidirectional source spreads a fixed acoustic power over a sphere. The sphere's area is `4πr²`, so intensity is `W / 4πr²`.
- At twice the distance, the same power covers four times the area. Intensity falls to one quarter, and sound-pressure level falls about 6 dB.
- Read the diagram from 1 m to 2 m, then ask students to predict 4 m. The answer is about 12 dB below the level at 1 m.
- Ask how the rule changes microphone placement. A close microphone captures more direct sound. Moving it back lowers the direct sound while the room contribution changes much less.
- Week 3 returns to this rule alongside air absorption, source familiarity, and the direct-to-reverberant ratio.


{{%/ note %}}

---

## Sound directivity

![](directivity.png)

{{% note %}}

- A polar plot shows level by angle around a source.
- The low-frequency pattern is broad. The high-frequency pattern narrows toward the front axis.
- Large wavelengths bend around the source more readily. Short wavelengths beam when the radiator is large relative to the wavelength.
- Directivity affects microphone placement, loudspeaker coverage, spill, and the spectrum of room reflections.
- Ask students which curve represents low frequency and what would change if the microphone moved off axis.

{{%/ note %}}


---

### Reading a loudspeaker directivity plot

![](monitor-directivity.jpg)

[Adam Audio Speaker Directivity Chart](https://www.adam-audio.com/blog/understanding-speaker-directivity-charts/)

{{% note %}}

- The horizontal axis is frequency. The vertical axis is the angle above or below the tweeter axis. Color shows level relative to the on-axis response.
- Low frequencies remain broad across many angles. Above several kilohertz, the strong central band narrows.
- The pinched and striped region around the crossover shows vertical lobing.
- A listener who stands up moves off the high-frequency axis first, so the monitor may sound darker.
- Ask how monitor height or tilt could keep the spectral balance more consistent.

{{%/ note %}}


---

### Tuba directivity

![](tuba.jpg)

{{% note %}}

- The left image shows microphones arranged at four elevation rings. The heat maps show frequency by azimuth at each elevation.
- Low frequencies radiate broadly. Above roughly 2 kHz, energy concentrates along the bell axis and drops sharply at the sides and rear.
- A microphone above and in front of the bell captures more articulation. Moving it off axis produces a darker tone without EQ.
- Ask students which microphone move would add brightness and which would reduce key and valve noise.

{{%/ note %}}


---

## Measuring directivity

- `Q = on-axis intensity / average intensity`
- `DI = 10 log10(Q)`
- An omnidirectional source has Q = 1 and DI = 0 dB. Larger values indicate narrower radiation.

{{% note %}}

- The last two slides showed directivity as a pattern. Q and DI reduce that pattern to values commonly printed on a loudspeaker specification sheet.
- Q compares intensity on the reference axis with the average intensity over a sphere for the same total acoustic power.
- A source radiating uniformly into a half sphere has Q = 2 and DI = 3 dB. Quarter-space gives 6 dB, and eighth-space gives 9 dB.
- Sources: Francis Rumsey, *Spatial Audio*, ch. 1, sec. 1.2.1, pp. 3 to 4; Tomlinson Holman, *Surround Sound: Up and Running*, ch. 2, p. 33.

{{%/ note %}}

---

### Sources in reflective spaces

![](OIP.jpg)

{{% note %}}

- The listener receives direct sound first, followed by early reflections and then a dense reverberant tail.
- Direct sound carries the strongest localization cue. Early reflections can widen or blur the image, depending on their delay and level.
- The late field contributes room size and envelopment.
- For a demonstration, compare a dry signal, early reflections alone, and late reverberation alone.

{{%/ note %}}

---

## Critical distance

- Direct sound falls about 6 dB per distance doubling. The reverberant field varies much less with source distance.
- At critical distance, direct and reverberant sound have equal levels.
- `Dc ≈ 0.057√(QV / RT60)` meters

{{% note %}}

- The formula uses source directivity Q, room volume V in cubic meters, and reverberation time RT60 in seconds.
- It assumes an approximately diffuse reverberant field. Real rooms vary with position and frequency.
- Inside critical distance, direct sound dominates. Beyond it, the reverberant field dominates and localization usually becomes less precise.
- This connects the free-field rule to indoor recording practice.
- Sources: Rumsey, *Spatial Audio*, ch. 1, secs. 1.2.1 and 1.2.2, pp. 2 to 5; Edwin Pfanzagl-Cardone, *The Art and Science of Surround and Stereo Recording*, ch. 9, sec. 9.1.4, p. 276.

{{%/ note %}}

---

## Critical distance and microphone placement

- Critical distance changes with frequency because source directivity and room absorption also change.
- In one tracking room, it measured 1.73 m at 63 Hz and 3.2 m at 8 kHz.
- A microphone at 2 m can be inside the direct field for treble but outside it for bass.

{{% note %}}

- The example shows why a microphone position is not simply close or distant across the entire spectrum.
- Spot microphones usually sit inside critical distance for clarity. Main-array placement depends on the intended balance of direct sound, ensemble blend, and hall response.
- Week 3 applies this idea to stereo arrays, including the Decca tree.
- Sources: Pfanzagl-Cardone, ch. 9, sec. 9.1.4, pp. 276 to 278, figures 9.3 and 9.8; Rumsey, ch. 1, sec. 1.2.3, p. 7.

{{%/ note %}}

---

## Boundary loading

- At low frequencies, one nearby boundary can add about 3 dB of output.
- Two boundaries can add about 6 dB. A three-boundary corner can add about 9 dB.
- Subwoofer placement uses this gain, but the room's modes and frequency response still require measurement.

{{% note %}}

- These are ideal low-frequency estimates. At shorter wavelengths, reflected and direct paths can interfere instead of producing uniform gain.
- The 3, 6, and 9 dB steps correspond to radiation into half, quarter, and eighth space.
- Ask why a monitor moved into a corner sounds bass-heavy and why repositioning may work better than EQ alone.
- Source: Holman, *Surround Sound: Up and Running*, ch. 2, p. 33, and the subwoofer section, p. 331.

{{%/ note %}}

---

### Three ways to represent spatial audio

* Channel-based: signals are assigned to a fixed loudspeaker layout.
* Object-based: audio carries position metadata for a renderer.
* Scene-based: a sound field is encoded independently of the playback layout.

{{% note %}}

- Stereo and ITU 5.1 are channel-based. Dolby Atmos combines channel beds with objects. Ambisonics is scene-based.
- Loudspeakers add the playback room to the result. Headphones need HRTFs to simulate direction and externalization.
- These categories describe how a system stores and renders space. They are not a quality ranking.
- Ask which representation adapts most easily to a different loudspeaker layout and why.

{{%/ note %}}


---

## Binaural recording

![Binaural Head Diagram](binaural-head.jpg)


{{% note %}}

- Binaural recording places microphones at or near two ear positions and is intended primarily for headphone playback.
- Interaural time and level differences provide lateral direction. The head and pinnae add frequency-dependent filtering that helps distinguish front from back and estimate elevation.
- A generic artificial head cannot match every listener's HRTF, so externalization and localization vary across people.
- Week 4 covers binaural recording methods, individual HRTFs, and listening examples.

{{%/ note %}}

---

## Ambisonics

- Scene-based representation of a full-sphere sound field
- Spherical-harmonic channels describe the field, not individual speakers
- Decoded for a loudspeaker array or binaural playback


{{% note %}}

- Michael Gerzon and Peter Fellgett developed Ambisonics in the 1970s as an alternative to fixed quadraphonic speaker feeds.
- A tetrahedral microphone can capture signals that are converted into first-order Ambisonics. A mix can also encode mono sources directly into the sound field.
- Spatial resolution depends on Ambisonic order and the playback system.
- Week 5 covers A-format, B-format, spherical harmonics, recording, and decoding.
- Further reading: [History of Ambisonics](https://intothesoundfield.music.ox.ac.uk/ambisonics)

{{%/ note %}}

---

## The ITU 5.1 reference layout

- Center: 0°
- Left and right: ±30°
- Surrounds: 100° to 120°

{{% note %}}

- ITU-R BS.775 standardizes a reference geometry so channel-based mixes translate between rooms.
- The LFE channel has no fixed position in the same sense as the five main channels. Bass management is a playback function, not an extra mix channel.
- Week 7 extends this geometry to 7.1 and measures the actual room before calibration.
- Source: ITU-R BS.775.

{{%/ note %}}

---

## Exit ticket: trace one spatial choice

- Physics: what changed in the sound field?
- Perception: which cue tells the listener about that change?
- Reproduction: which recording or playback method preserves it?

{{% note %}}

- Ask each student to choose one example from the lecture: microphone distance, off-axis placement, room reflections, binaural capture, or a spatial format.
- Their answer should link one physical change to one perceptual cue and one production decision.
- This reveals whether they can connect the lecture's three sections instead of recalling isolated terms.

{{%/ note %}}

---

## Appendix: early spatial-audio milestones

{{% note %}}

- These slides are optional context. The dedicated historical-context lectures carry the main chronology.

{{%/ note %}}

---

## Early sound reproduction

![](phonograph.jpg)

{{% note %}}

- Early commercial reproduction was monophonic, but a mono signal could still preserve distance cues through level, spectrum, and reverberation.
- What mono could not produce over one playback channel was a stable lateral image between independent channels.
- The historical-context lecture places these systems within the larger development of recorded and cinema sound.

{{%/ note %}}

---

## The Théâtrophone: early stereo transmission

![Théâtrophone poster by Jules Chéret](Theatrophone_-_Affiche_de_Jules_Cheret.jpg)

{{% note %}}

- In 1881, Clément Ader placed telephone transmitters across the Paris Opera stage and routed paired signals to telephone receivers.
- Listeners at the International Exposition of Electricity heard a remote performance with left-right differences.
- The experiment demonstrated two-channel spatial transmission decades before commercial stereophonic recording.

{{%/ note %}}

---

## Bell Labs in the 1930s

![](ideal.png)

{{% note %}}

- Steinberg and Snow asked how many microphone-to-loudspeaker channels were needed to preserve auditory perspective for an audience.
- Their ideal system used a dense microphone screen feeding a matching loudspeaker screen. A practical system used two or three channels.
- Three front channels gave a more stable central image across a wide seating area than a two-channel phantom center.
- The center-channel advantage does not depend on the precedence effect. It follows from reproducing central material through an independent center loudspeaker.
- Ask why the center channel matters more in a cinema than at a single centered stereo listening position.

{{%/ note %}}
