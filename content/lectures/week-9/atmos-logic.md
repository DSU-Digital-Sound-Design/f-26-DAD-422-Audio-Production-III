---
title: "Dolby Atmos with Logic Pro"
summary: "A guided workshop: build a bed-and-object mix, automate a musical gesture, check monitoring, and verify an ADM test export."
---

## Today's workshop

Build a short Atmos mix from the class song. Keep a foundation in the bed, place one featured source as an object, and automate one movement that serves the music. Then compare playback and verify a short ADM export.

Use the multitrack chosen in class, such as [Aiguille Rouge from the Mixing Secrets library](https://cambridge-mt.com/ms/mtk/#BabeGrand). Start with three or four tracks and a 20–30 second passage so we can check the whole workflow before mixing the full song.

By the end, you should have a saved Logic session with its audio copied into the project, one working bed track, one automated object, and an ADM test that reopens correctly. This is practice for [Project 4: Atmos Mix](/projects/atmos/), with no separate graded submission.

### Plan for 50 minutes

| Time | Task |
| --- | --- |
| 0–5 | Recall the signal paths and choose a passage |
| 5–15 | Set up Logic and verify monitoring |
| 15–25 | Build the bed and add one object |
| 25–35 | Automate and compare one musical gesture |
| 35–42 | Compare speaker and headphone playback |
| 42–50 | Export, reopen, and explain the result |

Follow the first setup together. If you finish a checkpoint early, help a partner trace their routing before adding more tracks. If setup takes longer, keep the mix small and finish the export check during Friday's continuation.

## 1. Five-minute recap

Without looking back at the slides, explain these paths to a partner:

- **Bed track:** audio passes through a Surround Panner into the shared bed, then the renderer.
- **Object track:** separate audio and position metadata reach the renderer.

Either path can carry a stationary or moving sound. Our bed is **7.1.2**; our room monitoring is **7.1**. Those settings describe different parts of the workflow.

For a refresher, use [What is Dolby Atmos?](/lectures/week-8/what-is-dolby-atmos/). Today we will prove the paths work in a session.

## 2. Create the session and check monitoring

1. Create a Logic project and save it as `YourName_Atmos_Workshop`. Include the source audio in the project when saving.
2. In **File > Project Settings > Audio**, set the sample rate to **48 kHz**. Enable **Dolby Atmos** under Spatial Audio and choose **7.1.2** as the surround/bed format.
3. Import the selected tracks at their common start position. Preserve their alignment and label each track by source.
4. Find the **Dolby Atmos plug-in** on the surround master channel strip. Open its monitoring-format menu.
5. For the studio, select **7.1** and verify the interface output assignments with the instructor. For headphones, select a binaural monitoring option and the correct headphone output device.

A 7.1.4 monitoring choice needs the corresponding speaker system. Our 7.1 room cannot reproduce discrete overhead speaker outputs. Use headphones later to compare the impression of height.

### Output routing reference

![Logic output-routing menu](../output-routing.png)

![Additional Logic output-routing options](../output-routing-2.png)

Output menus depend on the connected interface. Use the actual studio channel map; do not copy output numbers from a screenshot.

In **Logic Pro > Settings > Audio > I/O Assignments > Output**, check which hardware output serves each speaker.

![Logic speaker output assignments](../io-assignments.png)

At the room's established reference settings, have the instructor play the channel check and confirm that each named channel reaches the intended speaker. Resolve swapped or missing channels before judging a mix. On laptops, confirm that both headphone channels work and that the selected preview is binaural.

**Checkpoint:** show a partner the bed format, monitoring format, and output device. Explain what would go wrong if the speaker assignments were swapped.

## 3. Build a foundation in the bed

1. Choose one or two foundation tracks, such as drums and bass. Start with these playing alone.
2. Use their **Surround Panners** and confirm that the output is **Surround**, feeding the bed.
3. Establish a clear front balance before spreading other elements around the room. Keep room for the featured source.
4. Solo one bed track and make a small placement change. Confirm that the audible position follows the panner, then return it to its intended position.

### Track format and plug-in components

Keep mono recordings mono and stereo recordings stereo unless you have a reason to change them. A stereo source contains a relationship between two channels that you may want to preserve.

![Logic mono and stereo channel-strip components](../mono-vs-stereo.png)

Plug-in menus offer components for different channel formats. Use a component compatible with the channel strip, then check that processing has not unexpectedly narrowed or changed the source.

![Logic surround-format options](../surround-format.png)

The surround format determines the bed panner's channel layout. It does not specify the physical speaker outputs used to monitor the renderer.

## 4. Add one object

1. Choose a featured instrument, vocal phrase, or effect. Say why independent placement would help it.
2. On that channel strip, click the **Output** slot and choose **3D Object Panner**. Alternatively, Control-click its Surround Panner and select **3D Object Panner**.
3. Confirm the output label changes to **Object**. Open the panner and choose a clear starting position.
4. Solo the source and check that it reaches the renderer. Then bring back the foundation and rebalance.

A mono or stereo track can be an object. If using a stereo object, compare a narrower and wider **Spread** setting before choosing one. Do not duplicate the source onto a second bed track for this exercise.

![Logic surround master and Atmos controls](../surround-mode.png)

**Checkpoint:** point to one Surround output and one Object output. Trace both paths aloud. An object bypasses the shared bed bus, so processing on that bus before the renderer does not automatically process the object.

## 5. Automate one musical gesture

Pick a moment in the passage where movement has a purpose: an entrance, transition, response, or phrase ending.

1. Listen with the object held in place. Describe what the music needs.
2. Show track automation with **A** and select the relevant 3D Object Panner position parameter from the automation menu. Draw a few points for one deliberate move. Add another position parameter only if the gesture needs it.
3. Use **Read** mode for playback. Replay from before the movement and confirm that both the panner and audible position change.
4. Compare with the stationary version at similar loudness. Keep the rest of the mix unchanged.

Tell a partner: “At ___, the source moves ___ because ___.” If you cannot connect the move to something in the music, simplify it or try another moment.

**Checkpoint:** replay the same passage twice. Your partner should identify where the move happens and say whether it supports the phrase or distracts from it. Revise one thing in response.

## 6. Compare monitoring

Use the same passage and automation for both checks.

- **Speakers:** listen through the verified 7.1 layout. Does the featured source remain clear against the foundation? Does the movement translate without height speakers?
- **Headphones:** switch to the Dolby binaural preview. Compare it with the Apple Renderer preview at a comfortable, similar listening level. Note one difference in placement, width, or balance.

Dolby's **Off, Near, Mid, and Far** binaural settings do not control Apple's headphone rendering. If trying these settings, keep the Dolby preview selected and change one source at a time. Off retains the source without the distance modeling; it does not mute it.

If headphones are unavailable today, record that the headphone check is pending and complete it Friday. A binaural signal played through room speakers does not substitute for this comparison.

**Checkpoint:** write one observation and one adjustment you made, or explain why you kept the mix unchanged. Identify which renderer and playback system you heard.

## 7. Export and reopen a test

1. Save the working project. Set a cycle range around the 20–30 second passage, including enough time for the ending to decay.
2. Choose **File > Export > Project as Spatial Audio**. Select **Selection** for the test range and choose **Dolby Atmos ADM BWF**.
3. Save as `YourName_Atmos_Test.wav`.
4. Choose **File > Import > Create Project from ADM BWF** and select the test file to create a separate verification project. Keep your original working project intact.
5. Check the passage length, bed, object, and movement. Listen for missing material or a cut-off ending. Save the verification project separately if you need to investigate a problem.

The ADM preserves bed audio, separate object audio, and metadata. A normal bounce records a selected listening format; switching the monitoring format does not change the ADM master export.

**Checkpoint:** demonstrate that the exported file reopens with the object and its movement, rather than only playing a flattened stereo or surround file. If something is missing, return to the working session and trace the source's routing before exporting again.

## Before you leave

Show the instructor or a partner:

- Your saved session with its source media included.
- One bed track and one object, with an explanation of the routing choice.
- One intentional automated movement and your monitoring observation.
- The reopened ADM test, or the specific issue to resolve Friday.

Next class, expand the song mix from this working session. Project 4 requires at least four automated object tracks and a finished mix; today's small test is a starting point. The [Atmos delivery lesson](/lectures/week-11/atmos-delivery/) covers the full loudness and delivery checks before submission.

## Troubleshooting

| Symptom | First check |
| --- | --- |
| No audio | Output device, track mute/solo, meters, and renderer monitoring format |
| Wrong speaker responds | Interface outputs and Logic I/O assignments against the room map |
| Supposed object still says Surround | Output slot and panner type |
| Movement does not replay | Correct automation parameter, points, and Read mode |
| Bed processing misses the object | Separate signal paths into the renderer |
| Headphone preview sounds different | Selected renderer, binaural settings, and comparison loudness |
| Export contains the wrong passage | Selection range and export choice |

## References

Menu wording can vary with the installed Logic version. Use the corresponding version of Apple's guide when a control differs from a screenshot.

- [Apple: bed tracks and object tracks](https://support.apple.com/en-au/guide/logicpro/lgcp73f9b9ac/mac)
- [Apple: monitoring formats and bounce versus export](https://support.apple.com/en-au/guide/logicpro/lgcp179f27c1/mac)
- [Apple: export an Atmos ADM master](https://support.apple.com/en-au/guide/logicpro/lgcp258ed132/mac)
- [Apple: create a project from an ADM master](https://support.apple.com/en-ie/guide/logicpro/lgcp306bc556/mac)
- [Apple: Dolby binaural render modes](https://support.apple.com/en-au/guide/logicpro/lgcp789f000d/mac)
