---
title: "Mixing in Atmos with Pro Tools"
---

Everything here comes from Avid's current Pro Tools and Dolby Atmos documentation, linked at the bottom.

## Two ways to render Atmos from Pro Tools

Pro Tools 2023.12 and later ships an internal Dolby Atmos renderer. You enable it under Setup, then I/O, on the Dolby Atmos tab, and you can monitor in binaural, 5.1, 7.1.4, and other layouts straight from the session.

The external Dolby Atmos Renderer application is still needed for `.atmos` master files, externally recorded metadata, and room EQ. On a single Mac it connects through the Dolby Audio Bridge, a 130-channel virtual Core Audio device that you select as the Pro Tools playback engine. Sync runs as LTC over audio, routed from a Dolby LTC Generator plugin to bridge channel 129. Windows machines need a two-computer setup, because the Audio Bridge is macOS only.

## Beds and objects

- A bed is a channel-based path of up to 7.1.2, with the channel order L R C LFE Lss Rss Lsr Rsr Ltm Rtm.
- An object is a mono or stereo track that carries position metadata, and the renderer decides which speakers reproduce it.
- The renderer accepts 128 inputs in total, split between beds and objects.
- Sessions must run at 48 or 96 kHz, and ADM BWF masters are 48 kHz only.

## Renderer settings that matter for our lab

- The input configuration defines which of the 128 inputs are bed channels and which are objects.
- Each element gets a binaural render mode: Off, Near, Mid, or Far. This setting decides how the headphone fold-down feels, and it is the answer to the elevation problem noted in the session walkthrough below.
- Re-renders are channel fold-downs of the live mix, such as 5.1, 2.0, and binaural, which you check against the [Atmos delivery lesson](/lectures/week-11/atmos-delivery/).

## Worked example: the Lange session

<!-- TODO (Tate): add the session file link and the real track name behind "kidiegren" -->

Lange stemmed his mix down to 34 tracks for the Atmos pass, and the mix uses Atmos panning only, with no other plugins. Details worth studying in class:

- The clicks are step-sequenced across positions, and each step can hold a single location or a trajectory.
- The kick drum uses the native surround panner. Try raising the divergence and listen for the kick spreading more evenly across the speakers.
- The claps are hard-panned to the left and left-surround pair and to the right and right-surround pair.
- The crackle runs as automated objects, using pan linking in mirror mode, which sums the sound to mono so it can travel around the room as one image.
- One track carries elevation that our room cannot fully reproduce, which is exactly where the binaural render modes above earn their keep.

## Export

With the internal renderer, use Bounce Mix and choose the "WAV (Dolby Atmos)" file type. With the external renderer, record a `.atmos` master, then choose File, Export Audio, ADM BWF. Either way, run the QC checklist from the delivery lesson afterward.

---

Sources: Avid Knowledge Base, ["Pro Tools and the Dolby Atmos Renderer FAQ"](https://kb.avid.com/pkb/articles/en_US/faq/Pro-Tools-and-the-Dolby-Atmos-Renderer-FAQ) (updated April 2026); the [Dolby Atmos Renderer Guide](https://professional.dolby.com/siteassets/content-creation/dolby-atmos/dolby_atmos_renderer_guide.pdf) (Dolby Professional); Dolby Professional Support on LTC sync.
