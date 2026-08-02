+++
title = "Spatial audio psychoacoustics"
outputs = ["Reveal"]
[reveal_hugo]
theme = "moon"
margin = 0.2
+++

# Spatial audio psychoacoustics

{{% note %}}
- Learn about the perception and cognition of spatial sound.
- Focus on psychoacoustic phenomena relevant to audio systems design and implementation.
{{%/ note %}}

---

## Sound source localization

![](Big-Ears-3387165105.jpg)

{{% note %}}
- How do we perceive the direction of a sound?
- Main cues:
    - ITD (Interaural Time Differences): Phase/timing differences between the ears.
    - IAD (Interaural Amplitude Differences): Amplitude or spectral differences between the ears.
- Spatial perception relies on two ears discerning differences in signals.
{{%/ note %}}

---

## Interaural Time Differences (ITD)

<img src="ITD.png" width=75%>

{{% note %}}
- ITD: Time difference between ears for non-central sound sources.
    - Related to the angle of sound incidence.
- **Binaural delay**: Max delay between ears is 650 μs (0.65 ms).
- Humans can resolve direction with ITD down to a few degrees.
    - ITD is ineffective for front/rear distinction or elevation.

This diagram illustrates the concept of **Interaural Time Difference (ITD)**, which helps explain how humans localize sound based on the time delay between sound arriving at each ear.

### Key Points for Notes:

- **Interaural Time Difference (ITD)**: 
  - ITD occurs because sound waves from a source arrive at each ear at slightly different times, depending on the direction the sound is coming from.
  - The farther ear will experience a delay as the sound has to travel a longer distance.

- **Distance and Angle**:
  - The figure shows that the sound source is positioned at an angle, indicated by the angle \( \theta \) (theta), relative to the front-center of the listener.
  - As the sound source moves from directly in front of the listener, the difference in path length between the two ears increases.

- **ITD Formula**:
  - The formula for ITD in this model is:
    \[
    ITD = \frac{r(\theta + \sin\theta)}{c}
    \]
    - \( r \) is the radius of the head (distance between the ears).
    - \( \theta \) is the angle of incidence of the sound wave (in radians).
    - \( c \) is the speed of sound in air (approximately 340 m/s).
  - This formula calculates the additional time delay for sound to reach the far ear (left ear in the diagram).

- **Explanation of Path**:
  - The two lines represent the paths of the sound waves traveling to the listener's ears. The path to the left ear is longer than the path to the right ear because of the angle \( \theta \).

- **Physical Explanation**:
  - Sound from the source must travel around the head, leading to the time delay calculated using the head's geometry.
  - As \( \theta \) increases (i.e., the sound source is farther from the front), the ITD increases, enhancing our ability to detect sound direction.

{{%/ note %}}

---

