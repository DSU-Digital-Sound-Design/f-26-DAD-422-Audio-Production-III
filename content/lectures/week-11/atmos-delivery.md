---
title: "Atmos Delivery: Loudness, the ADM Master, and Binaural QC"
summary: "How to prepare an Atmos mix for submission: meet the loudness target, export an ADM BWF, and check the renders listeners will hear."
tags: [atmos, loudness, delivery, ADM, binaural]
---

Atmos uses the same loudness measurement system you learned in DAD 322, but
the target and master format are different. You also need to check how the mix
translates to several playback formats before you submit it.

By the end of class, you should be able to measure the complete mix, correct
its level without changing the bed/object balance, and distinguish a playback
render from an ADM master. We'll demonstrate the workflow together using one
prepared session.

## Delivery levels

Use these course limits for both the music and film routes of [Project 4](/projects/atmos/). They are adapted from music delivery practice, not universal specifications for all film or Atmos content:

{{< stats >}}
{{< stat value="-18 LUFS-I" label="Maximum integrated loudness" note="Measure the complete song or supplied film from the 5.1 loudness re-render according to ITU-R BS.1770. Quieter is acceptable." >}}
{{< stat value="-1 dBTP" label="Maximum true peak" note="Measure true peak from the same 5.1 loudness re-render." >}}
{{< /stats >}}

LUFS and LKFS are numerically equivalent. Integrated loudness measures the
mix as a whole; true peak checks the highest reconstructed signal peak.
A mix can pass one limit and fail the other.

### Set up the surround master strip

Choose **5.1** as the Monitoring Format in the Dolby Atmos plug-in. On the
surround master channel strip, use this order from top to bottom:

**Dolby Atmos → Level Meter, set to True Peak → Loudness Meter**

Add the meters from **Audio FX > Metering**. Use their multichannel versions
so they measure the rendered bed and objects together. These readings apply
to the 5.1 render, not the room's 7.1 output or a binaural render.

1. Set the full mix's start and end, including the final decay. Turn cycle off.
2. Reset the Level Meter peak values and the Loudness Meter. Enable the
   Loudness Meter's **Start/Pause** analysis button.
3. Play the complete song or supplied film once without stopping. Read the **Integrated**
   value and the highest true-peak value across the channels.
4. Record both readings before starting another playback, which can reset
   the Level Meter's peak holds.

Do not judge the integrated result from a short loop or from the momentary
loudness display. We can use short excerpts for listening comparisons, but
the delivery measurement covers the complete song or supplied film.

### Correct the level in the source mix

If the mix measures -15 LUFS-I, reducing the complete mix by about 3 dB is a
starting point. Remeasure the full mix and check true peak as well.
Quieter than -18 LUFS-I is acceptable; do not raise a mix simply to hit the ceiling.

Adjust the bed and object source levels together while preserving their
relative balance. VCA groups for bed tracks and object tracks can help;
make sure returns and other contributing paths are accounted for without
attenuating a signal twice.

Processing before the Dolby Atmos plug-in affects the bed, not the separate
object signals. Processing after it affects the monitoring render and is
not included in the ADM export. Lowering the surround output fader or adding
a gain plug-in after the renderer is therefore not a fix for an over-level
ADM master. Use that distinction in the demonstration: predict which changes
will survive export.

Heavy limiting can reduce dynamics and alter the mix. First check source
levels and isolated peaks instead of using a limiter to force the result.

Keep the LFE channel for low-frequency effects rather than using it as a
bass-management channel. Apple also prohibits Atmos masters made by upmixing,
de-mixing, or adding spatial effects to a finished stereo master. Build the
Atmos mix from the multitracks or from stems created from those multitracks.

## Native surround plug-ins

A native surround plug-in supports a multichannel format directly. Multi-mono
processing instead uses separate plug-in instances for individual channels,
with controls that can be linked or adjusted separately. Check the format
available on the channel strip; not every plug-in supports every layout.

Useful examples in Logic include:

| Plug-in | Use |
|---|---|
| Multichannel Gain | Adjust individual surround-channel levels |
| Surround Compressor | Control dynamics across a surround signal; supports up to 7.1 |
| Space Designer | Create a surround reverberant space |
| Delay Designer | Create delay patterns across channels; supports up to 7.1 |
| Level Meter and Loudness Meter | Inspect channel peaks and overall loudness |

On the surround master, processing **before Dolby Atmos affects the bed**;
it does not include the separate objects. Processing **after Dolby Atmos
affects the selected monitoring render**, and is not part of the ADM master.
Process an individual object on its own channel strip before it reaches the renderer.

For Friday, compare a short bed passage with and without surround processing.
Open the plug-in's channel controls and identify which channels it affects.
Then solo an object and predict whether that bed processing will change it.
Listen to test the prediction. What changes in the spatial balance, and is
the processing helping?

