---
title: "Sound Particles Introduction"
---

Sound particles is free for student use. See [here](https://soundparticles.com/products/soundparticles/plans) for details.

Sound Particles is an immersive audio software capable of generating thousands (even millions) of sounds in a virtual 3D audio world. Creating highly complex sounds has never been this quick.

## Presets

When first opening up sound particles look at the templates. The interface has an allows you to play the original sound, then audition the sound effected with sound particles.

Once one of the presets is opened you have to add one or multiple sounds to the _audio files_ box. Now you can render your sound particles. This can be done either in real-time or offline. To render in real-time just press the space bar. If you hear drop outs try to render offline by clicking the render button.

## Particles

Now let's start with a blank project so we can see how each part works together. Add a _particle group_ by clicking on the plus on the left side of the screen. Add or remove particles under the general box on the right hand side. Leave this at 100 for now.

Change the shape of the particle starting point with the start zone drop down. There are many shapes to chose from. Set this to _Sphere (surface)_ for this example.

Now this becomes interesting if you add movement modifiers. These will move the particles during playback, sort of like automation. Try _Straight line movement -> Add velocity_. Particles move in a straight line from the start place with random velocities.

Add an audio modifier _Random Delay (2s)_. This will delay the start of each particle randomly between 0 and 2 seconds. This time can be changed, try 5 seconds.

Now it's time to import audio. Import multiple audio files to get a complex scene.

Finally add a microphone system to "record" your particles. By default it's mono, but it can be any type of system. This represents the output file format. So for our purposes we wna tto use "Multichannel 7.1 (3/4)".

Finally we can export this rendered microphone array for use in another DAW. Right click on the microphone track and select _Export Audio_. Make sure your channel order is correct and export. It may be a good idea to export with a standard channel order so that you can use these files in other places, and then remap the channels in a DAW.

Other things to make:

- an explosion with the doppler explosion preset
- Fly by with plane
- Jet information - sounds like space ships
