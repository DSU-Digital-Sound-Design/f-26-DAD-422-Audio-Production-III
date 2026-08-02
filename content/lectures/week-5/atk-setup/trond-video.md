First video transcript:

### A Guide to Encoding Mono Audio with the Ambisonic Toolkit for Reaper

For audio artists and sound designers venturing into the world of immersive audio, the Ambisonic Toolkit (ATK) for Reaper offers a powerful and accessible entry point. This toolkit, developed by Trond Lossius, provides a suite of plugins for working with Ambisonic surround sound, a full-sphere surround sound format. This article, based on a tutorial by Trond Lossius, will walk you through the initial steps of encoding mono sound sources into first-order Ambisonics using ATK for Reaper.

#### Getting Started: Essential Tools

Before diving into the encoding process, you'll need a few key pieces of software:

*   **Reaper:** A powerful and affordable Digital Audio Workstation (DAW) that is highly customizable. You can download a free, fully functional 60-day trial from their website.
*   **Ambisonic Toolkit for Reaper:** This is the core set of free plugins you will be using. They can be downloaded from the official Ambisonic Toolkit website at ambisonictoolkit.net. The toolkit is available for both Windows and OSX.

For visualization and more advanced processing, the tutorial also mentions two other useful tools:

*   **Harpex:** This is a high-quality B-format decoder that provides excellent visualization of the soundfield. While it is a paid plugin, it can be a valuable tool for serious Ambisonic work.
*   **Matthias Kronlachner's Plugins:** A suite of free and useful multichannel and Ambisonic plugins that can complement the ATK.

#### Setting Up Your Reaper Project for Ambisonics

To begin, you need to configure your Reaper project to handle the multi-channel audio that Ambisonics requires.

1.  **Create a New Project:** Open Reaper and start a new project.
2.  **Set Up the Master Track:** The key to a proper Ambisonic workflow in Reaper is to ensure your tracks can handle 4-channel audio for first-order Ambisonics.
    *   Click on the routing button on the Master track.
    *   Change the track channels from the default of 2 to 4.
3.  **Add a Decoder to the Master Track:** To monitor your Ambisonic mix, you'll need to decode it to a format you can listen to, such as binaural for headphones.
    *   On the Master track, add the "ATK FOA Decode Binaural" plugin. This will allow you to hear a 3D representation of your Ambisonic soundfield through headphones.

#### Encoding a Mono Sound Source

Now that your project is set up, you can start encoding a mono sound source.

1.  **Import a Mono Audio File:** Drag and drop a mono audio file onto a new track in Reaper.
2.  **Set the Track Channels:** Just like the Master track, you need to set this track's channel count to 4. Click the routing button on the track and change the number of channels to 4.
3.  **Add an Encoder Plugin:** This is where the magic happens. You will add a plugin to this track to encode the mono signal into the 4-channel B-format. The tutorial highlights a few different encoders within the Ambisonic Toolkit, each with its own character:

    *   **ATK FOA Encode Planewave:** This is a common and straightforward encoder. It places your sound source at a specific direction (azimuth and elevation) in the soundfield. It's ideal for sounds that are meant to be perceived as coming from a distant, fixed point.
    *   **ATK FOA Encode Omni:** This encoder places the sound so that it appears to be coming from all directions at once, creating a sense of being enveloped by the sound.
    *   **ATK FOA Encode Spreader:** This encoder spreads the sound source across a range of directions, which can be useful for creating a sense of size or space. It achieves this by encoding different frequency bands in different directions.
    *   **ATK FOA Encode Diffuser:** This encoder also spreads the sound but in a more random and diffuse manner, which can be great for creating atmospheric textures.

By experimenting with these different encoders and the transform plugins, you can begin to craft rich and immersive soundscapes. The Ambisonic Toolkit for Reaper is a fantastic and accessible way to explore the creative possibilities of Ambisonic audio.