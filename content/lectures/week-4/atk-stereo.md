---
title: "Encoding Stereo in ATK"
---

Download some example sounds [here](https://www.ambisonictoolkit.net/download/recordings/).

Now we'll look at some stereo encoding options.

Setup your project in the same way as for mono sources, with a master track that decodes to binaural and a b format mix track to hold all of your encoders. Route the encoders folder to the viz to see what's happening. Make all tracks 4 track channels. Don't send the viz to the master. Also make sure the master track received 4 tracks.

**Stereo Encode**

Now we'll add encoder track as a subfolder to the b format mix track. The first is a stereo encoder track using _ATK FOA Encode Stereo_. This encoder uses two plane wave encoders for the left and right directions.

Now rotate the stereo field with RoateTiltTumble. You can keep the stereo width you set with the stereo encoder but move the image to different parts of the sound field keeping the relationship the same. Also try to tilt and tumble listening to the result.

Now add DirectO, a spatial lowpass filter. This will reduce the directness of the sound source. This can make the transform sound a bit more natural.

**SuperStereo Encode**

Add another track then add the _SuperStereo_ encoder. We can see how different this encoding is, sound is spread around the stereo field in more than two plane waves. Sound bounces around to recreate natural reflections.

**UHJ Encode**

Add anther track and the URJ Encoder. Increase the Kernel size to improve the sound quality.

Here are a few UHJ format recordings to try: https://www.ambisonic.info/tetramic/samples.html
