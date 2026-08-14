---
title: "Publishing Ambisonics: 360 Video for YouTube"
summary: "The delivery pipeline that turns a B-format mix into a head-tracked video anyone can watch on a phone."
tags: [ambisonics, 360 video, delivery, YouTube]
---

Everything you have mixed with the ATK so far has stayed in this room. YouTube
plays first-order ambisonics on 360 video with head tracking, which makes it
the one place you can publish an ambisonic mix and hand someone a link. The
viewer turns their phone, and your sound field turns with the picture.

## What YouTube accepts

{{< stats >}}
{{< stat value="AmbiX FOA" label="The audio format" note="Four channels in ACN order (W, Y, Z, X) with SN3D normalization, 48 kHz, as the video's only audio track." >}}
{{< stat value="Discontinued" label="Head-locked stereo" note="YouTube previously accepted four ambisonic channels plus a head-locked stereo pair. It now accepts plain four-channel ambiX only." >}}
{{< /stats >}}

The head-locked idea still matters as a design concept. Diegetic sound belongs
to the world and rotates as the viewer turns: the birds stay behind you when
you turn away from them. Head-locked sound sticks to the viewer's head:
narration or score that should not move. On YouTube's current pipeline there
is no separate head-locked track, so anything you include will rotate with the
world. Plan the mix accordingly: put narration at front center and accept that
it turns, or leave it out.

## FuMa to ambiX

The ATK works in FuMa B-format; YouTube requires ambiX. The two differ in
channel order and normalization, and a FuMa file uploaded as ambiX plays back
with the sound field scrambled. Convert at the end of the chain with the ATK's
FuMa to ambiX transform as the last insert on the master, after the mix and
before the render. Render a 4-channel WAV at 48 kHz.

## The pipeline

1. Mix in the ATK as usual, monitoring binaural or through the room decoder.
2. Add the FuMa to ambiX transform last, then render a 4-channel 48 kHz WAV.
3. Replace the 360 video's audio with your 4-channel file. REAPER can render
   video with the new audio track, or use ffmpeg.
4. Run Google's [Spatial Media Metadata
   Injector](https://github.com/google/spatial-media/releases) on the file and
   check both the 360 and spatial audio boxes. This writes the metadata that
   tells YouTube how to interpret the file.
5. Upload, wait for processing, then verify with headphones: drag the view
   around and confirm the sound field rotates opposite your drag. If the image
   moves and the sound does not, the metadata or channel order is wrong.

The verification step is the QC habit from the Atmos unit in another form:
delivery is not done until you have played back the published version.

{{< drill label="Lab: publish one minute of ambisonics" >}}
Use a 360 video clip provided in class and material from your ambisonics
project.

1. Spatialize at least three sources against the picture: something fixed in
   the world, something that moves, and an ambience bed.
2. Convert FuMa to ambiX, render 4 channels at 48 kHz, and mux it with the
   video.
3. Inject metadata, upload as unlisted, and verify with headphones that the
   field rotates correctly.
4. Trade links with another student and QC each other's uploads before the end
   of class.
{{< /drill >}}

## Reference

- [YouTube: use spatial audio in 360 and VR videos](https://support.google.com/youtube/answer/6395969), the current format requirements
- [Spatial Media Metadata Injector](https://github.com/google/spatial-media/releases)
- [VRTonung: YouTube ambisonics guide](https://www.vrtonung.de/en/youtube-ambisonics-the-spatial-audio-experience-for-vr-video-2/)
