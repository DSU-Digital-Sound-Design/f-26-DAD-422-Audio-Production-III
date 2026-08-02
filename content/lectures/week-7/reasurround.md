---
title: "Surround Mixing in Reaper"
---

## Introduction  
Surround mixing allows you to create immersive audio by distributing sounds across multiple speakers. Whether you’re building a cinematic soundscape, crafting 3D audio for installations, or designing game sound, Reaper’s flexible routing system makes it a powerful tool for multi-channel mixing. In this post, we’ll explore key techniques, from configuring multi-channel output and mapping channels to working with Sound Particles, automating surround panning, and rendering video with surround audio.

---

## Distributed Sources  

One of the simplest ways to begin with surround mixing in Reaper is to send a mono or stereo track to all speakers. First, ensure that both your **track** and **master track** are using **8 track channels**. You can adjust this by clicking the routing button for each track and setting the **track channels** to 8.  

Once your outputs are set to **multi-channel output**, your setup should look like this:  

![Multi-channel routing](../output-source.png)  
*Track routing for multi-channel output in Reaper*  

Try playing back any mono or stereo track with these settings. You’ll now hear the sound across all speakers.

---

## Adding a Multi-Channel Track  

To route a multi-channel track to specific speakers, configure its channel outputs. For example, to send audio only to the **side speakers**, use **channels 7 and 8** in your routing matrix.  

Try with [freesound](https://freesound.org/search/?f=channels:6) multi-channel files to experiment with different speaker configurations.

---

## Using Sound Particles  

**Sound Particles** is a powerful tool for creating audio files encoded with spatial data. It allows you to design sounds that move dynamically in a 3D space. For example, you can take a simple recording—like a cat’s growl—and use Sound Particles to move it through your mix environment.  

Here’s another idea: I used Sound Particles to create an **immersive fire soundscape**. Starting with a basic fire recording, I applied the **immersive fire preset**, which automatically places the sound around the listener. Export your spatial audio from Sound Particles, then import it into Reaper as a multi-channel file to experience it in your surround mix.

---

## Extending Channel Mapping with ReaSurroundPan and Automation Items  

You can achieve sophisticated channel mapping and modulation using **ReaSurroundPan** for surround control. This tool lets you pan audio dynamically across multiple speakers, with full automation support for creative modulation.  

### Steps for ReaSurroundPan Setup and Automation  

- **Add ReaSurroundPan** to your track and select the appropriate surround preset (e.g., 5.1 or 7.1).  
- **Route your audio** to different channels using ReaSurroundPan’s interface. For example, set the X and Y coordinates of your input channels to align with your speaker arrangement.  

![ReaSurroundPan](../reasurroundpan.png)  
*Speaker arrangement view in ReaSurroundPan*  

- **Reveal the panning parameters** for automation by clicking the param button in the ReaSurroundPan interface and selecting **‘show track envelope’**.  
- **Insert an Automation Item**: Right-click on the timeline and select **Automation Item → Insert New Automation Item**. Use the **LFO editor** to create custom panning shapes, such as sine waves or square pulses.  
- **Experiment with LFO parameters** such as **skew, pulse width, and phase** for creative modulation.  
- **Combine multiple automation items**: For advanced movement, use several automation items across different parameters (e.g., X, Y, and width) to simulate complex trajectories, such as circular panning patterns.  

This approach gives you fine-grained control over how sound moves through the space, making it ideal for immersive audio applications like game audio or installations.

---

## Recording Automation  

To add automated movement to your panning, use **ReaSurroundPan's automation features**:  

1. Find the automation parameters for **input channels 1 and 2 (X and Y coordinates).**  
2. **Arm these parameters** and set the automation mode to **Write**.  
3. Play your session and move the parameters to **record automation in real time**.  
4. **Set the automation mode back to Read** once you're finished to prevent unwanted overwriting.  

Here’s how you can use **preset pan moves**:  

![Pan moves](../pan-moves.png)  
*Preset pan moves in ReaSurroundPan*  

For example, the **'To Left Front'** preset moves both pucks toward the front left speaker when increased. This simplifies automation by controlling movement with a single parameter.  

Pro tip: If you’re working with **height channels**, experiment with **Z-axis shapes** to control vertical movement.  

---

## Panning Multiple Point Sources  

You can combine multiple sources into one track and control them as if they were part of a single multi-channel track:  

1. **Send multiple sources** to a single track and route each one to a different track channel.  
2. Use **ReaSurroundPan** to automate and pan these sources as a cohesive unit.  
3. **Rename tracks** in ReaSurroundPan to stay organized.  

![Surround mixing](../surroundpanmix.png)  
*Managing multiple sources in ReaSurroundPan*  

---

## Rendering Video with Surround Audio  

To export your surround mix, follow these steps:  

1. Go to **Options → Channels → 6** to configure your output for 5.1 surround.  
2. Select an appropriate video format that supports multi-channel audio (e.g., **AVI or MP4**).  
3. Render your project, ensuring all audio tracks are routed correctly to match the surround format.  

