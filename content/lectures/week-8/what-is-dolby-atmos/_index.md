+++
title = "What is Dolby Atmos?"
outputs = ["Reveal"]
[reveal_hugo]
margin = 0.2
+++

# Why Atmos?

{{% note %}}
Atmos separates the mix from a fixed playback layout. Beds carry
channel-based audio, objects carry audio with position metadata, and a
renderer combines them for the available speakers or headphones.

This solves a practical problem. A 7.1 mix describes what each of eight
channels should play. An Atmos master describes the sound scene and gives the
renderer information it can adapt to different systems.

By the end of class, students should be able to explain beds and objects,
compare the two panners in Logic, describe the renderer's job, and identify an
appropriate master format for a delivery.
{{%/ note %}}

---

## From mono to immersive

* Mono: one channel
* Stereo: an image between two speakers
* Surround: speakers around the listener
* Immersive: surround with height

{{% note %}}
These categories describe different ways of representing and reproducing
space. They are not a quality ranking. A strong stereo mix can be more
effective than a weak immersive mix.

Atmos is one immersive-audio system. Other approaches include Ambisonics,
Auro-3D, MPEG-H Audio, IAMF, and Apple's newer ASAF and APAC workflow.
{{%/ note %}}

---

## Terms that get confused

* A channel is a signal; a speaker is a transducer
* Several speakers can reproduce the same mono channel
* Surround describes a playback layout
* Ambisonics represents a sound scene
* Atmos combines channel beds, objects, metadata, and rendering

{{% note %}}
A bed is a channel-based submix routed to a fixed layout, commonly 7.1.2.
An object is a mono or stereo signal whose position and movement are stored as
metadata. The renderer decides how to reproduce that position on the playback
system.
{{%/ note %}}

---

## What Atmos contains

* One or more channel-based beds
* Mono or stereo objects with position metadata
* Up to 128 input channels at 48 kHz
* Up to 118 object inputs
* A renderer for the target playback layout

<img src="https://blog.soundparticles.com/hs-fs/hubfs/channel-object-audio.png?width=1875&name=channel-object-audio.png" alt="Channel and object audio" style="display:block;margin:1.5rem auto 0;max-width:70%;height:auto;">

{{% note %}}
A standard 7.1.2 bed uses ten channels: seven ear-level channels, LFE, and a
pair of top-middle channels. The remaining renderer inputs can carry objects.
The exact number available depends on the bed configuration, but an Atmos
master cannot exceed 128 PCM channels or 118 objects.

Beds and objects serve different purposes. Beds are useful for material that
should remain distributed across a channel layout. Objects are useful when a
sound needs precise location, movement, size, or separate metadata.
{{%/ note %}}

---

<img src="object-tracks-and-bed-tracks-routing.png" alt="Object tracks and bed tracks routing" style="display:block;margin:1rem auto 0;max-width:80%;height:auto;">

{{% note %}}
This Apple diagram shows the two signal paths in Logic.

Bed tracks route to one shared surround bed. Logic can configure that bed as
5.1, 7.1, or 7.1.2. A 7.1.2 bed contains L, R, C, LFE, Ls, Rs, Lrs, Rrs,
Ltm, and Rtm. Because it has only one overhead pair, it cannot distinguish
front-height from rear-height positions.

Object tracks bypass the surround bed and connect to object inputs on the
Dolby Atmos plug-in. The 3D Object Panner sends the audio and its position
metadata to the corresponding input. Logic allows mono and stereo object
tracks, but not surround object tracks. A stereo object uses two object
inputs, and object tracks do not have an LFE send.

Logic exports the bed audio, object audio, automation, and supporting metadata
in an ADM BWF master.
{{%/ note %}}

---

## Two panners in Logic

<img src="bed-vs-object-logic.png" alt="Bed and object panners in Logic Pro" style="display:block;margin:1rem auto 0;max-width:80%;height:auto;">

