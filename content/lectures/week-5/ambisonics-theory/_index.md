+++
title = "Ambisonics Introduction"
outputs = ["Reveal"]
[reveal_hugo]
margin = 0.2
+++

# Listen: where is the sound?

Two B-format recordings by John Leonard:

- [A couple of Chinook helicopters](https://raw.githubusercontent.com/ambisonictoolkit/atk-sounds/master/b-format/Leonard-Chinook.wav)
- [Fireworks](https://raw.githubusercontent.com/ambisonictoolkit/atk-sounds/master/b-format/Leonard-Fireworks.wav)

- Sketch the sound's location and any movement.
- Compare your sketch with a neighbor.
- Compare the sustained helicopter sound with the brief fireworks events.

Which directions felt clear? Where were you uncertain?

{{% note %}}
Timing: 0–6 minutes elapsed (6 minutes).
Before class: download the excerpt and audition it through a B-format decoder configured for the room's actual seven main loudspeaker positions and output routing. Confirm the source convention against the decoder. The four source channels are not speaker feeds. Use the room's established bass management for the subwoofer; do not send an ambisonic component directly to LFE. Prepare playback before students arrive, without turning this opening into a routing tutorial. A horizontal 7.1 array does not reproduce the recording's full height information.
The official ATK catalogue identifies this as a B-format recording. The current WAV URL returned HTTP 200 on September 23, 2026; the old jlc2.amb link returned 404. Room playback still needs an audition.
Prepare both excerpts through the same room decoder. The Fireworks WAV URL also returned HTTP 200 on September 23, 2026. Audition both before class and set a comfortable level for the fireworks transients.
Spend one minute setting the question, two minutes playing both short excerpts and making individual sketches, two minutes comparing sketches, and one minute collecting observations. Ask whether brief events or sustained sounds were easier to locate and what listeners heard between events. Differences between seats are useful observations, not wrong answers. Do not promise a particular trajectory before auditioning.
Then introduce the imagined bird in front and traffic behind as a simpler scene we can reason about throughout the lesson. These opening excerpts motivate the theory. Leave microphone comparisons to the recording lesson and file/decoder practice to the ATK lesson; choose other ATK excerpts there.
Credit and catalogue: https://www.ambisonictoolkit.net/download/recordings/
{{% /note %}}

---

### What you should be able to explain

- What ambisonic channels represent.
- Where encoding, transformation, and decoding belong.
- Why two four-channel files may need a format conversion.
- What changes when we change the playback system.

{{% note %}}
Timing: 6–7 minutes elapsed (1 minute).
This lesson establishes the concepts. The next lesson examines microphone arrays. The ATK lesson provides listening and routing practice in REAPER.
{{% /note %}}

---

### The production signal path

1. **Capture or encode** a sound field.
2. **Transform** the field, such as rotating it.
3. **Decode** it for headphones or a speaker layout.

Keep an ambisonic master so you can make different playback versions.

{{% note %}}
Timing: 7–10 minutes elapsed (3 minutes).
Return to the bird and traffic. Capture stores directional information, rotation changes the scene's orientation, and decoding produces signals for the listening system. ATK calls these stages author, image, and monitor. Save plugin names and routing instructions for the ATK lesson.
Source: https://www.ambisonictoolkit.net/documentation/workflow/
{{% /note %}}

---

### Why separate the field from the speakers?

- Developed in the 1970s by Gerzon, Craven, Fellgett, and others.
- Recordings store sound-field components.
- Decoders turn those components into playback channels.
- One ambisonic master can serve different listening systems.

{{% note %}}
Timing: 10–12 minutes elapsed (2 minutes).
Keep the history brief. Contrast a channel assigned to a speaker with a component used to calculate several speaker feeds. Flexibility does not mean every array produces equally good results.
Background: https://www.bbc.co.uk/rd/blog/2010-03-ambisonics-periphony-audio-sound
{{% /note %}}

---

### Two ways into the field

- An **ambisonic microphone** captures a scene, including its ambience.
- An **encoder** places a mono source at a chosen direction in the field.

We could record the whole environment or combine an ambience recording with a separately encoded bird call.

{{% note %}}
Timing: 12–15 minutes elapsed (3 minutes).
Ask which approach gives more control over the bird. A separate source allows independent control before joining the field. A captured scene preserves relationships and ambience at the microphone. Both approaches can be combined. Leave microphone models and array construction to the next lesson.
{{% /note %}}

---

### A-format: capsule signals

![](a-format.png)

Four raw signals from a tetrahedral microphone.

{{% note %}}
Timing: 15–17 minutes elapsed (2 minutes).
This diagram shows example capsule geometry, not a universal channel order. A-format depends on the microphone. Use its specified conversion, including calibration or filtering where required. The recording lesson examines arrays in detail.
Source: https://ambisonics.ch/learn/ambisonics-formats/
{{% /note %}}

---

### First-order B-format: field components

![](b-format.png)

W: omni. X: front/back. Y: left/right. Z: up/down.

{{% note %}}
Timing: 17–20 minutes elapsed (3 minutes).
These are field components, not four speaker feeds. The figure-eight lobes represent opposite polarities, not separate sources. Their weighted combination represents direction. Full-sphere first-order B-format has four channels; higher orders have more.
Source: https://ambisonics.ch/learn/ambisonics-formats/
{{% /note %}}

---

### Predict the components

Imagine one source directly in front of the microphone, at ear height.

- Moving front to back: which component reverses polarity?
- Moving above to below: which component changes?
- Compare predictions with a partner.

{{% note %}}
Timing: 20–24 minutes elapsed (4 minutes).
Use one minute for individual predictions, one minute for partner comparison, and two minutes to explain the answers with the diagram. For an ideal source on the front/back axis, X changes sign. W remains omnidirectional; Y and Z are zero for this ideal direction. Directly above versus directly below changes Z's sign. Real room reflections also contribute, so a recording need not have silent Y and Z channels.
{{% /note %}}

---

### A-format and B-format

| | A-format | First-order B-format |
| --- | --- | --- |
| Signals represent | Microphone capsules | Field components |
| Channels | Four for this array | Four for full-sphere FOA |
| Next step | Mic-specific conversion | Transform or decode |

Both have four channels. Their meanings differ.

{{% note %}}
Timing: 24–26 minutes elapsed (2 minutes).
Conversion combines capsule signals to derive field components. It is not compression. Skip matrix arithmetic here. A recorder may perform the conversion internally and save B-format directly.
Source: https://ambisonics.ch/learn/ambisonics-formats/
{{% /note %}}

---

### FuMa and AmbiX

Both can represent first-order B-format.

- **FuMa:** W, X, Y, Z channel order, with FuMa scaling.
- **AmbiX:** ACN order and SN3D scaling. At first order: W, Y, Z, X.

The file and processor must agree on order and scaling.

{{% note %}}
Timing: 26–29 minutes elapsed (3 minutes).
Neither convention is compression. Reordering alone is insufficient because relative channel levels also differ. Classic ATK FOA tools use FuMa; an AmbiX source needs conversion before those tools. Identify the file's convention before choosing a converter. Leave software setup to the ATK lesson.
Sources: https://ambisonics.ch/learn/ambisonics-formats/ and https://www.ambisonictoolkit.net/news/archive/
{{% /note %}}

---

### Rotating our scene

Rotate the whole field by a quarter turn.

- Where do the bird and traffic move?
- Does their separation change?
- Could this move only the bird?

{{% note %}}
Timing: 29–32 minutes elapsed (3 minutes).
Both directions rotate together and retain their relative separation. Independent control requires keeping the bird separate before combining it with the ambience. This distinguishes source placement from whole-field transformation without repeating the plugin demonstration.
Source: https://www.ambisonictoolkit.net/documentation/workflow/
{{% /note %}}

---

### Decoding for the listener

- A **binaural decoder** produces headphone signals.
- A **loudspeaker decoder** produces feeds for a specified array.

What happens to height reproduction if all the speakers are at ear level?

{{% note %}}
Timing: 32–35 minutes elapsed (3 minutes).
A horizontal array cannot reproduce the full vertical field. Binaural rendering uses directional hearing cues, with results that vary across listeners and methods. The master may retain height when a playback version cannot reproduce it. Speaker placement and listener position still matter. Avoid promising identical localization on every system.
Source: https://ambisonics.ch/learn/ambisonics-formats/
{{% /note %}}

---

### Higher order: more spatial detail

![](Spherical_Harmonics_deg3.png)

Full-sphere channels: first order 4, second order 9, third order 16.

{{% note %}}
Timing: 35–37 minutes elapsed (2 minutes).
Identify the omni component, first-order figure-eights, and additional components. Higher order can improve resolution and enlarge the useful listening region, with more channels and processing. Extra output speakers or empty channels cannot recover higher-order information absent from a first-order recording. The next lesson introduces recording systems.
Source: https://ambisonics.ch/learn/ambisonics-formats/
{{% /note %}}

---

### Ambience and individual sounds

- A recorded field can provide surrounding ambience.
- A separate bird source can move independently.

Which approach would you choose for a player-controlled vehicle, and why?

{{% note %}}
Timing: 37–39 minutes elapsed (2 minutes).
Listen for the need to control a source as the game changes. An ambience field and individually positioned sources can coexist. A sound-field recording alone does not provide arbitrary listener translation or independent control of everything captured.
{{% /note %}}

---

### Find the problems

This workflow contains deliberate mistakes. What would you change?

1. Combine a raw mono bird call with four-channel AmbiX ambience.
2. Decode the result to binaural stereo.
3. Put a FuMa field-rotation processor after the decoder.
4. Save only the binaural stereo file, then try to use it to create a 7.1 mix.

With a partner, identify what needs changing and explain why.

{{% note %}}
Timing: 39–44 minutes elapsed (5 minutes).
Give pairs two minutes to mark problems, then use three minutes to build a corrected sequence together. The mono source needs encoding before combining with the field. The AmbiX source must be converted if subsequent processors expect FuMa. Field rotation belongs before decoding, and an ambisonic master should be retained for later speaker rendering. Ask students to name the representation at each stage, not just memorize plugin order.
If pairs finish early: would swapping the four AmbiX channels into WXYZ order complete the conversion? No: normalization must also match. Ask what would change if the goal were to rotate only the bird.
{{% /note %}}

---

### Check the signal path

Available sources and processors:

- Mono bird call and AmbiX ambience.
- FuMa field-rotation processor.
- Binaural decoder expecting FuMa.

Sketch the combined path for headphones. Mark the format conversion and where to save a master for speaker playback.

{{% note %}}
Timing: 44–49 minutes elapsed (5 minutes).
Use two minutes for individual sketches, one minute for partner comparison, and two minutes to explain and correct the path. Have students revise their own sketch after the discussion. Expected path: encode mono to FuMa FOA; convert AmbiX ambience to FuMa; combine four-channel signals; rotate the field; decode to binaural. Save the mix before decoding. Rotating only the bird changes the requested behavior. Sending raw mono into the rotation processor skips encoding.
{{% /note %}}

---

### Next lessons

- [Ambisonics recording](/lectures/week-5/ambisonics-recording/): arrays, recorder choices, and listening examples.
- [ATK in REAPER](/lectures/week-5/atk-setup/): auditioning files, routing, and rendering.

{{% note %}}
Timing: 49–50 minutes elapsed (1 minute).
Use the exit sketches to identify what needs a brief recap before practical work. UHJ distribution and detailed A-to-B equations are optional follow-up topics.
Further reading: https://www.ambisonictoolkit.net/documentation/workflow/ and https://ambisonics.ch/learn/ambisonics-formats/
{{% /note %}}
