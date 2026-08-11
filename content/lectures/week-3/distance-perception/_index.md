+++
title = "Distance Perception in Mono"
outputs = ["Reveal"]
[reveal_hugo]
margin = 0.2
+++

## Acoustical and Psychoacoustic Properties for Mono Sound Walk

* Explore how sound changes with distance in a mono mix
* Identify psychoacoustic cues that suggest depth and movement
* Apply these cues in the Mono Sound Walk project
* Practice strategies to simulate space without stereo

{{% note %}}

* Open with the idea: even in mono, sound can **suggest distance** and **movement** if you shape it intentionally.
* Explain that acoustical properties (volume, frequency loss, reverberation) and psychoacoustic perception (how the brain interprets these changes) work together.
* Stress that this knowledge isn’t abstract: students will use it directly in their Mono Sound Walk.
* Frame today’s goal as “learning how to fake space in one channel” using practical design tools (automation, EQ, reverb, delay).

{{%/ note %}}

---

## Distance Illusion: Guess the Distance

* I will play the same mono clip three times: take A, take B, take C.
* Your task: identify which take is farthest and estimate the distance bin.
* Bins to choose from: 1–3 m, 4–8 m, 10–20 m.
* Listen for three cues: level change, high-frequency roll-off, and the direct-to-reverberant balance.

{{% note %}}
REAPER setup for the demo (mono signal path):

* Source: one short, steady sound from your walking video or a dry SFX. Downmix to mono or insert JS: Utility/mono on the track.
* FX chain order: ReaEQ (low-pass) → ReaVerb (or ReaVerbate) → optional ReaDelay for early-reflection sketch.
* Create three takes or snapshots with these starting points:

Near (1–3 m):

* Gain: 0 dB
* LPF cutoff: 10–12 kHz, gentle slope
* Reverb: small room IR or short algorithmic; wet 10–15%, predelay 5–10 ms

Mid (4–8 m):

* Gain: −6 dB
* LPF cutoff: 4–6 kHz
* Reverb: medium room; wet 20–30%, predelay 15–25 ms

Far (10–20 m):

* Gain: −12 dB
* LPF cutoff: 2.5–3.5 kHz
* Reverb: large room/hall; wet 35–45%, predelay 30–45 ms

Tips:

* Keep takes time-aligned. Toggle takes live or place them on three stacked tracks and A/B/C with mute/solo.
* Avoid panning; keep the master bus mono.
* If students guess too easily, narrow the differences (e.g., far at −9 dB and 4 kHz) to increase challenge.
  {{%/ note %}}

---