{{% note %}}
The Surround Panner on the left routes a bed track among channels in the
selected surround format. Its controls refer to the speaker layout.

The 3D Object Panner on the right stores a speaker-independent position. It
controls left and right position, front and back position, elevation, and
object size. Stereo objects also have a Spread control. These parameters can
be automated.

Ask students which sounds need object behavior. Movement and precise
localization are good reasons. A stable ambience or reverb return may be
easier to manage in the bed.
{{%/ note %}}

---

## Master files and playback encodes

| Stage | Common format | Purpose |
| --- | --- | --- |
| Music master | ADM BWF | Delivery to a label, distributor, or music service |
| Renderer master | DAMF, ADM BWF, or IMF IAB | Post-production, interchange, QC, and encoding |
| Consumer encode | Dolby Digital Plus with Atmos, TrueHD with Atmos, or AC-4 | Streaming, disc, broadcast, or device playback |
| Cinema package | IAB in a DCP | Theatrical playback |

{{% note %}}
Do not treat one file type as the answer for every Atmos delivery. The client
or platform specification decides what to submit.

For Atmos music, an ADM BWF is widely accepted as the source master. It stores
PCM audio for the beds and objects along with position, binaural, and
downmix-related metadata. Music delivery usually also includes a synchronized
stereo master.

DAMF is the Dolby Atmos Renderer's editable master fileset. IMF IAB packages
immersive audio in MXF for larger post-production and distribution workflows.
Compressed formats such as Dolby Digital Plus with Atmos and AC-4 are playback
encodes. Do not submit one in place of a master unless the delivery
specification requests it.
{{%/ note %}}

---

## Rendering is layout-aware

* Objects retain position metadata until playback
* Beds retain their channel assignments
* The renderer uses the available speaker layout
* Headphone playback uses a binaural renderer

{{% note %}}
A static downmix applies a fixed channel matrix. An Atmos renderer also reads
object position, movement, and size before distributing the audio to the
available outputs.

Rendering cannot guarantee identical sound on every device. Speaker placement,
room acoustics, virtualization, and the renderer itself still matter. The mix
must be checked in the formats the audience is likely to use.
{{%/ note %}}

---

## Binaural monitoring

* Dolby Renderer modes: Off, Near, Mid, Far
* Apple Renderer: Music and Movie monitoring modes
* Optional head tracking and personalized profiles on supported Apple devices

{{% note %}}
In Logic, the Dolby Renderer lets you assign Off, Near, Mid, or Far to each bed
channel and object. These settings change the distance model in Dolby's
binaural render. Off still includes the signal but removes distance modeling.

The Apple Renderer uses Apple's headphone virtualization for Apple Music and
Apple TV previews. Dolby's binaural render modes do not affect the Apple
Renderer. Check both instead of assuming that one headphone preview represents
every service.
{{%/ note %}}

---

## Where Atmos is used

* Theatrical cinema and home video
* Film and television streaming
* Music streaming
* Games and interactive media
* Live broadcasts and sports
* Automotive playback systems

{{% note %}}
Atmos spans several industries, but each uses its own production and delivery
workflow. A music ADM submission, a streaming-series package, and a cinema DCP
are not interchangeable. Start every delivery by reading the recipient's
current specification.
{{%/ note %}}

---

## DAW support

* Pro Tools Studio and Ultimate: integrated or external Dolby Atmos Renderer
* Nuendo: internal Atmos authoring with external-renderer support
* Logic Pro: built-in Dolby Atmos plug-in and ADM BWF export

{{% note %}}
The basic workflow is similar across these systems: route tracks to beds or
objects, send them through a renderer, monitor several output formats, and
export a master.

The details differ. Pro Tools can switch between its integrated renderer and
the separate Dolby Atmos Renderer. Nuendo has extensive multichannel and
post-production tools. Logic keeps the renderer inside the project and offers
a direct ADM BWF export.
{{%/ note %}}

