---
title: "Atmos Mix"
number: "04"
weight: 4
week: 10
assigned: "2026-10-30"
due: "2026-11-16"
summary: "A Dolby Atmos mix of a song or a film excerpt, using object-based panning and automation in Logic Pro."
tools: ["Logic Pro", "Dolby Atmos Renderer"]
# the brief in the body already spells out deliverables and grading
rubric: false
---

## Your task

Create a **2–3 minute Dolby Atmos mix in Logic Pro**, due **Monday, November 16**. Use spatial placement and movement to support a song or film scene, then verify that the mix translates to speakers and headphones and survives ADM export.

You may develop the session started in class. This project assesses mixing and delivery; you do not need to compose new music, record new sources, or redesign a film's entire soundtrack.

## 1. Choose your source

Choose one route. Use enough separately controllable source tracks to build a bed and at least four object tracks.

| Route | Source and scope | What the mix should achieve |
| --- | --- | --- |
| Music | A coherent 2–3 minute passage from [Aiguille Rouge – Bebe Grand](https://cambridge-mt.com/ms/mtk/#BabeGrand), or another multitrack agreed with the instructor | Keep the intended focal elements clear; use space to support phrasing, arrangement, and contrast |
| Film | A continuous 2–3 minute excerpt from [Like Lambs](/projects/like-lambs-5-1/), using the supplied dialogue and effects | Preserve picture sync, intelligible dialogue, and convincing perspective; use placement and movement to support the scene |

Choose a passage with a clear beginning and ending, and allow effects to decay naturally. Confirm your source and excerpt by the **November 6 checkpoint**. The same duration and technical requirements apply to both routes.

## 2. Set up and mix

Use the [Logic Atmos workshop](/lectures/week-9/atmos-logic/) for setup instructions.

1. Work at **48 kHz** with a **7.1.2 bed**. Use 24-bit recording for any new audio. For film, match the project frame rate to the supplied picture.
2. Use both the shared bed and **at least four object tracks**. Explain why the routing suits each source's role. A stereo object track is valid; it uses two object inputs.
3. Include **at least two purposeful spatial automation gestures across at least two object tracks**. Make their positions and timing serve musical phrasing or on-screen/offscreen action. Other objects may remain stationary; explain any featured stationary placement.
4. Balance the bed and objects so intended focal elements remain clear. Use width, depth, and height where they help. More movement or more extreme placement does not earn more credit.
5. Check the mix through the room's verified **7.1 monitoring layout** and on headphones. Compare the Dolby binaural and Apple Renderer previews, plus a stereo render. Address missing elements, distracting level shifts, and unwanted masking.

Our room has no discrete height speakers. You can author height positions, but assess their translation through the available speaker and headphone renders. Do not select 7.1.4 monitoring for the 7.1 room.

## 3. Check levels and export

Follow the [Atmos delivery lesson](/lectures/week-11/atmos-delivery/) for measurement and export procedures.

- Measure the complete submitted passage through the **5.1 render**, using a multichannel loudness meter after the Dolby Atmos plug-in. Meet the course limits of **−18 LUFS-I or quieter** and **−1 dBTP or lower**. These limits apply to both routes for this assignment; they are not universal film or Atmos delivery standards.
- Export **Dolby Atmos ADM BWF** using **File > Export > Project as Spatial Audio**. The monitoring format does not change this master export.
- Use **File > Import > Create Project from ADM BWF** to open the exported master as a new verification project. Check its start, ending, bed/object content, automation, and balance. Fix problems in the source project and export again.

## Checkpoints

These checks support the project and do not add separate graded deliverables.

- **November 6: working mix.** Bring the chosen passage in a Logic session with its media, working bed/object routing, and one automation gesture. Play an excerpt, identify your intended focus, and bring one question.
- **November 9: delivery check.** Bring the mix far enough along to measure and export an ADM test. Verify that it reopens while the instructor is available. Save the remaining fixes for the independent work days, then repeat the checks on the final mix.
- **November 13: progress bounce.** Post the scheduled 1–2 minute listening preview to D2L for conference-week participation. Identify it as a stereo or binaural render and include one question. This preview is separate from the final ADM master.

Arrange a room listening check by November 9. November 11 and 13 are independent work days; studio access during the instructor's absence requires prior arrangements. Continue headphone checks on laptops and keep the final weekend for revisions rather than first-time setup.

## Submit to D2L by November 16

1. **Logic Pro project folder**, with all source media included.
2. **Final ADM BWF master**, verified by creating a new project from it.
3. **One short document** containing:
   - **Reflection, 1–2 paragraphs:** explain bed/object choices, the two automation gestures, and one problem you solved. Include timestamps for the gestures. For film, describe how placement supports the picture; for music, describe its role in the arrangement.
   - **QC record:** measured integrated loudness and true peak from the final 5.1 render; speaker/headphone formats checked, including Dolby and Apple previews and stereo; one timestamped observation and the change you made or why you kept the result; confirmation that the final ADM reopened correctly. Add one meter screenshot showing the final readings.

## Grading rubric: 70 points

| Criterion | Exemplary | Proficient | Developing | Emerging | Points |
| --- | --- | --- | --- | --- | --- |
| **Bed and object use** | Working bed and at least four object tracks; routing and stationary/moving choices clearly serve source roles and are explained | Required routing works; most choices are explained | A required source path or object track is missing, or choices are unclear | Bed/object routing does not work or is not demonstrated | /19 |
| **Spatial design** | At least two purposeful automation gestures across two objects; placement and restraint support the musical or narrative focus | Required gestures work and mostly support the piece | Required gestures incomplete, or placement distracts from the intended focus | Little intentional spatial design or automation is demonstrated | /16 |
| **Mix balance** | Intended focal elements stay clear; levels and transitions are controlled; perspective suits the source | Mostly clear and balanced, with minor unwanted masking or level shifts | Repeated masking, abrupt level changes, or perspective problems obscure the material | Balance makes essential material difficult to follow | /14 |
| **Loudness and delivery** | Course limits met and documented; ADM reopens with expected content and automation; project includes all media | Delivery works with a minor documentation or organization omission | Level limits missed, media incomplete, or ADM verification identifies unresolved problems | Master or project cannot be used, or required delivery evidence is missing | /12 |
| **Monitoring and QC** | Speaker, Dolby/Apple headphone, and stereo checks documented; a timestamped observation supports a revision or justified decision; essential content translates | Required checks documented; one minor translation issue or weak explanation remains | Some checks or evidence missing, or significant translation problems remain | No meaningful monitoring comparison or QC evidence | /9 |

**Total: ___ / 70**
