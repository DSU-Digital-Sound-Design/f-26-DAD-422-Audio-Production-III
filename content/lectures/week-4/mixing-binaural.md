---
title: "Mixing Binaural Audio"
---

Tools: [Panagement](https://www.auburnsounds.com/products/Panagement.html), [Ambisonic Toolkit for Reaper](https://www.ambisonictoolkit.net/download/reaper/)

## Panagement

Listen to some of the [sound samples](https://www.auburnsounds.com/products/Panagement.html#samples) to get a feel for what this plugin can do.

### Cheat Sheet

![](https://www.auburnsounds.com/downloads/panagement-cheat-sheet.jpg)

## Ambisonic Toolkit

![](../atk-network.png)

<!-- TODO: Follow the videos here: https://www.ambisonictoolkit.net/documentation/reaper/tutorials/ -->

We will use the ATK to mix our binaural audio. We'll get into ambisonics in much more detail later in the class, but for now we're using it to have access to the ambisonic transforms.

Be sure to look at the documentation for [ATK for Reaper](https://www.ambisonictoolkit.net/documentation/reaper/).

### Encoding Mono using ATK for Reaper

[Source](https://vimeo.com/182434517?embedded=true&source=vimeo_logo&owner=805020)

Download Reaper and the ATK Toolkit and install. Also download the [Harpex-X](https://harpex.net/index.html) plugin for visualization purposes.

Create a new project and call it MonoDecode. Make sure to create a subdirectory for the project when you save.

Make the master track visible from the view menu. Then set your track channels on the master to 4.

Now add the _ATK FOA Decode Binaural_ js plugin to the master track. See the options for the variety of Head Related Transfer Functions available.

Create the visualization track then the B-Format Mix tracks. Make sure that they both have 4 track channels, because b format uses four channels. On the visualization track turn off _Master send_. Also set this track to receive all 4 channels of audio from the **B format mix** track. Now load the Harpex-X plugin on the visualization track. Set the output mode on the plugin to binaural to simplify the visualization.

**Planewave**

We will now add several tracks to try different encoders. Add a child track to the **B Format Mix** track, call it **Planewave**, and set it to 4 track channels. Add any mono source to this track. Now add the **ATK FOA Encode Planewave** plugin to the track. Change both Azimuth and Elevation settings; hear the differences and look at the visualizer.

Notice how directional this mono source is. We can clearly hear where it is coming from. If we want to alter this perception we can transform the sound field. Add the _ATK FOA Transform DirectO_ plugin. Pulling the blue dot towards the center will create a more "in the head", omnipresent, sound. This is sort of like a spatial low pass folder.

> DirectO - Adjusts the directivity of an FOA soundfield across the origin, functioning as a spatial low-pass filter; with an increasing degree of transformation, the soundfield becomes less directional, eventually becoming omnipresent.

**Omni**

Duplicate the **Planewave** track and rename it **Omni**. Remove the plugins. Add the omni encoder **ATK FOA Encode Omni**.

> Omni - Encodes a mono signal as an omnidirectional soundfield.

Now we can do something like the inverse of the previous example, to take an omnidirectional recording and make it as directional as we want. Add the **ATK FOA Transform FocusPressPushZoom** transform.

> FocusPressPushZoom - Unified interface to four different spatial transforms. Focus and Zoom are dominance related transforms and can be described as ‘emphasising’ elements in the direction of interest. Press and Push differs, and rather than emphasising elements in a target direction, all are ‘pressed’ or ‘pushed’ towards the direction of interest. With increasing spatial transform all four transforms collapse the soundfield to a planewave arriving from the direction of interest specified by azimuth and elevation.

Try press mode and move the blue dot. As you move to one side the sound starts getting a more directional feeling. Compare the previous track to hear what sorts of differences there might be. There are subtle differences between press and push. Experiment with both.

**Spreader**

Add a new track called Spreader. Make sure it has 4 track channels. Add the spread encoder. We'll first test this encoder with pink noise, so add a pink noise generator. See the way this encoder is visualized in Harpex.

> Spread - Encodes a monophonic signal by smoothly rotating the signal across the soundfield by frequency.

Changing the kernel size will increase the resolution. You can also change the bands per octave.

Add a transform to make this diffusion pattern less recognizable. Add the **RotateTiltTumble** transform.

> RotateTiltTumble - Multi-axes FOA rotations

Add the **PressPushZoom** transform in order to focus this sound for mixing.

**Diffuser**

> Diffuse - Randomises the phase of the incoming monophonic signal to create a diffuse field.
