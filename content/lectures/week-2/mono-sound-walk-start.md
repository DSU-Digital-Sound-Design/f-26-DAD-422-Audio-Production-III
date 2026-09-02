---
title: "Starting the Mono Sound Walk"
summary: "Plan the walk, begin the REAPER session, and test one moment in mono."
tags: [mono, soundscape, reaper, project lab]
---

Today is about getting [Project 1: Mono Sound Walk](/projects/mono/) out of your
head and into a working REAPER session. We will work on headphones in our regular
classroom. The project is mono, so we do not need the immersive room yet.

By the end of class, each person should have:

- a one-sentence concept and a clear listener path
- a rough timeline for a 1–2 minute piece
- a list of at least 10 sound elements
- a saved, organized REAPER session
- a short proof of concept that suggests depth or movement in mono

## 1. Pitch the walk

Take two minutes to explain your project:

1. Name the environment.
2. Describe where the listener begins and ends.
3. Identify one event or change that gives the walk a shape.
4. Name the sound that will make the place immediately recognizable.

After each pitch, the other three people ask one practical question or suggest
one sound that could make the journey clearer.

If the concept is still broad, finish this sentence:

> The listener moves from __________ to __________ while __________ changes.

## 2. Draw a sound map

Sketch a horizontal timeline from `0:00` to the end of the piece. Mark the
listener's route first, then place at least 10 sounds along it. For each sound,
note:

- when it enters and exits
- where it seems to be in relation to the listener
- whether it stays still, approaches, recedes, passes, or changes in another way

Choose the first three sounds you need: one for the opening, one for the main
change in the walk, and one for the ending.

Before sourcing anything, check the shape of the piece:

- Does the listener have somewhere to go?
- Does anything change between the beginning and end?
- Can the journey be understood without an image or explanation?

## 3. Find the first three sounds

Start with those three sounds rather than collecting all 10 at once. Use your
own recordings, [Freesound](https://freesound.org/), or
[SoundQ](https://www.prosoundeffects.com/soundq/).

For each file:

1. Preview enough of the recording to find a usable section. After downloading,
   listen through the file and check for noise, clipping, unwanted voices, and
   an abrupt ending.
2. Choose a mono file when one is available. If the source is stereo, downmix or
   render it to mono before building the piece.
3. Rename it by what it contains, such as `door_metal_close_01.wav`, rather than
   leaving a download number as the filename.
4. Save the source or license information when the library requires credit.

## 4. Build the REAPER session

1. Create REAPER track folders based on the sections or locations in your walk.
2. Put each sound on its own clearly named track and keep every track centered.
3. Confirm that every item plays in mono. `Item settings > Take channel mode >
   Mono (downmix)` will collapse a stereo item when needed.
4. Put `JS: Utility/mono` on the master as a safety check. Do not use panning to
   create the movement.
5. Save a new version before experimenting: `lastname_soundwalk_v01.rpp`.

## 5. Make a short distance test

Choose one clear sound and build a 15–20 second test in which it approaches or
recedes. This is an experiment, not a finished section.

Use three cues:

- **Level:** farther sounds are usually quieter.
- **Filtering:** reduce high frequencies as the sound moves away or behind an
  obstruction.
- **Direct-to-reverberant balance:** use more dry signal nearby and more room
  sound at a distance.

Try these as rough starting points, then adjust by ear:

| Position | Track level | Low-pass filter | Reverb |
| --- | ---: | ---: | --- |
| Near | 0 dB | 10–12 kHz | Mostly dry |
| Middle | −6 dB | 5–7 kHz | Moderate |
| Far | −12 dB | 3–4 kHz | More wet signal |

Automate smooth changes rather than jumping between three fixed settings. Solo
the master in mono and ask whether the distance is still clear with your eyes
closed.

## 6. Four-person playback

Each person plays the concept test once without explaining it. The other three
listeners answer:

1. Where did the sound seem to begin and end?
2. Which cue made the movement readable?
3. What single change would make the illusion clearer?

The person presenting writes down the responses without defending the mix. Make
one revision while the feedback is still fresh.

## Before you leave

- [ ] Concept and listener path are written down.
- [ ] Timeline contains at least 10 planned sounds.
- [ ] The opening, main change, and ending sounds are in the project folder.
- [ ] REAPER session is saved and plays in mono.
- [ ] The distance test has been played for the group.
- [ ] The next three concrete tasks are written at the top of your notes.

Project 1 is due Monday, September 14, at the start of class. The next class on
Wednesday, September 9, covers distance perception in more detail, so bring this
session and any problems you discover today.
