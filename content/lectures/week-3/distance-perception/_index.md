+++
title = "Distance Perception in Mono"
outputs = ["Reveal"]
[reveal_hugo]
margin = 0.2
+++

## Distance perception in mono

Make a sound seem to approach, pass, and recede without stereo panning.

- Identify the cues that suggest distance.
- Use automation to coordinate those cues in your Mono Sound Walk.

{{% note %}}
- Begin with a familiar scene: someone speaking while walking away down a hallway.
- Today's sequence is listening to individual cues, then building a moving sound in REAPER.
{{%/ note %}}

---

## Cues to distance

- **Level:** a source usually gets quieter as it moves away.
- **Brightness:** high-frequency loss can make it seem more distant.
- **Direct-to-reverberant balance:** reflections become more prominent relative to direct sound in a room.

{{% note %}}
- These are clues interpreted together with knowledge of the source and setting. A quiet source nearby can resemble a louder source farther away.
- Introduce direct sound as the sound arriving straight from the source, and reverberant sound as the room's reflections. We will compare their balance after exploring level and filtering.
- Avoid treating perceived distance as an exact metre reading.
{{%/ note %}}

---

## Level and distance

For a point source in a free field, doubling distance reduces sound pressure level by about 6 dB.

| Distance | Example level |
| --- | --- |
| 1 m | 70 dB SPL |
| 2 m | 64 dB SPL |
| 4 m | 58 dB SPL |
| 8 m | 52 dB SPL |

Predict the level at 16 m.