---

## Dolby Atmos Composer

* [fiedler-audio.com/dolby-atmos-composer/](https://fiedler-audio.com/dolby-atmos-composer/)
* Atmos authoring in DAWs with limited multichannel routing
* Beam plug-in for audio and object positioning
* ADM BWF import and export
* Optional OBAM processing on the Atmos master channel

{{% note %}}
Fiedler Audio's Dolby Atmos Composer is an alternative to a DAW's native Atmos
workflow. The Beam plug-in sends audio and panning information from tracks to
Composer. Composer handles monitoring, metadata, and ADM BWF export.

The full version can host OBAM plug-ins on its Master Channel for processing
up to the complete 128-channel Atmos mix. Composer Essential provides a
simpler feature set. Fiedler states that both workflows can operate in DAWs
that do not provide native multichannel routing.
{{%/ note %}}

---

## Other immersive formats

* MPEG-H Audio: channels, objects, scenes, and listener interactivity
* IAMF: an open, codec-agnostic immersive-audio specification
* Eclipsa Audio: a Samsung and Google implementation based on IAMF
* ASAF and APAC: Apple's production format and delivery codec

{{% note %}}
MPEG-H Audio supports channel-, object-, and scene-based material. Producers
can authorize playback controls such as dialogue level, language choice, or
alternate sports commentary. Sony 360 Reality Audio uses MPEG-H Audio.

IAMF is an open specification from the Alliance for Open Media. It can carry
information for rendering to speakers or headphones without requiring one
specific audio codec. Eclipsa Audio is based on IAMF and is supported in parts
of the YouTube and Samsung ecosystem.

Apple introduced ASAF as a production format for high-resolution spatial
audio and APAC as its delivery codec. That workflow is associated with Apple
Immersive Video and newer Apple-platform media. It is separate from the Dolby
Atmos music workflow used by Apple Music.
{{%/ note %}}

---

{{< slide class="stepped" >}}

## Questions to carry forward

* Does this sound belong in the bed or in an object?
* Which renderer will the audience hear?
* Which alternate renders need QC?
* What master does the recipient require?

{{% note %}}
Atmos is not a single plug-in setting or speaker count. It is a production and
delivery system built around audio, metadata, rendering, and quality control.
These four questions are more useful than memorizing a list of platforms.
{{%/ note %}}

---

## References

* [Dolby: Overview of Dolby Atmos Master File Formats](https://professionalsupport.dolby.com/s/article/Overview-of-Dolby-Atmos-Master-File-Formats)
* [Dolby: Object Beds](https://professionalsupport.dolby.com/s/article/What-is-an-Object-Bed-and-how-do-I-set-it-up)
* [Apple: Overview of Spatial Audio with Dolby Atmos in Logic Pro](https://support.apple.com/guide/logicpro/overview-of-spatial-audio-with-dolby-atmos-lgcp449359b0/mac)
* [Apple: 3D Object Panner Parameters](https://support.apple.com/guide/logicpro/3d-object-panner-lgcp3f532b96/mac)
* [Apple: Spatial Audio Monitoring Formats](https://support.apple.com/guide/logicpro/spatial-audio-monitoring-formats-lgcp179f27c1/mac)
* [Avid: Pro Tools and the Dolby Atmos Renderer](https://kb.avid.com/pkb/articles/Knowledge/Pro-Tools-and-the-Dolby-Atmos-Renderer-FAQ)
* [Fiedler Audio: Dolby Atmos Composer](https://fiedler-audio.com/dolby-atmos-composer/)
* [Alliance for Open Media: IAMF](https://aomedia.org/specifications/iamf/)
* [Fraunhofer IIS: MPEG-H Audio](https://www.iis.fraunhofer.de/en/ff/amm/broadcast-streaming/mpegh-audio-production-tools.html)
* [Apple Developer: ASAF and APAC](https://developer.apple.com/videos/play/wwdc2025/403/)
