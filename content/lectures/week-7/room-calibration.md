---
title: "Speaker Layouts and Room Calibration"
summary: "Where the speakers belong and how to align each channel to a known monitoring level."
tags: [calibration, 7.1, monitoring, bass management]
---

A surround mix is only as reliable as the room where you make it. Speaker
placement, level, delay, and frequency response all affect what you hear at
the mix position. Calibration gives you a repeatable reference for judging
balance and checking whether a mix will translate to another system.

## The 7.1 layout

ITU-R BS.775 defines the basic front and surround geometry for multichannel
sound. A 7.1 system extends that arrangement by dividing the surrounds into
side and rear pairs. Use these horizontal angles as a practical starting
point:

{{< stats >}}
{{< stat value="0°" label="Center" note="Place left and right at ±30° to form the same front triangle used for stereo." >}}
{{< stat value="±90° to 110°" label="Side surrounds" note="Place them beside the listening position or slightly behind it." >}}
{{< stat value="±135° to 150°" label="Rear surrounds" note="Place them behind the listener and mirror their angles left to right." >}}
{{< /stats >}}

Aim every speaker at the reference listening position. The ear-level speakers
should ideally have similar distances from that point. When the room prevents
an equidistant layout, compensate for the difference with output level and
delay. A nearby speaker that arrives early or plays louder can pull the image
toward it.

## Align the channel levels

Use the same test signal and measurement settings for every channel:

1. Send pink noise to one full-range channel at a time. Dolby's calibration
   guidance assumes its Renderer noise; with another generator, use
   approximately -20 dBFS RMS. In REAPER, you can use `JS: Pink Noise
   Generator`, but verify its output with an RMS meter before calibrating.
2. Place an SPL meter at the mix position and at seated ear height. Set it to
   C weighting and Slow response. The NIOSH Sound Level Meter app supports
   both settings, although a calibrated measurement microphone is more
   accurate.
3. Adjust the channel's monitor trim until the meter reaches the chosen
   reference level. Repeat for all seven full-range channels without changing
   the test signal.

{{< stats >}}
{{< stat value="79 to 82 dB SPL(C)" label="Small-room reference" note="Align every full-range channel to the same chosen level. Dolby recommends 85 dBC for commercial Atmos music rooms but allows 79 to 82 dBC for small, single-operator rooms." >}}
{{< stat value="+10 dB in-band" label="LFE alignment" note="Within the LFE passband, its acoustic output is 10 dB above a main channel. A broadband SPL reading will show a smaller difference, so verify this with band-limited measurement or an RTA." >}}
{{< /stats >}}

After alignment, mark the monitor controller's reference position. This mark
lets everyone return to the same playback level. It does not mean that every
task must be done at reference.

## LFE and bass management

The subwoofer may reproduce two different signal paths:

- The LFE channel contains material that the mixer sends to the `.1` channel.
- Bass management redirects low frequencies from speakers that cannot
  reproduce them. The crossover belongs to the monitoring system, not the
  mix.

Do not treat these paths as interchangeable. The main channels should contain
their intended low-frequency content whether or not the playback system uses
bass management. The LFE channel is an additional effects channel, not a
replacement for bass in the main speakers.

## Reference level and hearing safety

Room calibration and hearing-risk measurements use different weightings and
serve different purposes. We align monitor channels with C-weighted pink
noise. NIOSH expresses occupational noise exposure as an A-weighted average
over time, with a recommended limit of 85 dBA over an eight-hour workday.

Use reference level for short balance checks and QC passes. Work at a lower
level for routine editing, take breaks, and reduce listening time as the level
rises.

{{< drill label="Lab: calibrate the immersive room" >}}
Work as one group and keep a shared log.

1. Measure the distance from the mix position to each speaker. Sketch the 7.1
   layout, label the angles, and note any speaker that does not match the
   intended geometry.
2. Send approximately -20 dBFS RMS pink noise to each full-range channel in
   turn. Before adjusting anything, record the SPL(C) reading at the mix
   position.
3. Choose one reference level in the 79 to 82 dB SPL(C) range. Trim all seven
   full-range channels to that value and record each adjustment.
4. Check the LFE response with band-limited noise and an RTA. Confirm the
   required +10 dB in-band gain instead of expecting a 10 dB difference on a
   broadband SPL meter.
5. Play a familiar 7.1 mix before and after calibration. Describe any changes
   in image position, balance, and low-frequency response.
{{< /drill >}}

## References

- [ITU-R BS.775-4: Multichannel Stereophonic Sound](https://www.itu.int/rec/R-REC-BS.775-4-202212-I/en)
- [Dolby: Best Practices for Dolby Atmos Music Studios](https://professionalsupport.dolby.com/s/article/Dolby-Atmos-Music-Studio-Best-Practices?language=en_US)
- [Dolby: How to Design a Dolby Atmos Mix Room](https://professionalsupport.dolby.com/s/article/How-to-Design-a-Dolby-Atmos-Mix-Room?language=en_US)
- [NIOSH Sound Level Meter App](https://www.cdc.gov/niosh/noise/about/app.html)
- [NIOSH: Noise-Induced Hearing Loss](https://www.cdc.gov/niosh/noise/about/noise.html)
