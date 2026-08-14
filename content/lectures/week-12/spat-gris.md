---
title: "SpatGRIS"
---

[SpatGRIS](http://gris.musique.umontreal.ca/) is a free, open-source system for spatializing sound over multichannel speaker arrays. This lecture uses SpatGRIS4 and the ControlGRIS2 plug-in.

The two applications divide the work:

- SpatGRIS receives audio, spatializes it for the selected speaker setup, and sends the result to the audio interface.
- ControlGRIS2 runs in the DAW and sends source positions and trajectories to SpatGRIS through Open Sound Control (OSC).

On the lab Macs, BlackHole carries audio between the DAW and SpatGRIS. It does not carry the panning data.

```text
Audio: DAW -> BlackHole -> SpatGRIS -> audio interface -> speakers
Control: ControlGRIS2 -> OSC -> SpatGRIS
```

Because control and audio follow separate paths, SpatGRIS can also receive position data from Max, Open Stage Control, or another device that sends OSC.

## Set up the speakers

Create or load a speaker setup in SpatGRIS before routing audio from the DAW.

1. Select BlackHole as the input device and the room's audio interface as the output device.
2. Open the speaker setup editor and place each virtual speaker in the position of its physical counterpart.
3. Use the reference pink-noise generator to test the array.
4. Solo each speaker and confirm that its label, output channel, and physical location agree.
5. Save the speaker setup for later sessions.

Do not begin spatializing until every output passes this test. A wrong channel assignment can make a correct trajectory sound wrong.

## Reaper setup

These steps assume that Reaper is using BlackHole as its output device.

1. Create a stereo track and add an audio file.
2. Disable the track's master/parent send. Otherwise, the track may reach an unintended output or be monitored twice.
3. Add a hardware output to BlackHole channels 1/2.
4. Insert ControlGRIS2 on the track.
5. Set the first source ID to 1 and configure the plug-in for the two channels in the track.
6. Start playback and confirm that SpatGRIS receives audio on inputs 1 and 2.

The source IDs in ControlGRIS2 must match the BlackHole channels carrying the audio. For a second stereo track, use BlackHole channels 3/4 and begin with source ID 3. Do not reuse source IDs unless you intend two tracks to control the same sources.

## Source links

The source-link controls determine how the channels in a stereo or multichannel source move in relation to one another. Try the available link modes and watch both source markers in SpatGRIS. Listen for changes in image width, orientation, and motion before choosing a mode.

## Trajectories

ControlGRIS2 can generate repeatable motion without drawing every position by hand.

1. Choose a trajectory type and activate it.
2. Adjust the cycle duration or speed.
3. Turn on Back & Forth when the source should reverse direction at the end of each cycle.
4. Change Deviation Degrees per Cycle to vary the path on successive cycles.
5. Compare the preset paths with a trajectory you draw yourself.

If you need an exact, editable performance, write the ControlGRIS2 position parameters as Reaper automation. Then return the track to automation read mode and play it back to confirm that the movement was captured.

## Multichannel sources

A multichannel file uses the same idea with more routing. Increase the track's channel count, route each channel to a corresponding BlackHole output, and assign the same range of source IDs in ControlGRIS2. Check the input meters in SpatGRIS before working on movement.

Keep a simple channel map in your notes. Once a session contains several sources, duplicate or skipped IDs become difficult to diagnose by ear.

## External control

SpatGRIS can receive OSC from software other than ControlGRIS2. Max can generate positions, map a controller to source movement, or build behaviors that respond to analysis data. Open Stage Control can provide a touch interface from a phone or tablet.

The audio routing does not change when you use an external controller. Only the source of the OSC messages changes.

## Record the result

Use the recorder in SpatGRIS to capture the spatialized output. You can record separate mono files or one interleaved multichannel file.

Use mono files when you need to inspect or process speaker feeds separately. Use an interleaved file when the destination expects one multichannel asset. In either case, document the channel order and verify the recording before dismantling the session.

## The same idea at concert scale

SpatGRIS is a research system, but its basic workflow also appears in commercial spatial-audio systems: define the speaker layout, treat inputs as movable sources, and control their positions over time.

- [L-ISA](https://www.l-acoustics.com/spatial-systems/) uses object controls such as pan, width, distance, and elevation in systems built around L-Acoustics hardware.
- [d&b Soundscape](https://www.dbaudio.com/global/en/solutions/soundscape/) combines the DS100 signal engine with En-Scene for object positioning and En-Space for room emulation.
- [Spacemap Go](https://meyersound.com/product/spacemap-go/) uses an iPad interface to control spatial panning on Meyer Sound GALAXY processors.
- [4DSOUND](https://4dsound.net/) combines proprietary spatial software with custom arrays of omnidirectional loudspeakers for performance, installation, and research spaces.

The products differ, but the habits developed here transfer: plan the array, keep the audio and control paths organized, test every output, and rehearse movement as part of the mix.

## Project idea

Combine work from the Topics course with this course by building a web interface for SpatGRIS. A browser cannot send OSC over UDP by itself, so the project would also need a small bridge that translates browser messages into OSC.

Begin with X/Y control for one source. Then add source selection, trajectory controls, or parameters derived from sound analysis.

## References

- [GRIS software and documentation](https://gris.musique.umontreal.ca/)
- [SpatGRIS4 downloads and current manual](https://sourceforge.net/projects/spatgris4/files/)
