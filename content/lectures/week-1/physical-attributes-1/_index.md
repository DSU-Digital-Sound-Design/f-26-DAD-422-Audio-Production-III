+++
title = "Physical Attributes of Sound - Part I"
outputs = ["Reveal"]
[reveal_hugo]
margin = 0.2
+++

## Oscillation and Vibration

{{< slide-columns >}}
{{< slide-column title="Oscillation" >}}
* Repetitive back-and-forth motion around a reference point
{{< /slide-column >}}
{{< slide-column title="Vibration" >}}
* A specific physical form of oscillation
* Typically involves a mass moving around its equilibrium
* A fundamental source of sound when that equilibrium is disturbed
{{< /slide-column >}}
{{< /slide-columns >}}

{{% note %}}
* Oscillation is the broader concept; vibration is its physical and acoustic manifestation.
* In musical contexts, systems (like strings or membranes) vibrate around stable equilibrium to sustain sound.
* Without a restoring force or with friction, vibration ceases.
{{% /note %}}

---

## Simple Harmonic Motion (SHM)

{{< slide-split src="circular-to-sine.svg" alt="A point moving around a circle at constant speed, with its vertical height traced out to the right as a sine wave." image-side="left" compact="true" >}}
* Restoring force proportional to displacement (Hooke's Law)
* Described by a [sinusoidal function](https://en.wikipedia.org/wiki/Simple_harmonic_motion)
* Defined by amplitude, frequency (or period), and phase
* Sine waves are the purest form of sound, and build every complex one

**Play with it:** [circular motion → SHM](https://physics.bu.edu/~duffy/HTML5/SHM_circular_motion.html) · [mass on a spring](https://www.physicsclassroom.com/Physics-Interactives/Waves-and-Sound/Mass-on-a-Spring/Mass-on-a-Spring-Interactive) · [SHM visualizer](https://ophysics.com/w0.html)
{{< /slide-split >}}

{{% note %}}
* Walk the figure left to right: the point goes around the circle at a constant rate, and the wave on the right is nothing but its height plotted against time.
* Enables mathematical modeling of real-world systems (like [mass-on-a-spring simulations](https://ophysics.com/w1.html) or [pendulums](https://phet.colorado.edu/en/simulation/pendulum-lab)).
* Foundation for Fourier analysis and spectral decomposition.
* Provides insight into resonance phenomena.
{{% /note %}}

---

## Complex Vibrations

* Real acoustic signals are rarely pure sine waves
* Comprised of multiple SHMs summed together
* Complex waveforms define timbre and texture

{{< audio-demo type="harmonics" compact="true" >}}

{{% note %}}
* Any sound can be decomposed into sine components (Fourier series/transform).
* This decomposition is essential for synthesis, analysis, and understanding timbre.
* Instruments derive their characteristic tone from the harmonic content.
* Demo audio plays in the window you click — run it from the stage window. Start on the sine preset, then push harmonics in one at a time; end with the saw/square presets.
{{% /note %}}

---

## Amplitude and the Signal Envelope

{{< slide-columns >}}
{{< slide-column title="Concepts" >}}
* **Amplitude**: peak height; correlates with loudness
* **Envelope**: the outline of amplitude over time
* Attack → Decay → Sustain → Release
{{< /slide-column >}}
{{< slide-column title="Design an envelope" >}}
{{< audio-demo type="adsr" compact="true" >}}
{{< /slide-column >}}
{{< /slide-columns >}}

{{% note %}}
* Envelopes shape the perceptual character of sounds (e.g., a piano vs. violin).
* Differentiates between impulse versus continuous signals.
* Crucial for sound synthesis, envelope generators, and expressive control.
* Reading: [ADSR stages](https://en.wikipedia.org/wiki/Envelope_%28music%29), [temporal envelope and fine structure](https://en.wikipedia.org/wiki/Temporal_envelope_and_fine_structure).
* Demo audio plays in the window you click — run it from the stage window. Try attack at minimum (pluck) vs. attack near 1 s (pad) on the same pitch.
{{% /note %}}

---

## Period and Frequency

{{< slide-columns >}}
{{< slide-column title="Period" >}}
* Time for one complete oscillation (T)
{{< /slide-column >}}
{{< slide-column title="Frequency" >}}
* Number of cycles per second (Hz); frequency = 1 / period
{{< /slide-column >}}
{{< /slide-columns >}}

{{< audio-demo type="sine" compact="true" >}}

{{% note %}}
* Frequency determines perceived pitch.
* Important for tuning, acoustic analysis, and digital sampling systems.
* Temporal and frequency domains are dual perspectives of sound.
* Demo audio plays in the window you click — run it from the stage window. Sweep the frequency slider and read f and T = 1/f changing together.
{{% /note %}}

---

## Frequency and Period Conversion

{{< slide-columns >}}
{{< slide-column title="Frequency (f)" >}}
* Number of cycles per second, measured in hertz (Hz)
* Formula: f = 1 / T
* Try it: [SensorsONE frequency→period calculator](https://www.sensorsone.com/frequency-to-period-calculator/)
{{< /slide-column >}}
{{< slide-column title="Period (T)" >}}
* Time for one complete cycle, measured in seconds
* Formula: T = 1 / f
* More examples: [Omni Calculator – Frequency](https://www.omnicalculator.com/physics/frequency)
{{< /slide-column >}}
{{< /slide-columns >}}

{{% note %}}
* Frequency and period are exact inverses: if one doubles, the other halves.
* Worked examples:
  * If T = 0.01 s, then f = 1 / 0.01 = 100 Hz.
  * If f = 440 Hz (concert A), then T ≈ 1 / 440 ≈ 0.00227 s.
* Teaching tip:
  * Show a single-cycle waveform and label the horizontal span as T; then remind students that frequency is "how many of those spans fit into 1 second."
* Forward-looking connection:
  * This inverse relationship underlies sample-rate reasoning in DAWs and will resurface when we discuss aliasing, FFT window lengths, and time–frequency trade-offs later in the course.
{{% /note %}}

---

## Phase

{{< slide-columns >}}
{{< slide-column title="Concept" >}}
* Describes the position within a cycle (degrees or radians)
* Two waves with same frequency and amplitude but different phase can behave differently together
{{< /slide-column >}}
{{< slide-column title="Impact" >}}
* Asynchronous phase shifts may be imperceptible
* Simultaneous multi-source phase relationships affect loudness, timbre, and spatial cues
{{< /slide-column >}}
{{< /slide-columns >}}

{{% note %}}
* Phase is critical in audio mixing (phase alignment) and stereo imaging.
* Misaligned phases can cause destructive interference or comb filtering.
* Phase differences contribute to perceptual features like localization.
{{% /note %}}

---

## Logarithmic Scales in Acoustics

{{< slide-columns >}}
{{< slide-column title="Why Logarithmic?" >}}
* Human perception of stimulus is proportional to logarithm of intensity (Fechner's Law)
* Compresses wide dynamic ranges into manageable scales
{{< /slide-column >}}
{{< slide-column title="Applications" >}}
* Express acoustic quantities (power, intensity, pressure) in decibels (dB)
* Aligns measurement scale with human hearing sensitivity
{{< /slide-column >}}
{{< /slide-columns >}}

{{% note %}}
* Decibel scale enables intuitive understanding of large acoustic ranges.
* Helps connect physical measurement with perceptual loudness.
* Foundational to metering, audio level calibration, and SPL measurement.
{{% /note %}}

---

## Common Sound Levels

{{< slide-split src="decibel-scale.svg" alt="A decibel scale from 0 to 180 dB, marking the threshold of hearing, normal conversation, a live rock band at the pain threshold, and a rocket launch." image-side="left" >}}
* \~180 dB – Rocket launch (irreversible hearing loss)
* \~120 dB – Live rock band (pain threshold)
* \~60 dB – Normal conversation
* \~0 dB – Threshold of hearing
{{< /slide-split >}}

{{% note %}}
* Human hearing spans \~0–120 dB over perceived loudness.
* Sustained levels above \~85 dB risk hearing damage—key for safety in sound professions.
* Real-world examples help contextualize abstract numbers.
{{% /note %}}

---

## RMS Amplitude

{{< slide-split src="peak-vs-rms.svg" alt="A sine wave with its peak amplitude, its RMS amplitude at 0.707 of the peak, and its peak-to-peak amplitude marked." image-side="left" >}}
* **RMS** measures the energy of an oscillating signal
* Squaring the signal makes positive and negative deflections both count toward the average
* Tracks perceived loudness far better than peak level does
{{< /slide-split >}}

{{% note %}}
* RMS = sqrt(mean(square(signal))).
* For pure sine waves: RMS ≈ 0.707 × peak.
* Crucial for accurate loudness estimation in signal processing and metering.
{{% /note %}}

---

{{< slide class="compact" >}}

## Superposition and Interference

* **Superposition**: multiple waves add algebraically to produce a complex resultant
* **Interference**: constructive amplifies, destructive cancels
* **Beats** arise from near-frequency waves (fluctuating amplitude)

{{< audio-demo type="phase" compact="true" >}}

{{% note %}}
* Fundamental to understanding room acoustics, comb filtering, and waveform texture.
* Beats are used intuitively in tuning and signal sensing.
* Destructive interference is core to noise cancellation technologies.
* Demo audio plays in the window you click — run it from the stage window. Play both, slow the detune toward 0 (beats slow down), then check invert at 0.0 Hz for total silence.
{{% /note %}}
