---
title: "Listening to Apple Music Dolby Atmos on a 7.1 System with an Audio Interface Using Only BlackHole"
date: 2024-06-12
draft: false
description: "A practical guide for setting up a Mac to route true 7.1.4 (or 7.1) Atmos audio from Apple Music, using only the free BlackHole virtual audio driver."
categories: ["lectures", "week-9", "atmos-apple-music"]
---

***

**Want to experience Apple Music’s Dolby Atmos tracks through your multichannel studio rig or home theater system? Here’s a practical guide for setting up a Mac to route true 7.1.4 (or 7.1) Atmos audio from Apple Music, using only the free BlackHole virtual audio driver.**

***

### Why Do This?
Apple Music supports Dolby Atmos playback, but sending real multichannel audio to a pro audio interface is tricky. By default, Apple Music restricts multichannel output to 5.1 or even converts everything to stereo unless it sees the “right” device—a 12-channel/7.1.4-capable output. This blog shows how to convince Apple Music to output full 7.1.4 and route those channels to your system.

***

### What You’ll Need

- **Mac running macOS (latest preferred)**
- **BlackHole 16ch** (from Existential Audio)
- **Audio interface** with enough outputs (ex: 8+ for 7.1)
- **DAW or host application** (Logic, Reaper, etc.) to pass audio through
- **Audio MIDI Setup** application (built-in)

***

### Step 1: Install and Configure BlackHole for 12 Channels

1. **Download and install BlackHole 16ch**  
   Get it from Existential Audio.
2. **Open Audio MIDI Setup**  
   (Spotlight → “Audio MIDI Setup”)
3. **Select BlackHole 16ch → Configure Speakers**  
   - Right-click BlackHole 16ch  
   - Click **"Configure Speakers..."**
   - Choose **7.1.4** (12 channels) in the dropdown  
   - Assign channels 1–12 for surround and height speakers (L, R, C, LFE, sides, rears, heights)

***

### Step 2: Create an Aggregate Device

1. In Audio MIDI Setup, click the **"+"** button and choose **"Create Aggregate Device."**
2. **Check your audio interface first** (set as clock source), then **check BlackHole 16ch.**  
   - Make sure Drift Correction is enabled for BlackHole.

*Tip: Setting up BlackHole’s channel configuration first ensures the aggregate device sees it as a 12-channel endpoint.*

***

### Step 3: Set System Output and DAW Routing

1. **Make BlackHole 16ch your Mac system audio output.**  
   - In Audio MIDI Setup, right-click BlackHole 16ch, select **“Use this device for sound output.”**
2. **In your DAW:**  
   - Set the **aggregate device** as audio input/output.
   - Create 12 audio tracks to capture channels 1–12 from BlackHole.
   - Route each track to the appropriate output channel of your audio interface (corresponding to your speakers).
3. **Activate live monitoring** in the DAW on all input tracks.

***

### Step 4: Configure Apple Music and Test

1. **In Apple Music:**  
   - Go to Settings → Playback.
   - Set Dolby Atmos to **“Automatic”** (not “Always On”).
2. **Play a Dolby Atmos track.**
3. **Test with a Dolby Atmos functional test or channel check track** to confirm audio reaches all 7.1.4 channels.

***

### Troubleshooting & Common Issues

- **Only 5.1 audio?**  
  Make sure no device in your aggregate has more than 12–16 active channels. Apple Music folds to 5.1 if it detects too many outputs.
- **No sound from rears or heights?**  
  Double-check BlackHole’s configuration and your DAW channel routing.
- **Audio glitches?**  
  Ensure your interface is the aggregate clock source; enable drift correction on BlackHole.

***

### Conclusion

With this setup, you can finally listen to Apple Music’s immersive Dolby Atmos content on your multichannel monitors. The key is forcing Apple Music to see a 12-channel (7.1.4) output device—BlackHole—then using your DAW to move those channels to your real speakers. No fancy software required—just smart virtual routing!