[Distance calculator](https://sengpielaudio.com/calculator-distance.htm)

{{% note %}}
- Answer: approximately 46 dB SPL. Use the calculator only if students need another example.
- This assumes unchanged source output and free-field propagation. Room reflections and extended sources can change the falloff.
- These are example acoustic levels, not REAPER fader readings. A relative fader reduction of 6 dB can model one doubling under these assumptions.
{{%/ note %}}

---

## Brightness and filtering

- Air absorption can reduce high frequencies over distance.
- A low-pass filter lets you imitate reduced brightness.
- A duller sound can also suggest an obstacle or a different source.

{{% note %}}
- Introduce cutoff frequency before opening the interactive demo: lowering the cutoff removes more high-frequency content.
- Use filtering as a sound-design choice guided by the scene. Small changes in distance do not always produce an obvious loss of brightness.
- Keep source and playback level fixed when comparing filter settings.
{{%/ note %}}

---

{{< slide class="compact" >}}

## Distance, loudness, and filtering

[Open the interactive spatial audio demo](https://ohylli.github.io/spatial-audio-demo/)

- **Distance only:** enable distance/loudness. Move toward and away from the target. Which sounds closer?
- **Filtering only:** disable distance/loudness and enable low-pass. Does a duller sound suggest distance or obstruction?
- **Both cues:** enable distance/loudness and low-pass. Do the cues agree about how far away the sound seems?

Move with the arrow keys or WASD. Keep panning, ITD, and pulse rate off.

{{% note %}}
- Click Start audio, then click the World area to use the movement keys.
- For distance only, turn off low-pass, panning, ITD, and pulse rate. Enable distance/loudness. Move toward and away from the target and observe the distance and gain readouts.
- Have students close their eyes while you choose two positions. Play at each position and ask which seems closer, then reveal the positions. Keep the computer's playback volume fixed.
- For filtering only, disable distance/loudness and enable low-pass. Watch the cutoff readout as you move vertically. Ask whether brightness alone changes apparent distance.
- This demo maps filtering to vertical position. It is a designed spatial cue, not a calibrated simulation of air absorption over metres.
- Ask students to describe the impression before explaining it. Reduced brightness can suggest distance or obstruction, depending on context.
- Finally enable both distance/loudness and low-pass. Because they follow different position rules, the cues can reinforce or conflict with one another. Ask which cue students rely on when they disagree.
- Source: [Spatial Audio Accessibility Demo](https://ohylli.github.io/spatial-audio-demo/). Allow about four minutes.
{{%/ note %}}

---

{{< slide class="stepped" >}}

## Direct-to-reverberant ratio

DRR compares direct sound with the room's reflected sound.

- Higher DRR often suggests a closer source.
- Lower DRR often suggests a more distant source.
- Judge the balance in the context of the room.

[Larsen et al.: Discrimination of direct-to-reverberant ratio](https://pmc.ncbi.nlm.nih.gov/articles/PMC2677334/)

{{% note %}}
- In a typical reverberant room, direct energy falls with distance while the reverberant field can remain comparatively steady. The balance changes without needing a longer reverb tail.
- Explain the ratio before the violin exercise. Ask whether a stronger direct component changes perceived closeness, then collect observations.
{{%/ note %}}

---

{{< slide class="compact" >}}

## Which violin sounds closer?

Compare **A1 with B1**, then **A2 with B2**. Vote: A closer, B closer, or no difference. What sound cue led you to that choice?

| A | B |
| --- | --- |
| A1 <audio controls preload="none" src="https://www.akutek.info/wav/A1.wav" aria-label="Play violin A1"></audio> | B1 <audio controls preload="none" src="https://www.akutek.info/wav/B1.wav" aria-label="Play violin B1"></audio> |
| A2 <audio controls preload="none" src="https://www.akutek.info/wav/A2.wav" aria-label="Play violin A2"></audio> | B2 <audio controls preload="none" src="https://www.akutek.info/wav/B2.wav" aria-label="Play violin B2"></audio> |

[Source: akuTEK, Intimacy—monaural](https://www.akutek.info/demo_files/intimacy_monaural.htm)

{{% note %}}
- Play one ten-second example at a time, keeping the playback volume fixed. Collect votes before explaining the processing.
- These are judgments of perceived closeness. The files do not represent known near, mid, and far distances, so do not ask for estimates in metres or score a subjective response as wrong.
- First compare A1 with B1, then A2 with B2. In each pair, B has a 6 dB higher direct-to-reverberant ratio than A. The reverberant tail has the same content and level across all four files. A stronger direct component is a cue that can suggest a closer source. Ask whether students heard that effect.
- Then compare A1 with A2, or B1 with B2. The direct-to-reverberant ratio stays the same within each letter pair. Example 1 has a 33 ms gap before the reverb begins; example 2 has no gap. Ask whether this changes perceived closeness or just the character of the room.
- The clips isolate direct-to-reverberant balance and reflection timing. They are not a demonstration of high-frequency roll-off with distance.
- Source and processing details: [akuTEK, Intimacy—monaural](https://www.akutek.info/demo_files/intimacy_monaural.htm). Audio streams from akuTEK and requires an internet connection.
{{%/ note %}}

---

{{< slide class="compact" >}}

## Convolution reverb for believable rooms

An impulse response captures how a space or reverb system responds to a brief input.

- Load an IR into **ReaVerb** to establish the environment.
- Keep that room consistent while changing the direct/reverb balance.
- Use level and filtering to support the source's movement.

[OpenAIR: measured spaces](https://www.openair.hosted.york.ac.uk/) · [Samplicity M7: reverb-unit IRs](https://samplicity.com/bricasti-m7-impulse-response-files/)

{{% note %}}
- Demonstrate loading one suitable IR. OpenAIR provides measured acoustic spaces; the M7 collection samples a digital reverb unit.
- Reverb decay describes the environment. Avoid switching from a short room to a long hall merely to make the same source move away within one room.
- Pre-delay controls the gap before reverb begins. Recall the violin comparison: changing that gap can change the impression, but it is not a universal distance dial.
- Keep the output mono for this assignment, including any stereo reverb output.
{{%/ note %}}

---

{{< slide class="compact" >}}

## Editing automation in REAPER

Make one mono sound approach, pass, and recede.

* Select the track and press **V** to show its volume envelope.
* Draw a quiet–loud–quiet fade. **Ctrl/Cmd-drag** in the lane draws freehand.
* **Alt/Option-drag a segment** to reshape the transition. Listen for believable movement.
* Adjust an FX control, then run **FX: Show/hide track envelope for last touched FX parameter** to automate it.

Resources:

* [Kenny Gioia: Automation Basics (YouTube)](https://www.youtube.com/watch?v=IBPIjLLnDhk)
* [Reapertips: Automation editing shortcuts](https://www.reapertips.com/post/10-automation-shortcuts-in-reaper)

{{% note %}}
- Demonstrate editing an envelope before the next slide's live fader recording. Keep the source mono and panning centered.
- Start quietly, rise to a peak at the closest point, then fall away. Let students compare a steady ramp with a curved transition and describe the implied motion.
- Curve names describe how parameter values change over time. A shape alone does not establish approach or departure; the direction of the change and the parameter matter.
- For precise point editing, Ctrl/Cmd-double-click a point. Alt/Option-click removes a point. Mouse modifiers can differ in customized REAPER setups.
- For an FX envelope, adjust the desired control first, open the Actions list with ?, and search for the action shown on the slide. The article author's L shortcut is a personal assignment, not a default.
- The combined practice will extend this volume envelope to the filter and room balance introduced earlier.
- Optional extension: Alt/Option-drag along the bottom of an envelope lane to create an automation item. Reuse a movement pattern by copying or stretching it.
- Source: [Reapertips: 10+ Automation Shortcuts in REAPER](https://www.reapertips.com/post/10-automation-shortcuts-in-reaper).
{{%/ note %}}

---

## Recording automation live

- **Touch:** write while moving a control, then return to the existing envelope.
- **Latch:** keep writing the last value after releasing the control, until playback stops.
- **Write:** overwrite armed envelopes throughout playback.

{{% note %}}
- This is an alternative to drawing points. Use one short volume pass to compare Touch with Latch.
- Arm only the intended envelope. Demonstrate Write on a disposable pass, then undo it.
- Return to Trim/Read after recording so playback does not keep rewriting automation.
{{%/ note %}}

---

## Practice: one sound moving through a room

Use the same mono clip and room throughout.

1. A volunteer draws or records its approach and departure.
2. Another adjusts filter cutoff to support the movement.
3. A third adjusts the direct/reverb balance.

Listen without the screen. Where does the sound seem closest?

{{% note %}}
- This replaces separate volunteer title slides. Each volunteer adds one layer to the same example.
- After each addition, bypass that layer and ask what it contributes. Coordinate the closest point across the envelopes.
- Encourage subtle changes and a consistent environment. The exercise applies the earlier listening observations rather than repeating their explanations.
{{%/ note %}}

---

## Echoes and reflection timing

- A delay can represent a distinct reflection from a surface.
- Delay time describes the extra travel path of that reflection.
- Feedback adds repeats; their level and brightness affect the impression.

Optional: add one quiet, filtered echo to the moving sound.

{{% note %}}
- Combine the former delay overview and settings slides into this optional extension.
- There is no fixed mapping from a delay setting to the source's distance. A nearby source can produce a late echo from a distant wall.
- Begin with low wet level and little or no feedback. Ask students what reflecting surface the echo suggests.
- Skip the extension if the chosen scene does not call for a distinct echo.
{{%/ note %}}

---

## Doppler and moving sources

Relative motion can shift the pitch we hear.

- Approaching sources can sound higher in pitch.
- Receding sources can sound lower in pitch.
- Use the effect when the source's speed makes it relevant.

Optional: compare the pass-by with and without a pitch shift.

{{% note %}}
- Introduce Doppler as an additional motion cue after students have built movement through level, filtering, and room balance.
- Ask a volunteer to add a restrained pitch change to a fast-moving source, such as a vehicle.
- A manually drawn pitch envelope is a stylized approximation. Avoid a dramatic pitch dive for an ordinary walking source.
{{%/ note %}}
