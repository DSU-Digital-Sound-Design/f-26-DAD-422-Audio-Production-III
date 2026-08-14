---
title: "Speaker Layouts and Room Calibration"
summary: "Where the eight speakers belong, and how to set every channel to a known level before trusting the room."
tags: [calibration, 7.1, monitoring, bass management]
---

You have mixed in the immersive room all semester without asking whether it
tells the truth. Calibration is how a room earns trust: every speaker at a
known position, every channel at a known level, so a balance decision made
here still holds somewhere else. It is also a skill studios expect someone on
staff to have.

## The layout

Surround layouts descend from ITU-R BS.775, which places speakers on a circle
around the listening position, equidistant and at ear height. For 7.1, the
angles from center are:

{{< stats >}}
{{< stat value="0°" label="Center" note="With left and right at ±30°, the same front triangle as stereo." >}}
{{< stat value="±90° to 110°" label="Side surrounds" note="Beside the listening position or slightly behind it." >}}
{{< stat value="±135° to 150°" label="Rear surrounds" note="Behind the listener, mirrored left and right." >}}
{{< /stats >}}

Equidistance matters as much as the angles. A closer speaker is a louder and
earlier speaker, which drags the image toward it. When a speaker cannot be
moved to the circle, its level and delay compensate; that is part of what
calibration is for.

## Level calibration

The procedure is the same in every studio in the world:

1. Generate pink noise at **-20 dBFS RMS** and send it to one channel at a
   time. REAPER's tone generator (`Insert > Media item > Tone`) or a signal
   generator plugin works.
2. Put an SPL meter at the mix position, ear height, set to **C-weighted,
   slow**. The NIOSH Sound Level Meter app from DAD 222 does this fine.
3. Trim that channel's output until the meter reads the target, then repeat
   for each of the eight channels without touching the noise level.

{{< stats >}}
{{< stat value="79–82 dB SPL(C)" label="Per channel, small room" note="Every full-range channel reads the same number. Dub stages calibrate at 85; small rooms run lower. Pick one number and keep it." >}}
{{< stat value="+10 dB in-band" label="The LFE channel" note="The LFE is calibrated 10 dB hotter than a main channel within its own passband. A wideband meter will not read +10; band-limited measurement or an RTA shows it." >}}
{{< /stats >}}

Once calibrated, the monitor level control has a meaning: reference. Mark it.
Mixes made at reference translate; the level you have been using until now was
whatever the last person left.

## Bass management

The subwoofer plays two different things, and confusing them is the classic
mistake. The **LFE channel** is content a mixer deliberately routed to the .1.
**Bass management** additionally redirects the low end of the other channels,
typically below an 80 Hz crossover, into the subwoofer because small surround
speakers cannot reproduce it. The sub is a delivery device; the LFE is a
channel. A mix should never rely on bass management to carry material that
belongs in the mains.

## Reference level and your ears

The calibrated reference sits near the 85 dB exposure limit from the hearing
health material in DAD 222. Reference level is for balance judgments and QC
passes, not for hours of editing. Work lower, check at reference, and give
your ears the same calibration discipline you give the room: a known level,
deliberately chosen.

{{< drill label="Lab: calibrate the immersive room" >}}
Work as one group with a shared log.

1. Measure the distance from the mix position to each of the eight speakers,
   and sketch the layout with angles. Note where the room deviates from the
   circle.
2. Send -20 dBFS pink noise to each channel in turn. Log the SPL(C) reading
   at the mix position before touching anything: that is the room as you found
   it.
3. Trim every full-range channel to the same target in the 79 to 82 dB range.
   Log the trims.
4. Check the LFE with band-limited noise or an RTA.
5. Play a 7.1 mix you know, before and after, and describe what moved.
{{< /drill >}}

## Reference

- [ITU-R BS.775-3](https://www.itu.int/dms_pubrec/itu-r/rec/bs/R-REC-BS.775-3-201208-S!!PDF-E.pdf), the multichannel layout recommendation
- [Surround speaker placement angles](https://theatercalc.com/guides/surround-sound-speaker-placement), a practical summary of 5.1 and 7.1 positions
