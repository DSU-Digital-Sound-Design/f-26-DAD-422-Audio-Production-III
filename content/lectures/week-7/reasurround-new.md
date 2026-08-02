---
title: "Surround Mixing in Reaper"
---

## Introduction  
Surround (and immersive) mixing lets you distribute sound spatially across multiple speakers to create more engaging and realistic sonic environments. Whether you’re designing cinematic soundscapes, interactive installations, or game audio, REAPER’s flexible routing and panning system makes it an ideal DAW for multi-channel work.  

We’ll explore key techniques for configuring surround projects in REAPER, from channel mapping and dynamic panning to integrating Sound Particles, automating movement, and exporting video with surround audio.  

---

## Before You Start: Setup and Routing Basics  

Before mixing, confirm the following setup steps:

- In **Preferences → Audio → Device**, select your multichannel audio interface and enable enough outputs (6 for 5.1, 8 for 7.1, etc.).  
- On the **Master track**, set **Track channels** to the desired number (6 or 8).  
- In the Master I/O window, map **Master track channels** to your hardware outputs (1 → Left, 2 → Right, etc.).  
- Use a surround meter or analyzer (JS: Loudness Meter Peak/RMS/LUFS) to verify your channel mapping before you start mixing.

---

## Channel-Order Cheat Sheet  

**5.1 (SMPTE/ITU order)**  
1 = L, 2 = R, 3 = C, 4 = LFE, 5 = Ls, 6 = Rs  

**7.1 (SMPTE order)**  
1 = L, 2 = R, 3 = C, 4 = LFE, 5 = Lss, 6 = Rss, 7 = Lrs, 8 = Rrs  

> Always confirm delivery specs, as some film and broadcast formats use different channel orders.

---

## Adding a Multi-Channel Track  

To send a sound only to certain speakers, assign it to the appropriate output channels.

- For **5.1**, surrounds are channels **5–6**.  
- For **7.1**, side surrounds are **5–6**, rear surrounds are **7–8**.  

You can experiment with multi-channel audio files—try [FreeSound’s multichannel library](https://freesound.org/search/?f=channels:6)—to explore how different channel mappings sound.

---

## Direct Routing to Speakers

You can route a mono or stereo track directly to specific speakers by adjusting its channel outputs. For example, to send audio only to the **rear speakers** in a 5.1 setup, route the track to **channels 5 and 6**. 

---

## Using Sound Particles  

**Sound Particles** is a 3D audio design tool that lets you position and animate thousands of sound sources in space. It’s perfect for generating realistic motion and spatial complexity.

Example workflow:  

- Create a project in Sound Particles and apply an **immersive fire preset** (or design your own particle scene).  
- Export your project as a **5.1, 7.1, or AmbiX** file.  
- In REAPER, import the exported file.  
  - If channel-based, map channels to the correct outputs.  
  - If Ambisonic, use IEM plugins (e.g., **BinauralDecoder**, **RoomEncoder**) for playback or monitoring.

Here’s how that looks in practice: a simple mono recording (like a cat growl) can be spatially “thrown” through the space to orbit around the listener.

> See Educational License info for Sound Particles [here](https://soundparticles.com/community/education).

---

## Extending Channel Mapping with ReaSurroundPan and Automation Items  

**ReaSurroundPan** provides flexible, dynamic surround panning. It supports 2D and 3D positioning, divergence controls, and automation for X/Y/Z motion.

### Steps for Setup and Automation  

1. Add **ReaSurroundPan** to your track.  
2. Choose a surround preset (e.g., 5.1 or 7.1).  
3. Position your sound source using the X/Y coordinates in the interface.  

![ReaSurroundPan](../reasurroundpan.png)  
*Speaker arrangement view in ReaSurroundPan*  

4. Click **Param → Show track envelope** to reveal panning parameters.  
5. Right-click on an **envelope lane**, then choose **Insert new automation item**.  
6. Open the automation item’s properties and enable the **LFO**.  
7. Adjust **phase, skew, pulse width**, etc. to sculpt motion paths.  
8. Layer multiple automation items (for X, Y, width, divergence) to create compound movement, such as circular or figure-eight panning.

This method enables rich, repeatable motion without needing manual keyframes.

---

## Recording Automation in Real Time  

You can also perform panning live:  

1. Arm ReaSurroundPan’s **X and Y parameters** for automation.  
2. Set automation mode to **Write** (or **Touch** to record safely).  
3. Play the session and move the panner while recording.  
4. Return automation mode to **Read** to lock it in.  

![Pan moves](../pan-moves.png)  
*Preset-style panning gestures created with envelope automation in ReaSurroundPan*  

If you’re working in 3D, experiment with **Z-axis** automation for vertical motion—useful for flyovers, drones, or height speakers.

---

## Panning Multiple Point Sources  

You can manage multiple sounds together as one cohesive panning unit:  

1. Create a “Panner” track.  
2. Send several source tracks to it, routing each to a different channel pair (e.g., 1/2 → 1/2, 1/2 → 3/4, 1/2 → 5/6).  
3. Add **ReaSurroundPan** to the Panner track.  
4. Automate motion on this track to control all sources collectively.  

![Surround mixing](../surroundpanmix.png)  
*Managing multiple sources in ReaSurroundPan*  

Rename sources in ReaSurroundPan to stay organized—this is essential in large spatial sessions.

---

## Rendering Video with Surround Audio  

When your mix is ready for export:  

1. **Set channel counts**  
   - Master track: set *Track channels* to 6 (5.1) or 8 (7.1).  
   - Confirm hardware routing aligns with your speaker setup.  
2. **Render settings**  
   - File → Render  
   - Source: **Master mix**  
   - Channels: **6 or 8**  
   - Format: **Video (FFmpeg/libav)**  
   - Choose container/codec:  
     - **MOV/MKV + PCM 24-bit** for production  
     - **MP4 (H.264) + AAC 5.1** for distribution  
3. **Verify channel order**  
   - Use the SMPTE/ITU order from the cheat sheet above.  
   - Render a short test file and check playback channel mapping.  
4. **Optional: export stems**  
   - Some workflows require discrete mono files (one per speaker).  
   - Render → Stems (selected tracks) and label each stem (e.g., `Mix_Ls.wav`, `Mix_Rs.wav`).


