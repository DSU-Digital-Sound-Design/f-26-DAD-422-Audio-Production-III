---
title: "SpatGris"
---

[SpatGRIS](http://gris.musique.umontreal.ca/) is a software package for sound spatialization. It differs slightly from the other programs we've used in the course.

SpatGRIS is a controller program that lets you setup your speaker configuration. It also takes audio as an input from your DAW and sends the audio out to your speakers. Audio is sent from your DAW using the BlackHole software for inter app audio routing.

The first thing I had to do was setup the speaker array in the _Speaker Setup Edition_. There is a useful interface that can be reached using _Opt+W_. I tested the speaker layout using the pink noise generator then soloed each speaker to hear it was correct. I then saved this layout as a speaker setup.

While audio is sent to the SpatGRIS app from your DAW using BlackHole, panning data is sent using Open Sound Control (OSC). This means that the panning can be controlled from anything that sends OSC. This is your phone, computer, or whatever you can think of.

## Reaper Setup

In Reaper setup a new track. Take it out of the master send and create a new hardware output to outputs 1 / 2. This makes it send to BlackHole instead of your speakers directly. Add a ControlGris plugin.

## Source Link

These determine the relationship between stereo sources.

## Trajectories

Try the different trajectories. This is actually way more powerful than the atmos panner in ProTools. Choose a trajectory type then click activate to start moving your sources around. Trajectories can go back and forth. Derivation degrees per cycle changes your trajectory a little bit each time. You can also change the speed of the trajectory. Also try to draw in trajectories.

To make these trajectories stick you need to record them as automation.

To add a new track you need to set it's output to hardware 3/4. This next source should be set to source ID 3.

Also try a multichannel file. This requires some more routing.

Spat can also be controlled from MaxMSP.

To export your project you can record either as mono files or interleaved.

## Project idea

If anyone wanted to it would be cool to combine the projects from the topics class and this class and build a website that can control spatialization in SpatGRIS.
