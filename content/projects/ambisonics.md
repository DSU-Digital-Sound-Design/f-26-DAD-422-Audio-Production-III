---
title: "Ambisonics"
number: "03"
weight: 3
week: 6
assigned: "2026-09-30"
due: "2026-10-19"
summary: "Create a first-order ambisonic mix and deliver both binaural and 7.1 WAV files."
tools: ["REAPER", "Ambisonic Toolkit", "IEM Plug-in Suite", "Zoom H3-VR"]
# this project carries its own rubric table in the body
rubric: false
---

## Project Overview

Make a first-order ambisonic (FOA) mix in REAPER using the [Ambisonic Toolkit](https://www.ambisonictoolkit.net/download/reaper/). You can create an original piece or mix an existing multitrack session. In either case, use spatial placement and movement to shape how we hear the music or scene. Include at least two audible spatial automation moves, visible in your REAPER session. Render both a binaural WAV and an eight-channel 7.1 WAV from the same FOA mix. Add one deliberate low-frequency effect to the 7.1 WAV's LFE channel.

## Choose an Approach

### A. Original Ambisonic Work

- Create a 1–3 minute piece of music, sound design, or narrative fiction.
- Record at least one source with the Zoom H3-VR in ambisonic mode.
- Make one original stereo recording using XY, ORTF, or Mid-Side, and document the setup.
- You may use mono sources. Encode them to FOA before applying spatial transforms.

### B. Multitrack Ambisonic Mix

- Choose a session from [Mike Senior's multitrack library](https://www.cambridge-mt.com/ms/mtk/) with at least 20 source tracks. You do not need to use every track.
- Identify two or three focal elements and use placement and movement to support them.
- Encode mono and stereo material to FOA before spatializing it.
- If your session strains the computer, freeze or print heavy effects chains.

## Spatial Goals

Decide where the listener should focus. Use depth, height, and rotation when they help the piece, and let some sounds remain still so movement has an effect. Your two automation moves should be audible in the render and serve the music or story.

## Project Setup

1. Keep the working mix in FOA B-format. Encode non-ambisonic sources before applying FOA transforms or panners. FOA tracks need four channels.
2. For Project A, set the Zoom H3-VR to record **FuMa (WXYZ)** so its files work directly with ATK without a conversion step. The recorder can also record AmbiX (ACN/SN3D); if you choose AmbiX, convert it to FuMa before using ATK. Keep channel order and normalization consistent throughout the mix.
3. Keep the FOA bus undecoded. Feed it to separate output tracks for the binaural and 7.1 renders; do not decode each source track.

Follow the [ATK setup lesson's binaural and 7.1 export steps]({{< rel "lectures/week-5/atk-setup/" >}}#render-binaural-and-surround-wavs) to make both WAVs. The 7.1 file must use the classroom channel order. Put a separate low-frequency effect on channel 4, the LFE channel, using the final print bus shown in the lesson. This is part of the rendered WAV, not merely a hardware send to the subwoofer.

## Submission Requirements

Submit these items to D2L:

1. A **binaural stereo WAV** at 48 kHz / 24-bit for grading.
2. A **7.1 WAV** at 48 kHz / 24-bit with eight interleaved channels in the classroom order, including a deliberate effect on LFE channel 4, for playback in class.
3. A **consolidated REAPER project**. Use "Save As… → Copy all media into project directory," then zip the folder as `lastname_firstname_ambisonics_v1.zip`.
4. A **two-paragraph reflection** of about 250–400 words. Explain your spatial choices, the two automation moves, your LFE effect, and how ATK and the format converter affected the mix. Describe one problem you solved. Include at least one screenshot showing routing or automation. If you chose Project A, also describe both recordings and include a photo of your stereo microphone setup.

---

## Grading Rubric (70 points total)

| Criterion | Exemplary | Proficient | Developing | Emerging | Points |
| --- | --- | --- | --- | --- | --- |
| **Spatialization (21 pts)** | Depth, height, and rotation are used purposefully and serve the piece, meeting the expectations in the brief | Spatial movement is present and effective in most of the piece | Some spatialization, applied without evident purpose | Static field | /21 |
| **FOA Compliance (17 pts)** | Non-ambisonic sources encoded before FOA transforms; any needed AmbiX-to-FuMa conversion is correct; FOA bus stays undecoded; FuMa-to-AmbiX conversion and 7.1 decoder routing are correct | Signal chain works with a minor routing or format issue | Encoding, format, or decoder routing is wrong in places | Chain does not produce a valid ambisonic mix | /17 |
| **Source Material (11 pts)** | Project A: the H3-VR recording and a documented stereo technique. Project B: two or three focal elements supported by spatialization | Required sources or focal elements present; documentation thin | A required source is missing, unusable, or unclear in the mix | Required sources or focal elements absent | /11 |
| **Automation (11 pts)** | At least two meaningful spatial moves, visible as automation lanes and audible in the render | Two moves present; one is subtle | One move, or automation that does not read | No automation | /11 |
| **Render, Project, and Reflection (10 pts)** | Binaural and eight-channel 7.1 WAVs with a deliberate LFE effect on channel 4, consolidated project, and a 250 to 400 word reflection with the required screenshot and, for Project A, microphone photo | All deliverables present; documentation is thin | A render, LFE effect, or documentation is missing, or project media is not consolidated | Deliverables incomplete or project cannot be opened | /10 |

**Total: \_\_\_ / 70**
