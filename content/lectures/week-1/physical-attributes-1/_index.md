+++
title = "Physical Attributes of Sound - Part I"
outputs = ["Reveal"]
[reveal_hugo]
theme = "moon"
margin = 0.2
separator = "##"
+++

## Oscillation and Vibration

### Oscillation

* Repetitive back-and-forth motion around a reference point

### Vibration

* A specific physical form of oscillation
* Typically involves a mass moving around its equilibrium
* A fundamental source of sound when that equilibrium is disturbed

{{% note %}}

* Oscillation is the broader concept; vibration is its physical and acoustic manifestation.
* In musical contexts, systems (like strings or membranes) vibrate around stable equilibrium to sustain sound.
* Without a restoring force or with friction, vibration ceases.
  {{%/ note %}}

---

**Simple Harmonic Motion (SHM)**

### Key Concepts

* Motion characterized by a restoring force proportional to displacement (Hooke’s Law)
* Described by a [sinusoidal function](https://en.wikipedia.org/wiki/Simple_harmonic_motion) (sine wave)
* Defined by amplitude, frequency (or period), and phase

### Relevance

* SHM serves as the theoretical backbone of acoustics
* Sine waves are the purest form of sound and build more complex waves

{{% note %}}

* Enables mathematical modeling of real-world systems (like [mass-on-a-spring simulations](https://ophysics.com/w1.html) or [pendulums](https://phet.colorado.edu/en/simulation/pendulum-lab)).
* Foundation for Fourier analysis and spectral decomposition.
* Provides insight into resonance phenomena.
  {{%/ note %}}

---

### Additional Interactive Visuals

* [Interactive Mass-Spring Simulation](https://www.physicsclassroom.com/Physics-Interactives/Waves-and-Sound/Mass-on-a-Spring/Mass-on-a-Spring-Interactive?utm_source=chatgpt.com)
* [Circular Motion → SHM Demonstrator](https://physics.bu.edu/~duffy/HTML5/SHM_circular_motion.html)
* [Web SHM Visualizer](https://ophysics.com/w0.html)

---

## Complex Vibrations

### Real-World Complexity

* Real acoustic signals are rarely pure sine waves
* Comprised of multiple SHMs summed together
* Complex waveforms define timbre and texture

{{% note %}}

* Any sound can be decomposed into sine components (Fourier series/transform).
* This decomposition is essential for synthesis, analysis, and understanding timbre.
* Instruments derive their characteristic tone from the harmonic content.
  {{%/ note %}}

---

## Amplitude and the Signal Envelope

### Amplitude

* Height from equilibrium to peak; correlates with loudness

### Signal Envelope

* Temporal outline of amplitude changes
* Identified stages: Attack → Decay → Sustain → Release (ADSR)

{{% note %}}

* Envelopes shape the perceptual character of sounds (e.g., a piano vs. violin).
* Differentiates between impulse versus continuous signals.
* Crucial for sound synthesis, envelope generators, and expressive control.
  {{%/ note %}}

**Visual resource**: [Envelope in music – ADSR stages](https://en.wikipedia.org/wiki/Envelope_%28music%29) and their [fine structure](https://en.wikipedia.org/wiki/Temporal_envelope_and_fine_structure).

---

## Period and Frequency

### Period

* Time for one complete oscillation (T)

### Frequency

* Number of cycles per second (Hz); frequency = 1 / period

{{% note %}}

* Frequency determines perceived pitch.
* Important for tuning, acoustic analysis, and digital sampling systems.
* Temporal and frequency domains are dual perspectives of sound.
  {{%/ note %}}

---


## Frequency and Period Conversion

### Frequency (f)

* Number of cycles per second, measured in hertz (Hz)
* Formula: f = 1 / T
* Try it: [SensorsONE frequency→period calculator](https://www.sensorsone.com/frequency-to-period-calculator/)
### Period (T)

* Time for one complete cycle, measured in seconds
* Formula: T = 1 / f
* More examples: [Omni Calculator – Frequency](https://www.omnicalculator.com/physics/frequency)

{{% note %}}

* Frequency and period are exact inverses: if one doubles, the other halves.
* Worked examples:
  * If T = 0.01 s, then f = 1 / 0.01 = 100 Hz.
  * If f = 440 Hz (concert A), then T ≈ 1 / 440 ≈ 0.00227 s.
* Teaching tip:
  * Show a single-cycle waveform and label the horizontal span as T; then remind students that frequency is “how many of those spans fit into 1 second.”
* Forward-looking connection:
  * This inverse relationship underlies sample-rate reasoning in DAWs and will resurface when we discuss aliasing, FFT window lengths, and time–frequency trade-offs later in the course.

{{%/ note %}}


---

## Phase

### Concept

* Describes the position within a cycle (degrees or radians)
* Two waves with same frequency and amplitude but different phase can behave differently together

### Impact

* Asynchronous phase shifts may be imperceptible
* Simultaneous multi-source phase relationships affect loudness, timbre, and spatial cues

{{% note %}}

* Phase is critical in audio mixing (phase alignment) and stereo imaging.
* Misaligned phases can cause destructive interference or comb filtering.
* Phase differences contribute to perceptual features like localization.
  {{%/ note %}}

---

## Logarithmic Scales in Acoustics

### Why Logarithmic?

* Human perception of stimulus is proportional to logarithm of intensity (Fechner’s Law)
* Compresses wide dynamic ranges into manageable scales

### Applications

* Express acoustic quantities (power, intensity, pressure) in decibels (dB)
* Aligns measurement scale with human hearing sensitivity

{{% note %}}

* Decibel scale enables intuitive understanding of large acoustic ranges.
* Helps connect physical measurement with perceptual loudness.
* Foundational to metering, audio level calibration, and SPL measurement.
  {{%/ note %}}

---

## Common Sound Levels

### Examples

* \~180 dB – Rocket launch (irreversible hearing loss)
* \~120 dB – Live rock band (pain threshold)
* \~60 dB – Normal conversation
* \~0 dB – Threshold of hearing

{{% note %}}

* Human hearing spans \~0–120 dB over perceived loudness.
* Sustained levels above \~85 dB risk hearing damage—key for safety in sound professions.
* Real-world examples help contextualize abstract numbers.
  {{%/ note %}}

---

## RMS Amplitude

### Definition

* Root-Mean-Square (RMS) measures energy of oscillating signals
* Takes absolute values into account positive and negative deflections

### Purpose

* More accurately correlates with perceived loudness than peak levels for sinusoidal and complex signals

{{% note %}}

* RMS = sqrt(mean(square(signal))).
* For pure sine waves: RMS ≈ 0.707 × peak.
* Crucial for accurate loudness estimation in signal processing and metering.
  {{%/ note %}}

---

## Superposition and Interference

### Superposition

* Multiple waves add algebraically to produce a complex resultant

### Interference

* Constructive: waves amplify each other
* Destructive: waves cancel out
* Beats arise from near-frequency waves (fluctuating amplitude)

{{% note %}}

* Fundamental to understanding room acoustics, comb filtering, and waveform texture.
* Beats are used intuitively in tuning and signal sensing.
* Destructive interference is core to noise cancellation technologies.
  {{%/ note %}}