See Apple's [native surround plug-in list](https://support.apple.com/guide/logicpro/lgcp337a1f65/mac)
and [multi-mono controls](https://support.apple.com/guide/logicpro/lgcp5aef9327/mac).

## The ADM BWF master

Deliver the Atmos mix as an ADM BWF. This single multichannel WAV file stores
the bed and object audio along with position, binaural, and downmix metadata.
Compatible Atmos tools and streaming services use that information to render
the mix for different playback systems.

In current versions of Logic, choose
`File > Export > Project as Spatial Audio`, then select
`Dolby Atmos ADM BWF`. Choose **Project** for the whole project or **Selection**
for the complete song or supplied film if it occupies only part of the session. Check the range includes the final decay. In older
versions, the command may be named **Project as ADM BWF**. The monitoring format selected in the Dolby Atmos
plug-in does not affect this export.

After exporting, choose **File > Import > Create Project from ADM BWF** and listen through the resulting verification project.
Confirm the beginning and end, object movement, automation, and overall
balance. If you find a problem, correct it in the source project and export a
new master.

Metering checks the source mix's levels. Reopening checks that the delivered
file contains the intended mix and range. Mix and meter first, then export
and verify the final file; you do not need to export after every level
adjustment. An ADM is not a normal stereo listening file or an editable copy
of your original Logic session, so keep the source project too.

For an Apple Music release, the Atmos master must match its stereo reference in length and sync. Use the same project version and start/end points for both. Project 4 requires the ADM master and QC record listed in its brief; it does not require a separate stereo master for release.

## Check the renders

Our studio monitors a 7.1 render of the Atmos mix; it has no discrete height speakers. Listeners may hear other renders. The Atmos
master may be rendered for headphones, stereo speakers, surround systems, or
a device with speaker virtualization. Check those versions as part of the
mixing process.

- Listen to the Dolby Renderer over headphones. Compare `Off`, `Near`,
  `Mid`, and `Far` on one featured object, then choose settings that suit the
  mix. `Off` disables distance modeling; it does not mute the sound. The LFE
  channel is fixed at `Off`. A default setting is fine if it sounds appropriate.
- Listen with Logic's Apple Renderer in Music mode. This previews the
  headphone virtualization used by Apple Music. The Apple Renderer controls
  affect monitoring only; they are not written to the ADM BWF.
  Dolby's binaural distance settings do not affect the Apple Renderer.
- Check the 5.1 and stereo re-renders. Listen for missing elements, level
  changes, masking, phase problems, and an unstable center image.
- Return to the room's verified 7.1 monitoring layout after making changes for
  another render. A correction for one format should not damage the main mix.

Use the same short passage for each comparison. Predict what may change,
listen, and name one audible difference. Headphone render comparisons need
headphones; playing them through the room speakers does not demonstrate
their intended spatial effect.

{{< drill label="Check your understanding" >}}
1. Why do we measure the 5.1 render rather than the headphone render?
2. A gain plug-in after Dolby Atmos makes the meters pass. Has it corrected
   the exported master? Explain the signal path.
3. The source mix sounds right, but the ADM cuts off its final decay. What
   needs to change?
{{< /drill >}}

Apply this workflow as you finish [Project 4](/projects/atmos/). Keep the
final meter readings, screenshot, listening observation, and ADM verification
result for the QC record described in the project brief.

## References

- [Dolby: Measuring the Loudness of a Dolby Atmos Mix](https://professionalsupport.dolby.com/s/article/Measuring-the-Loudness-of-a-Dolby-Atmos-Mix?language=en_US)
- [Dolby: How Do I QC My Dolby Atmos Mix?](https://professionalsupport.dolby.com/s/article/How-do-I-QC-my-Dolby-Atmos-mix)
- [Apple Music: Delivering Dolby Atmos Audio](https://itunespartner.apple.com/music/support/5216-delivering-dolby-atmos-audio)
- [Apple Logic Pro: Export a Spatial Audio Project to an ADM BWF](https://support.apple.com/guide/logicpro/export-a-spatial-audio-project-dolby-atmos-lgcp258ed132/mac)
- [Apple Logic Pro: Spatial Audio Monitoring Formats](https://support.apple.com/guide/logicpro/spatial-audio-monitoring-formats-lgcp179f27c1/mac)
- [Apple Logic Pro: Surround Master Plug-ins and Metering](https://support.apple.com/guide/logicpro/lgcp337a1f65/mac)
- [Apple Logic Pro: Level Meter](https://support.apple.com/guide/logicpro/lgcef24f3e79/mac)
- [Apple Logic Pro: Loudness Meter](https://support.apple.com/guide/logicpro/lgce12d9d256/mac)
- [Apple Logic Pro: Dolby Atmos Signal Flow](https://support.apple.com/guide/logicpro/lgcpc8111cb7/mac)
- [Apple Logic Pro: Binaural Render Modes](https://support.apple.com/guide/logicpro/lgcp789f000d/mac)
