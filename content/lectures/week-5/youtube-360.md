---
title: "Publishing Ambisonics: 360 Video for YouTube"
summary: "How to prepare an ATK mix for head-tracked playback with a 360-degree YouTube video."
tags: [ambisonics, 360 video, delivery, YouTube]
---

YouTube can render first-order Ambisonics with a 360-degree or VR video. As
the viewer changes direction, the platform rotates the sound field to match
the view. This gives you a practical way to publish an ambisonic mix and share
it with a link.

## Supported audio formats

YouTube accepts two first-order Ambisonics formats. Both use AmbiX with ACN
channel order, SN3D normalization, a 48 kHz sample rate, and one audio track in
the uploaded video file.

{{< stats >}}
{{< stat value="4 channels" label="AmbiX FOA" note="Use the channel order W, Y, Z, X. All four channels rotate with the 360-degree view." >}}
{{< stat value="6 channels" label="FOA with head-locked stereo" note="Use the channel order W, Y, Z, X, L, R. The final stereo pair stays fixed to the listener." >}}
{{< /stats >}}

The six-channel format does not contain a separate stereo audio track. It is
one multichannel track with the Ambisonics channels first and the head-locked
left and right channels last.

## World-locked and head-locked sound

World-locked sound turns with the scene. If a bird is behind the viewer, it
stays in that part of the scene when the viewer looks elsewhere. Most
diegetic sound belongs in the Ambisonics channels.

Head-locked sound does not move when the viewer turns. Narration and
non-diegetic music often work better this way. To use head-locked audio,
deliver the six-channel format and route the stereo signal to channels 5 and
6. If you deliver four channels, every sound in the mix rotates with the
scene.

## Convert ATK output to AmbiX

ATK processes first-order Ambisonics in FuMa B-format, while YouTube expects
AmbiX. The formats use different channel orders and normalization. Uploading
FuMa without conversion will distort the level and direction of the sound
field.

Place ATK's `BtoAmbiX` plug-in last in the four-channel Ambisonics path. Choose
the S3DN option for YouTube's SN3D normalization. For a four-channel delivery,
render channels 1 through 4 as W, Y, Z, X. For a six-channel delivery, route
the head-locked stereo mix to channels 5 and 6 before rendering W, Y, Z, X, L,
R.

## Prepare and upload the video

1. Finish the ATK mix while monitoring through the room decoder or a binaural
   decoder.
2. Add `BtoAmbiX` as the final process in the Ambisonics path and select S3DN.
3. Render one 48 kHz multichannel WAV. Use four channels for AmbiX alone or
   six channels when the project includes head-locked stereo.
4. Replace the video's temporary audio with the multichannel file. For this
   lab, use PCM audio in a MOV container. YouTube also accepts four-channel
   AAC in MP4 or MOV and four- or six-channel Opus in MP4, subject to its
   bitrate and channel-mapping requirements.
5. Run Google's [Spatial Media Metadata
   Injector](https://github.com/google/spatial-media/releases) on the finished
   video. Select `My video is spherical (360)` and
   `My video has spatial audio`. The tool identifies head-locked stereo from
   the six-channel audio layout.
6. Upload the result as unlisted and wait for YouTube to finish processing it.

Check the uploaded version with headphones, in Chrome on the desktop or in
the YouTube mobile app. Other browsers play a stereo downmix and will make
correct metadata look broken. Drag the view to the right. A world-locked
source should appear to move left relative to your head, while a head-locked
source should stay in place. If the picture moves but the sound
field does not, check the metadata. If directions are wrong, check the AmbiX
conversion and channel order.

## Listening list

You will not be able to record ambisonics of the scene in the video. That is
the normal condition for this work. The pieces below built their sound fields
entirely in post, from library material, foley, and synthesis, encoded to FOA
and placed against the picture.

Play these in Chrome on the desktop or in the YouTube mobile app. Other
browsers fall back to a stereo downmix without telling you.

### Designed fields

- [Pearl](https://www.youtube.com/watch?v=WqCH4DNQBUA). Google Spotlight
  Stories, 2016. An Emmy winner and the first VR film nominated for an Oscar.
  Nearly all of it happens inside one car, so the world-locked field is easy to
  follow as the view turns.
- [Sonaria](https://www.youtube.com/watch?v=LQhfXrl9kUQ). Directed by Scot
  Stafford, Google's creative director for audio. Built with UC San Diego's
  Sonic Arts department to get sources above and below the listener.
- [Behind the scenes: Sonaria](https://www.youtube.com/watch?v=Z6wXsIDGYo0).
  The team walks through the choice between head-locked stereo and the
  ambisonic channels. That is the same decision you make in the lab below.
- [Behind the scenes: Pearl](https://www.youtube.com/watch?v=7fN0bZhks5Y).

### Test material

Less interesting to listen to, more useful for calibrating what you are
listening for.

- [Ambisonic audio test](https://www.youtube.com/watch?v=vUtEW6OTQLw). One
  source, one rotation. Use it to confirm your playback chain works before you
  check your own upload.
- [Ambisonic audio test with 360 visualization](https://www.youtube.com/watch?v=yoVbl-QPe9Q).
  Draws the field on screen while it plays.
- [YouTube spatial audio test demo](https://www.youtube.com/watch?v=IURc99o8vQo).
  Tones at twelve azimuth angles.
- [Wizard Battle 360 audio test](https://www.vrtonung.de/en/portfolio/wizard-battle-360-sound-test-3d-videoaudio/).
  A fully invented field in third-order ambisonics.

{{< drill label="Lab: publish one minute of ambisonics" >}}
Use a 360-degree video provided in class and material from your ambisonics
project.

1. Place at least three sources against the picture. Include one stationary
   source, one moving source, and an ambience bed.
2. Add `BtoAmbiX`, select S3DN, and render a four-channel 48 kHz WAV. If the
   project uses head-locked narration or music, render six channels instead.
3. Mux the audio with the video, inject the required metadata, and upload the
   result as unlisted.
4. Check the published video with headphones. Confirm that the world-locked
   field follows the scene and that any head-locked audio stays with the
   listener.
5. Exchange links with another student and check each other's uploads before
   the end of class.
{{< /drill >}}

## References

- [YouTube: Use Spatial Audio in 360-Degree and VR Videos](https://support.google.com/youtube/answer/6395969)
- [Google Spatial Media Metadata Tools](https://github.com/google/spatial-media)
- [Spatial Media Metadata Injector Releases](https://github.com/google/spatial-media/releases)
- [ATK for REAPER: FuMa and AmbiX Conversion](https://www.ambisonictoolkit.net/publications/2016/07/24/atk-reaper-1.0.0b9.html)
