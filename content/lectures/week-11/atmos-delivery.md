---
title: "Atmos Delivery: Loudness, the ADM Master, and Binaural QC"
summary: "How to prepare an Atmos mix for submission: meet the loudness target, export an ADM BWF, and check the renders listeners will hear."
tags: [atmos, loudness, delivery, ADM, binaural]
---

Atmos uses the same loudness measurement system you learned in DAD 322, but
the target and master format are different. You also need to check how the mix
translates to several playback formats before you submit it.

## Delivery levels

Use these course limits for both the music and film routes of [Project 4](/projects/atmos/). They are adapted from music delivery practice, not universal specifications for all film or Atmos content:

{{< stats >}}
{{< stat value="-18 LKFS" label="Maximum integrated loudness" note="Measure the full submitted passage from the 5.1 loudness re-render according to ITU-R BS.1770. Quieter is acceptable." >}}
{{< stat value="-1 dBTP" label="Maximum true peak" note="Measure true peak from the same 5.1 loudness re-render." >}}
{{< /stats >}}

These numbers apply to the 5.1 loudness re-render, not the room's 7.1 speaker output
or a binaural render. In Logic, choose 5.1 as the monitoring format in the
Dolby Atmos plug-in. Place a multichannel loudness meter after the plug-in,
reset the meter, and play the entire submitted passage without interruption.

If the mix measures -15 LKFS, lower the overall level. Heavy limiting may
raise loudness while reducing the dynamics and space that Atmos is meant to
preserve. It also provides no delivery advantage: a service may turn down a
master that exceeds its loudness limit.

Keep the LFE channel for low-frequency effects rather than using it as a
bass-management channel. Apple also prohibits Atmos masters made by upmixing,
de-mixing, or adding spatial effects to a finished stereo master. Build the
Atmos mix from the multitracks or from stems created from those multitracks.

## The ADM BWF master

Deliver the Atmos mix as an ADM BWF. This single multichannel WAV file stores
the bed and object audio along with position, binaural, and downmix metadata.
Compatible Atmos tools and streaming services use that information to render
the mix for different playback systems.

In current versions of Logic, choose
`File > Export > Project as Spatial Audio`, then select
`Dolby Atmos ADM BWF`. The monitoring format selected in the Dolby Atmos
plug-in does not affect this export.

After exporting, choose **File > Import > Create Project from ADM BWF** and listen through the resulting verification project.
Confirm the beginning and end, object movement, automation, and overall
balance. If you find a problem, correct it in the source project and export a
new master.

For an Apple Music release, the Atmos master must match its stereo reference in length and sync. Use the same project version and start/end points for both. Project 4 requires the ADM master and QC record listed in its brief; it does not require a separate stereo master for release.

## Check the renders

Our studio monitors a 7.1 render of the Atmos mix; it has no discrete height speakers. Listeners may hear other renders. The Atmos
master may be rendered for headphones, stereo speakers, surround systems, or
a device with speaker virtualization. Check those versions as part of the
mixing process.

- Listen to the Dolby Renderer over headphones. Set each bed channel and
  object to `Off`, `Near`, `Mid`, or `Far` deliberately rather than leaving
  the binaural render mode at its default.
- Listen with Logic's Apple Renderer in Music mode. This previews the
  headphone virtualization used by Apple Music. The Apple Renderer controls
  affect monitoring only; they are not written to the ADM BWF.
- Check the 5.1 and stereo re-renders. Listen for missing elements, level
  changes, masking, phase problems, and an unstable center image.
- Return to the room's verified 7.1 monitoring layout after making changes for
  another render. A correction for one format should not damage the main mix.

The goal is one mix that translates across all of these formats, meets the
delivery levels, and survives export and re-import without surprises.

{{< drill label="Lab: make Project 4 submission-ready" >}}
Bring your Atmos mix in progress.

1. Choose the 5.1 monitoring format and measure integrated loudness and true
   peak over the full submitted passage. Record both values.
2. Adjust the overall level until the mix is at or below -18 LKFS integrated
   and -1 dBTP. Do not use heavy limiting simply to reach -18 LKFS.
3. Monitor through the Dolby Renderer over headphones. Review the binaural
   render mode for every bed channel and object.
4. Monitor through the Apple Renderer in Music mode, then check the stereo
   re-render. Write down anything that disappears, shifts, or becomes masked.
5. Export an ADM BWF, create a new project from it, and compare it with the
   source project.
6. Record the final readings, monitoring formats, one timestamped listening
   observation and resulting decision, and the ADM verification result in your
   project QC record. Include a screenshot of the final meter readings.
{{< /drill >}}

## References

- [Dolby: Measuring the Loudness of a Dolby Atmos Mix](https://professionalsupport.dolby.com/s/article/Measuring-the-Loudness-of-a-Dolby-Atmos-Mix?language=en_US)
- [Dolby: How Do I QC My Dolby Atmos Mix?](https://professionalsupport.dolby.com/s/article/How-do-I-QC-my-Dolby-Atmos-mix)
- [Apple Music: Delivering Dolby Atmos Audio](https://itunespartner.apple.com/music/support/5216-delivering-dolby-atmos-audio)
- [Apple Logic Pro: Export a Spatial Audio Project to an ADM BWF](https://support.apple.com/guide/logicpro/export-a-spatial-audio-project-dolby-atmos-lgcp258ed132/mac)
- [Apple Logic Pro: Spatial Audio Monitoring Formats](https://support.apple.com/guide/logicpro/spatial-audio-monitoring-formats-lgcp179f27c1/mac)