[![Distance Perception Demo](https://img.youtube.com/vi/D0Hm7D1-Ra4/0.jpg)](https://www.youtube.com/watch?v=D0Hm7D1-Ra4)

*Click to watch a short demo on distance perception in mono sound.*

{{% note %}}

* Introduce the video as a **demonstration of how mono sound alone can suggest distance**.
* Ask students to listen for three main cues:

  1. **Volume drops** as the source gets further away (inverse-square law).
  2. **High-frequency roll-off**, where distant sounds become more muffled.
  3. **Reverberation increases**, as reflections dominate over direct sound.
* Point out that these are the same cues they’ll be using in the **Mono Sound Walk project**.
* Encourage students to jot down what changes they notice first—volume, brightness, or reverb. This primes them for the later **REAPER “guess the distance” exercise**.
* After the video, recap: “Even without stereo imaging, these cues trick our ears into perceiving distance. That’s what we’re learning to design today.”

{{%/ note %}}

---

## Acoustical Properties of Distance Perception

* **Loudness drops** as the source moves farther away
* **High frequencies fade first**, making distant sounds more muffled
* **Reverberation builds up** in enclosed or reflective spaces
* **Direct-to-reverberant balance** shifts: more reflections = more distance

{{% note %}}

* Use a simple analogy: imagine hearing a friend speak while walking away down a hallway—quieter, less bright, and more echoey.
* Reinforce the **inverse-square law**: −6 dB per doubling of distance.
* Emphasize that **air absorption** mainly reduces brightness, which is why distant sounds lose detail.
* Explain that **reverb and reflections** dominate perception indoors, while outdoors, reverberation is less obvious but still matters (open vs. reflective surfaces).
* Stress the **direct-to-reverberant ratio (DRR)** as a powerful psychoacoustic cue—close = mostly direct, far = mostly reverberant.
* Connect back to project: these are the four main “knobs” they’ll manipulate in mono to simulate depth.

{{%/ note %}}

---

## Quick Calculator Demo: Inverse-Square Law

* Try −6 dB per doubling of distance
* Start: 1 m at 70 dB
* 2 m ≈ 64 dB
* 4 m ≈ 58 dB
* 8 m ≈ 52 dB

Resources (open one live):

* [Sengpiel Audio: Distance Law Calculator](https://sengpielaudio.com/calculator-distance.htm)
* [WKC: Inverse-Square Law Sound Calculator](https://www.wkcgroup.com/tools-room/inverse-square-law-sound-calculator/)

{{% note %}}
Demo plan (2–3 minutes):

* In the calculator, set 70 dB at 1 m; step to 2, 4, 8 m and read off the approximate drops (−6 dB per doubling).
* Ask students to predict 16 m before showing it.
* In REAPER, add a track volume envelope and set points at 0 dB, −6 dB, −12 dB, −18 dB to mirror 1, 2, 4, 8 m.
* Keep the master mono. Play once with and once without the envelope so students hear how level alone cues distance.
  {{%/ note %}}

---

## Automation Essentials in REAPER

* **Linear**: smooth, constant-rate change
* **S-Curve (Slow Start/End)**: gradual entry and exit
* **Fast Start**: steep change at the beginning, flattens later
* **Fast End**: flat at first, steep change at the end
* **Square**: instant jump, no transition
* **Bezier**: fully customizable shape for precision

Resources:

* [Kenny Gioia: Automation Basics (YouTube)](https://www.youtube.com/watch?v=IBPIjLLnDhk)
* [Automation Review](https://www.reapertips.com/post/10-automation-shortcuts-in-reaper)

{{% note %}}
Explain envelope shapes in plain terms:

* Linear = steady volume fade
* Fast Start = sudden drop, then gradual
* Fast End = gradual, then sudden drop at the end
* S-Curve = natural, speech-like fades
* Bezier = lets you draw any curve

Connect shapes to distance/motion metaphors:

* Fast Start → object leaving suddenly
* Fast End → object approaching then disappearing quickly
* S-Curve → natural pass-bys
  {{%/ note %}}

---

## Automation Demo: Write, Touch, Latch

* Try **Write** mode: captures every move live
* **Touch**: adjusts only while fader is touched
* **Latch**: holds last change until stopped
* Practice: automate volume for a car “approach and pass-by” in mono

{{% note %}}
Keep demo under 60 seconds:

1. Put REAPER in Write mode.
2. Play clip, move volume fader to simulate approach → pass → recede.
3. Show how Touch/Latch differ for finer control.
4. Ask: “Which envelope shape would you use for this?”
   {{%/ note %}}

---

# Volunteer to try volume automation?

---

## Frequency Response (High-Frequency Roll-off)

- High frequencies attenuate faster than low frequencies.
- Distant sounds lose high frequencies, creating a "muffled" effect.
- Use low-pass filtering to replicate distant sounds.

{{% note %}}

- High frequencies diminish more rapidly over distance due to atmospheric absorption, making distant sounds softer and less defined.
- Low-pass filters in a DAW can simulate this effect, helping to create realistic distant sounds in the Mono Sound Walk.
- Encourage students to think about how reducing high frequencies alters the perception of distance in their soundscapes.

{{%/ note %}}

---

# Volunteer to try low-pass filtering?

---

## Reverberation and Distance

* **Near sounds**: dry, minimal reverb, bright and clear
* **Far sounds**: more reverb, muffled, less direct energy
* Adjust **wet/dry ratio** and **EQ** to simulate depth
* Reverb should match the **environment** (small room, hall, outdoors)
* Direct-to-reverberant balance is a key distance cue

{{% note %}}

* Stress that reverberation is a critical distance cue in enclosed spaces—our brain reads reflections as “farther.”
* Demonstrate: play a dry mono clip, then gradually add reverb and roll off highs to show how distance emerges.
* Encourage students to think not just about “more reverb = farther,” but also about the type of reverb and how EQ changes (HF loss, less clarity) reinforce the illusion.
* Tie back to their project: they’ll use reverb automation to “place” sounds along a path in the Mono Sound Walk.

{{%/ note %}}

---


## Direct-to-Reverberant Ratio (DRR)

* DRR = balance of direct sound vs. reverberant sound
* **As DRR decreases, perceived distance increases**
* High DRR → close, present, detailed
* Low DRR → far, diffuse, less intelligible

Resources:

* [Intro to DRR – Montana State Univ.](https://www.montana.edu/rmaher/eele217_fl19/lectures/lecture_12a.html?utm_source=chatgpt.com)
* [Review of Auditory Distance Cues (Larsen et al.)](https://pmc.ncbi.nlm.nih.gov/articles/PMC2677334/?utm_source=chatgpt.com)

{{% note %}}
Keep explanation short:

* Direct sound dominates when source is near.
* Reverberant field dominates when source is far.
* Students should listen for this in their Mono Sound Walk.
  {{%/ note %}}

---

**Convolution Reverb for Believable Rooms**

* Load real room impulse responses (IRs) into ReaVerb
* **OpenAIR**: free architectural IRs → realistic halls & rooms
* **Samplicity M7**: musical, smooth reverbs → great for creative use
* Apply: same mono sound at three “distances”
  * Near: short IR, low wet, bright EQ
  * Mid: medium IR, moderate wet, mild HF roll-off
  * Far: long IR, high wet, strong HF roll-off

Resources:

* [OpenAIR Impulse Response Library](https://www.openair.hosted.york.ac.uk/?utm_source=chatgpt.com)
* [Samplicity Bricasti M7 IR Pack](https://samplicity.com/bricasti-m7-impulse-response-files/?utm_source=chatgpt.com)

{{% note %}}
In-class demo (3 minutes):

* Play same mono clip three times (near/mid/far).
* Ask students: Which is which? What cues tell you?
* Reinforce how DRR + EQ changes combine with reverb length.
  {{%/ note %}}



---

## Starting Reverb Settings for Distance

- Close proximity: Short reverb time, low wet/dry mix.
- Medium distance: Moderate reverb, slight high-frequency damping.
- Far distance: Long reverb, heavy high-frequency roll-off.
- Adjust pre-delay for spatial reflection.

{{% note %}}

- For close proximity, use minimal reverb and pre-delay to maintain the dry sound with clear mids and highs.
- In medium-distance settings, more reverb and slight EQ changes simulate a natural room tone.
- To create far distances, use long reverb and reduced clarity by dampening high frequencies.
- Pre-delay settings affect how the sound reflections are perceived, adding a sense of depth.

{{%/ note %}}


---

## Advanced Automation: Tail and Pre-delay

- Tail length: Adjust reverb tail for room size.
- Pre-delay: Automate for proximity changes.
- Combine wet/dry and pre-delay for complex depth.
- Simulate large spaces with longer reverb tails.

{{% note %}}

- Reverb tail length directly influences the perceived room size—long tails suggest large, open spaces.
- Pre-delay automation helps control the initial perception of sound distance.
- Blending changes in pre-delay with wet/dry ratio creates intricate space and depth effects.
- By manipulating the reverb tail, you can simulate a shift from a small room to a vast outdoor environment.

{{%/ note %}}

---


# Volunteer to try reverb?

---

## Practice Tips for Simulating Distance with Echo or Delay Automation

- Use echo/delay to create a sense of distance
- Adjust delay time for close or distant effects
- Modify feedback to simulate multiple reflections
- Combine delay with reverb for natural depth

{{% note %}}

- Echo/delay replicates real-world sound reflections, where greater delay suggests a farther sound.
- Shorter delays (few milliseconds) for closer sounds, longer delays (50 ms to several hundred milliseconds) for distant ones.
- Higher feedback values create multiple reflections, mimicking large spaces.
- Reverb adds realism by simulating how sound reflects off surfaces in natural environments.

{{%/ note %}}

---

## Suggested Starting Settings for Delay Automation

- For close proximity (1-3 meters): 10-50 ms delay, 10-20% feedback
- For medium distance (3-10 meters): 50-150 ms delay, 30-40% feedback
- For long distance (10+ meters): 200-500 ms delay, 50-80% feedback
- Automation curves: adjust for linear or fast changes

{{% note %}}

- Close proximity: Use a delay time of 10-50 ms, with 10-20% feedback and a dry/wet mix of 20-30%. Keep reverb subtle or minimal.
- Medium distance: Set delay to 50-150 ms, 30-40% feedback, and dry/wet mix at 30-50%, with moderate reverb.
- Long distance: Increase delay to 200-500 ms, feedback to 50-80%, and dry/wet mix to 50-80%. Use larger reverb spaces for a more immersive effect.
- Automation curves adjust how quickly delay changes with sound movement.

{{%/ note %}}

---

# Volunteer to try delay?

---

## Motion and Dynamic Cues

- Changing sound level or frequency suggests movement.
- The Doppler effect simulates pitch changes as sound moves.
- Adjust sound properties dynamically to reflect movement.

{{% note %}}

- Dynamic cues, such as changes in volume or pitch, help convey movement in sound design.
- The Doppler effect, where pitch increases as a sound approaches and decreases as it moves away, is a powerful tool for simulating motion.
- Students can use these dynamic cues to create realistic movement and depth in their Mono Sound Walk projects, even without stereo sound.

{{%/ note %}}

---

# Volunteer to try Doppler effect?