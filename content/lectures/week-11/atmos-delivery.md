---
title: "Atmos Delivery: Loudness, the ADM Master, and Binaural QC"
summary: "What makes an Atmos mix submission-ready: the loudness spec, the master file format, and checking the renders listeners actually hear."
tags: [atmos, loudness, delivery, ADM, binaural]
---

You know stereo loudness from DAD 322. Atmos delivery uses the same measurement
system with its own target, its own master format, and one extra QC problem:
your mix will be rendered several different ways after it leaves you, and you
are responsible for how all of them sound.

## The spec

Streaming services accept Atmos music against the Dolby delivery
specification:

{{< stats >}}
{{< stat value="-18 LKFS" label="Integrated loudness ceiling" note="Measured per ITU-R BS.1770 on a 5.1 render of the full mix, per track. Quieter is acceptable; louder is rejected." >}}
{{< stat value="-1 dBTP" label="True peak ceiling" note="Measured on the same render. The headroom protects the lossy encode." >}}
{{< /stats >}}

Two more rules from the same spec: no full-frequency content in the LFE
channel, and no Atmos masters upmixed from a stereo file. The mix must come
from multitracks, which is what you are doing anyway.

Note what the measurement is not: it is not the loudness of your 7.1.4
monitoring mix or the binaural render. The spec measures a 5.1 re-render. In
Logic, set the Dolby Atmos plugin's monitoring format to 5.1 and read an
integrated measurement on a loudness meter placed after the plugin, over the
full duration of the song. If you land at -15, pull the mix down; do not
limit your way to the number. The normalization logic is the same as stereo:
platforms level everything, so loud buys nothing.

## The master: ADM BWF

An Atmos mix is delivered as a single file, the ADM BWF: a broadcast WAV
carrying every bed and object plus their position metadata. It is the
interchange master; any Atmos renderer can open it and reproduce your mix,
which is what Apple, Amazon, and Tidal do on their side.

Logic exports it directly: `File > Export > Project as ADM BWF`. Verify the
export the same way you verify any render: make a new empty project, import
the ADM BWF, and confirm it plays back as your mix. A master you have not
re-opened is a master you have not checked.

Delivery services also require the Atmos master to be conformed to a stereo
deliverable of the same song: same length, same sync. Keep your stereo bounce
and your ADM export from the same project state.

## Binaural QC

Most people who play your Atmos mix will hear it on headphones, folded down by
a renderer you do not control. That makes the fold-downs part of your mix, not
an afterthought.

- Audition the **binaural render** in Logic (monitoring format: binaural), and
  set the per-track binaural distance modes (near, mid, far) deliberately.
  They are mix decisions.
- Know their limit: Apple Music renders spatial audio with Apple's own
  renderer, so the Dolby binaural settings you audition in Logic are not
  exactly what Apple listeners hear. Do not tune the mix to binaural quirks;
  make it work on speakers and confirm it survives headphones.
- Check the **stereo and 5.1 re-renders** the same way. If the mix falls apart
  in stereo, most listeners never hear what you made.

The QC pass, in one sentence: one mix, auditioned in 7.1.4, binaural, 5.1, and
stereo, measured on the 5.1 render, exported as ADM BWF, and re-imported to
prove it.

{{< drill label="Lab: make Project 4 submission-ready" >}}
Bring your Atmos mix in progress.

1. Set the Atmos plugin's monitoring format to 5.1 and measure integrated
   loudness and true peak over the whole song. Write both numbers down.
2. Bring the mix into spec: at or under -18 LKFS integrated and -1 dBTP, by
   level, not limiting.
3. Switch monitoring to binaural and listen through. Adjust any track whose
   near/mid/far setting was left at the default by accident.
4. Listen once in stereo. Note anything that vanished.
5. Export the ADM BWF, import it into an empty project, and confirm it plays
   back as your mix.
{{< /drill >}}

## Reference

- [Apple Music: delivering Dolby Atmos audio](https://itunespartner.apple.com/music/support/5216-delivering-dolby-atmos-audio)
- [Loudness in Dolby Atmos in Logic Pro](https://killandermusicrecords.com/en/guides/dolby-atmos/loudness-in-dolby-atmos-in-logic-pro-a-step-by-step-guide/), a step-by-step metering guide
- [Pros and cons of the integrated Atmos renderer in Logic](https://www.production-expert.com/production-expert-1/pros-and-cons-of-the-integrated-dolby-atmos-renderer-in-logic-pro)
