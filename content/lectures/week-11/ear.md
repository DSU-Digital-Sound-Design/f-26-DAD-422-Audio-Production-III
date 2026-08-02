---
title: "Ear Production Suite"
---

The [Ear Production Suite](https://ear-production-suite.ebu.io/) is a set of open source VST plugins for object based sound spatialization. The plugins are optimized for Reaper, but can be used with any DAW.

## Components

- EAR production suite VSTs
  - define audio assets and author the ADM file, and monitoring plugins
- ADM Export Source VST
  - Support for export using Facebook 360 or VISR
- Reaper Extension
  - Import and export ADM files

## Plugins

![](../ear-plugins.png)

- Earsuite plugins
  - Input
    - many inputs - ex: EAR Object, EAR DirectSpeakers
  - Control
    - One per project - EAR Scene
    - This can be fed by any number of input plugins and feed any number of rendering plugins the available input plugins are ear object and eardirect speakers which are used for the adm objects and direct speakers type definitions respectively the central control plugin is called the ear scene this receives metadata from each one of the input plugins and has audio routed to it on specifically allocated channels from each input plugin it provides a user interface for authoring the adm structure and passes this collated metadata onto the rendering plugins the audio is also routed through to the rendering plugins.
  - Rendering
    - Many renderers - ex: EAR Monitoring 0+2+0 etc.

## Basic Setup

Create a new track and add an instance of the Ear Scene plugin to it. Make sure to set the track channels to 64 and don't send to Master.

To hear what's happening create a new track with an EAR Monitoring plugin set to 0+2+0 for stereo output. This should also be 64 channels.

Route your all 64 channels of the scene track to the monitoring track.

Create a new track and add an instance of the EAR DirectSpeakers plugin. Select 5.1 in the layout and 1-6 for the routing. This track should be 6 channels and not sent to Master because it goes to the scene plugin first. Send all 6 channels to the scene. Check the scene plugin to see that it has automatically picked up the DirectSpeakers input.

Add a random 5.1 audio file to this track. You can find them on freesound.org by searching by channel count.

Make a new track and add an instance of EAR Object. Select the next available channel routing 7. Take it out of the master send and then send 1 -> 7 of scene. Move the object around to make sure the routing was set up correctly. If it was then record some automation.

We can now render our project as an ADM BW64 file. This file will contain all of the panning we wrote to it.

You should be able to recreate this project with only the ADM wav file. Let's try that. Notice how it recreates all of our panning moves so we can keep editing. Amazing!

ADM files can also be added to projects then exploded.

## Importing from Logic

Let's try this with the Lil Nas X mix. We can export from logic then import into Reaper using _Create project form ADM BW64 file -> Create using EAR_.

## Exporting

If we want to export this project for listening only we can still render a channel based file.