Try the [Interaural Time Differences](https://isle.hanover.edu/isle2/Ch11AudBrainLoc/Ch11InterTime.html) example

---

### ILD - Amplitude and spectral cues

![](cone.jpg)

{{% note %}}
- ILD: The second method of spatial perception.
    - High frequencies blocked by the head, low frequencies pass through.
- Pinna shape changes the sound spectrum at the eardrum based on the angle of incidence.
- Rear sources have reduced high-frequency response due to the pinna’s shape.
{{%/ note %}}

---

## Listening Experiment

[Interaural Level Differences](https://isle.hanover.edu/Ch11AudBrainLoc/Ch11InterLoud.html)

---

## Animals with no pinna? Dolphins! 

<iframe width="560" height="315" src="https://www.youtube.com/embed/CE5tZKFVlto?si=jprSzq9LwWtGa7UX" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

## Experiment 2 

> Find a sound with steady high frequencies (motor, fan, etc.). Move your head and note how high frequencies change.

<audio src="HighHum.wav" controls>

{{% note %}}

### 1. **Interaural Level Differences (ILD)**
   - **Explanation**: ILD refers to the difference in sound intensity between the two ears. The head blocks or attenuates high-frequency sounds, making them quieter in the ear farther from the sound source.
   - **Effect when turning head**:
     - As you turn your head toward the fan, the sound becomes louder in the ear closest to the fan.
     - When you turn your head away, the fan sound is quieter in the farther ear due to the **head-shadow effect**, helping you localize the fan.

### 2. **Interaural Time Differences (ITD)**
   - **Explanation**: ITD is the difference in the time it takes for sound to reach each ear, depending on the direction of the sound relative to the head.
   - **Effect when turning head**:
     - Facing the fan directly results in nearly simultaneous arrival of sound at both ears.
     - Turning your head introduces a time delay, where the sound reaches the ear closer to the fan slightly earlier than the farther ear, helping your brain localize the sound source.

### 3. **Pinna Filtering and Spectral Cues**
   - **Explanation**: The shape of the pinna (outer ear) alters incoming sound waves, especially higher frequencies, depending on the sound's direction.
   - **Effect when turning head**:
     - As you turn your head, the pinnae modify the sound, especially at high frequencies, giving subtle cues about the sound’s direction and angle.
     - You may notice slight changes in the timbre or brightness of the fan sound due to the pinna filtering high-frequency content differently based on your head’s orientation.

### 4. **Head-Related Transfer Function (HRTF)**
   - **Explanation**: HRTF combines ILD, ITD, and pinna filtering to help your brain process the 3D location of sounds.
   - **Effect when turning head**:
     - As you move your head, your personal HRTF dynamically adjusts, allowing your brain to continuously update its perception of the fan’s location in three-dimensional space.
     - This helps you accurately identify the direction and position of the fan in the auditory environment.
{{%/ note %}}

---

- Low frequencies: localized by ITD (Interaural Time Differences).
- High frequencies: localized by IAD (Interaural Amplitude Differences).

---

- ITD-only localization (audio): 
  - <audio src="IPO73-BinauralArrivalTime.wav" controls>
- Smaller steps with percussive sounds:
  - <audio src="Binaural_demo.wav" controls>
- Interaural phase differences for 500 Hz and 2 kHz tones:
  - <audio src="IPO72-BInauralPhase.wav" controls>

{{% note %}}
- Lower frequencies: Phase differences are time differences.
- For 500 Hz, phase switches create a spatial shift.
- For 2 kHz, phase shifts are too small and ambiguous to discern spatially.

Check out in reaper to show the time and phase differences.
{{%/ note %}}

---

![](man-listening-with-big-ears-picture-id487047931-767487051.jpg)

{{% note %}}
- Human pinnae vary widely in shape, much like fingerprints.
Here’s a more detailed explanation of **HRTF (Head-Related Transfer Function)**:

### **HRTF (Head-Related Transfer Function)**:
   - **Definition**: HRTF describes how sound is filtered and transformed by the unique shape of a listener's head, ears (pinnae), and even the torso before reaching the ear canal. It essentially captures how these body parts affect the sound waves based on their direction and location relative to the listener.
   
   - **Key Factors**:
     - **Head**: The size and shape of the head create **shadows** that block or reflect high-frequency sounds, which leads to **Interaural Level Differences (ILD)**.
     - **Ears (Pinnae)**: The shape of the outer ear modifies incoming sound waves, especially high frequencies, depending on their direction, contributing to the unique **spectral cues** for localization.
     - **Torso and Shoulders**: These parts of the body also contribute to sound diffraction and filtering, especially for lower frequencies, adding further depth to sound localization.
   
   - **Simulating Spatial Cues**:
     - HRTFs are used in virtual audio systems (like binaural audio or 3D sound) to simulate realistic spatial cues. By applying an HRTF to audio, the system can mimic how sounds would be perceived from different directions and distances.
   
   - **Individual Variability**:
     - Since everyone has a unique head shape, ear structure, and torso size, HRTFs vary from person to person. This means that the same HRTF may not work perfectly for everyone.
     - **Custom HRTFs** are sometimes created for individuals to ensure accurate spatial sound reproduction, particularly in high-end audio systems or virtual reality.

### Key Point:
- **HRTF** encapsulates how physical characteristics (head, ears, torso) transform sound, helping the brain perceive direction, distance, and elevation.
{{%/ note %}}

---

![](https://upload.wikimedia.org/wikipedia/commons/4/4a/FreqHRTF.jpg)

{{% note %}}
The graph you've provided shows the **frequency response** of the **HRTF** (Head-Related Transfer Function) for the left and right ears (labeled as XR and XL) at a given **azimuth** and **elevation**. It provides insight into how sound is altered for each ear at different frequencies due to the unique physical shape of the listener's head, ears, and torso.

### Key Points to Understand the Graph:

1. **Frequency Response**:
   - The **x-axis** represents the **frequency** in Hertz (Hz), while the **y-axis** represents the **magnitude response** in decibels (dB).
   - The frequency range in the plot goes from approximately 200 Hz to 20,000 Hz (2 × 10^4 Hz), which covers the human hearing range.

2. **Asymmetry Between Ears**:
   - **XR (right ear)** and **XL (left ear)** show distinct frequency response curves.
   - This asymmetry is common because of the head’s effect on sound, particularly the **head-shadow effect**, which causes sound to be attenuated differently for each ear depending on the direction of the sound source.
   - Differences in magnitude between the ears, especially in high-frequency regions, are critical for **Interaural Level Differences (ILD)**, which help localize sounds horizontally.

3. **Peaks and Dips in the Response**:
   - The peaks in the frequency response represent **resonances**, where certain frequencies are amplified due to the shape of the pinna and ear canal.
   - Dips, or **nulls**, correspond to frequencies that are attenuated due to destructive interference from sound reflections off the head, shoulders, or other body parts.
   - These peaks and dips provide **spectral cues** that your brain uses to determine the **elevation** and **azimuth** (direction) of the sound.

4. **HRTF Variability**:
   - The difference between the left and right ear responses illustrates how HRTFs vary depending on the **listener’s head orientation** relative to the sound source. 
   - Factors such as head size, ear shape, and the direction of the sound all cause these variations.

### How HRTFs Vary:
- **Head Size and Shape**: Larger heads create more significant ILD at higher frequencies due to increased sound shadowing.
- **Pinna Shape**: The shape and size of the pinna cause different reflections and resonances, altering the frequency response.
- **Ear Canal Length**: Variations in the length of the ear canal affect the resonances, especially in higher frequencies.
- **Torso and Shoulders**: Sounds reflected off the torso and shoulders contribute to changes in sound wave interaction at lower frequencies, especially for vertical localization.
  
### Interpreting the Graph:
- **Low Frequencies (below ~1 kHz)**: The response between the left and right ears is fairly similar, indicating that **ITD (Interaural Time Differences)** dominate in this range for localization.
- **High Frequencies (above ~1 kHz)**: Noticeable differences in magnitude between the two ears, reflecting the role of **ILD (Interaural Level Differences)**. This is especially pronounced in the range from 3 kHz to 8 kHz, where the pinnae and head-shadowing effects are strongest.

{{%/ note %}}

---

#### Listening Experiment - Different HRTFs

- <audio src="HRTF/IRC_1002_P345.wav" controls>
- <audio src="HRTF/IRC_1003_P345.wav" controls>
- <audio src="HRTF/IRC_1004_P345.wav" controls>
- <audio src="HRTF/IRC_1006_P345.wav" controls>
- <audio src="HRTF/IRC_1008_P345.wav" controls>
- <audio src="HRTF/IRC_1012_P345.wav" controls>

source: http://recherche.ircam.fr/equipes/salles/listen/sounds.html

{{% note %}}
### Purpose of the Demo:
- The demo allows listeners to experience how different **HRTFs** (Head-Related Transfer Functions) affect spatial sound perception. 
- Since HRTFs vary based on a listener's anatomy (head, ear shape, etc.), users can try different audio files to find the one that best matches their own **physiological and auditory characteristics**.

### Sound Movement:
- As you listen through headphones, the sound should appear to move around your head, simulating spatial cues provided by the HRTF.
- Each sound file corresponds to a different HRTF, offering a unique experience of how sound is perceived when it moves in a horizontal plane around the listener.
{{%/ note %}}

---

[PHRTF - Dolby Professional](https://professional.dolby.com/phrtf)

{{% note %}}
**PHRTF** stands for **Personalized Head-Related Transfer Function**. It refers to an HRTF that is tailored specifically to an individual listener, rather than using a generic or standardized HRTF. The goal of PHRTF is to improve the accuracy of spatial audio perception by accounting for the unique physical characteristics of each person's head, ears, and torso.

### Key Points about PHRTF:

1. **Individual Customization**:
   - PHRTF is generated using measurements of a listener’s specific anatomy, such as the shape and size of their head, ears (pinnae), and even shoulders or torso. This customization allows for more precise simulation of how sound waves are altered before reaching the listener's ear canals.

2. **Improved Spatial Perception**:
   - Using a generic HRTF can work for many listeners but may not provide an optimal experience for everyone, as individual differences in anatomy can result in less accurate spatial cues. A **PHRTF** offers improved spatial localization and externalization (perceiving sounds outside the head) by more accurately representing the listener’s unique hearing profile.

3. **Applications**:
   - **Virtual Reality (VR) and Augmented Reality (AR)**: PHRTFs are used in immersive audio systems where precise spatialization is critical for a more realistic and engaging experience.
   - **Gaming**: Personalized HRTFs can make audio environments more immersive and help players localize sounds more accurately (e.g., footsteps, distant noises).
   - **Hearing Aids and Assistive Devices**: Personalized audio filtering can be used to enhance the user's ability to localize sound sources in real-world environments.
   
4. **How PHRTFs Are Generated**:
   - **Measurement Techniques**: PHRTFs are often measured in a specialized sound environment, where microphones are placed in the ear canal, and sound is played from various angles to capture how the sound is modified by the listener’s body.
   - **Photo-Based or Scanning Methods**: Some technologies generate PHRTFs by taking 3D scans or photos of a person’s ears and head, using algorithms to simulate how sounds would be altered.

5. **Challenges**:
   - Creating a **PHRTF** can be time-consuming or require specialized equipment, making it less accessible for everyday users.
   - However, with advancements in technology, there are ongoing efforts to make PHRTF more widely available through faster, more affordable methods.

{{%/ note %}}

---

![](precedence.png)

{{% note %}}

#### **(a) Binaural Delay**:
- A **single sound source** emits sound that reaches the ears at slightly different times.
- **Binaural delay** (denoted as δt) occurs due to the extra distance sound travels to reach the farther ear.
- The brain uses this **time difference** to localize sound direction.
- Relevant for **headphone listening** and **natural environments** where the sound source is continuous and singular.

#### **(b) Precedence Effect**:
- Involves **two sound sources** emitting the same signal but with a slight delay.
- The brain prioritizes the **first-arriving sound** (from the earlier source).
- Creates a **phantom image** perceived towards the earlier sound source.
- Important for **loudspeaker setups**, where sound localization depends on both timing and amplitude cues.
  
#### **Key Concepts**:
- **Binaural delay** is most effective for localization in natural settings.
- The **precedence effect** helps the brain focus on the most important sound in complex environments, such as multiple speakers.

{{%/ note %}}

---

### Cocktail party effect

- Same voice with mixed texts (mono vs. stereo):
  - <audio src="Cocktail_Party_Effect.wav" controls>
- Two texts, one at a time, then mixed:
  - <audio src="Duda13-CocktailPartyEffect.wav" controls>

{{% note %}}
- Cocktail party effect: Ability to focus on a specific source amid noise.
- Primary cue: Location and direction of sound sources.
- Sounds from the same direction are assumed to come from the same source.
{{%/ note %}}

---

![](th-1700196290.jpg)

{{% note %}}
- Spatial cues may be influenced by other senses, especially vision.
- Learned experiences influence spatial expectations.
- Example: Planes are expected to fly overhead; playing recordings may cause confusion if heard below.
{{%/ note %}}

---


### Apparent source width

![](ASW.png)

{{% note %}}
- **Apparent Source Width (ASW)**: Describes how large a sound source appears from a sonic perspective.
- Related to **spaciousness**: Sense of the space a sound source occupies.
- Larger ASW is preferred in concert halls, but the optimum width remains unclear.
- May relate to "image blur."
{{%/ note %}}

---

- **Spaciousness**:
  - Refers to the **perceived size** or openness of an acoustic space.
  - Creates the sensation of sound filling a large environment.
  - Important for a sense of **naturalness** and **externalization** of sound.
- **Envelopment**:
  - Describes the extent to which the listener feels **surrounded by sound**.
  - Key to creating **immersive** and **reverberant soundfields**.
  - High envelopment occurs when sound reaches the listener from multiple directions.

{{% note %}} 
- **Spaciousness**: Describes the perceived size of the acoustic space.
- **Envelopment**: The degree to which the listener feels surrounded by sound.
    - Both are key to immersion in reverberant soundfields (e.g., concert halls).
{{%/ note %}}

---

# Naturalness

{{% note %}}
- One of the goals of spatial sound reproduction.
- No precise definition.

- **Definition**: 
  - Refers to how **realistic** and **believable** the spatial audio sounds.
  - The listener perceives sound as coming from natural sources in a lifelike space.

- **Key Factors for Achieving Naturalness**:
  - **Accurate spatial cues**: Correct positioning, distance, and movement of sounds in 3D space.
  - **HRTF (Head-Related Transfer Function)**: Customized or well-matched HRTFs enhance realism.
  - **Timbral consistency**: The tone and quality of sound must remain authentic as the source moves.
  - **Proper reverberation**: Reflects the size and characteristics of the acoustic environment.

- **Challenges**:
  - Personal differences in how listeners perceive spatial sound due to varying anatomy (e.g., head shape, ear structure).
  - **Virtual environments** may struggle to perfectly simulate all nuances of natural listening.


{{%/ note %}}

---

### Subjective attributes of spatial impression

![](spatial-impression.png)

{{% note %}}

### **Spatial Impression**
- This is the overall perception of space and sound, influenced by two main factors: **Source** and **Environment**.


### **Source**:
- Refers to the sound origin and how it contributes to the spatial impression.
  
  1. **Position**:
     - **Azimuth**: The horizontal angle of the sound source (left-right).
     - **Distance**: How far the sound source is from the listener.
     - **Elevation**: The vertical angle of the sound source (up-down).

  2. **Dimensions**:
     - **Width**: The perceived width of the sound source.
     - **Depth**: The perceived depth of the sound source, creating a sense of distance.
     - **Height**: The vertical size or height of the sound.

  3. **Focus/Diffuseness**:
     - How clear or diffuse the sound source appears, which impacts the perception of spatial clarity and spread.
     - **Width, Depth, Height**: The perceived clarity or diffusion of the sound in these dimensions.


### **Environment**:
- Refers to the acoustic space or environment in which the sound occurs.

  1. **Envelopment**:
     - The extent to which the listener feels surrounded by sound, contributing to immersion.

  2. **Dimensions**:
     - **Width**: The perceived spatial width of the environment.
     - **Depth**: The perceived depth of the environment.
     - **Height**: The perceived height of the environment.

### **Perceived Dimensions**:
- The combination of source and environmental factors results in the listener’s **perception** of the following dimensions:
  - **Width**: The perceived spread of sound horizontally.
  - **Depth**: The perceived distance and depth of the sound.
  - **Height**: The vertical extent of the sound.

{{%/ note %}}
