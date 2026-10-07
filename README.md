# The Archivist

<p align="left">
  <img src="https://github.com/user-attachments/assets/9be852bd-a7af-4edb-b8d2-a0f4d680d7b6" width="700">
</p>


A [Detuned Transmissions (DTND)](https://detunedtransmissions.com/) firmware for the [Noise Engineering Versio](https://noiseengineering.us/pages/world-of-versio/).

> *Recollection* is a re-presentation, the elapsed object reproduced and posited as having been, at will and repeatably. *Retention* exists as an axis of strata with the just-elapsed object held in the active present within the context of previously perceived experience. Each successive stratum retains those before it, the elapsed receding through a continuum towards an indistinct horizon. 

As an agent of retention and recollection, **The Archivist** is a compact performance processor for capturing and manipulating sound in 10hp. It offers two modes of sonic manipulation from distinct eras: **TAPE** emulates early tape splicing procedures, while **GRAINS** affords modern microsound exploration.

Each mode has a specialised sampling engine constructed from tuned misuse of various technologies from its era, resulting in unique aesthetic colouration across memory recall. **TAPE** recreates analogue properties of reel-to-reel and cassette media, with the afforded manipulations—emulating various recording (EQ, saturation, noise), playback (wow/flutter, head tracking errors), splicing (looping) and effects processing (tape echo, pitch modulation); **GRAINS** is inspired by 1980s/1990s digital codecs for decimation, bit reduction, and efficient storage (DPCM with residual *μ*-law companding and slope overload), with parameterisation over a granular engine and storage qualities. Both modes encourage a departure from the present by navigating retention strata to excavate old memories, which find expression through degradation that antiquated mediums impart. 

---

## CONTENTS

* [Install](#install)
* [Operation](#operation)
* [Modes](#modes): [TAPE](#mode-1-tape-sw1lc) · [GRAINS](#mode-2-grains-sw1r)
* [Retention and Strata](#retention-and-strata)
* [Settings](#settings)
* [Examples](#examples)
* [Disclaimer](#disclaimer)

---

## MANUAL

*Video manual to follow; hardware panel imminent...*

## INSTALL

1. Download `the-archivist.bin` from the repository.
2. Put Versio into DFU mode (see the NE Versio firmware wizard for instructions).
3. Load the `.bin` using either the NE Versio firmware wizard on the [NE Versio page](https://noiseengineering.us/pages/world-of-versio/) or the [Electrosmith Daisy Bootloader page](https://flash.daisy.audio/).

## OPERATION

### SWITCHES
SW0 = Switch 0 (top); SW1 = Switch 1 (bottom)

| SWITCH | SETTING | MODE/CTRL | DESCRIPTION |
|---|---|---|---|
| **SW1** | L/C | TAPE | Tape engine.|
| **SW1** | R | GRAINS | Granular engine.|
| **SW0** | L/C | Main controls | Main controls for either mode.|
| **SW0** | R | Alt controls | Alternative controls for either mode.|

Parameter values are stored upon toggling **SW0** control pages and recalled on passthrough.

### FSU BUTTON

| GESTURE | DESCRIPTION |
|---|---|
| **Tap** | Capture. |
| **Hold 3 sec, SW0=C** | Enter/exit **SETTINGS** page.|
| **Hold 3 sec, SW0=L or R** | Clears retention in **TAPE** or **GRAINS**.|

**FSU Button** operation is equivalent in both modes. Captures are cleared upon mode switch or entering **SETTINGS**.

### KNOBS
Knob parameterisation differs per mode and pages. Please see knob layout descriptions in the relevant sections. 

## MODES

### MODE 1: TAPE (SW1=L/C)

<p align="left">
<img src="https://github.com/user-attachments/assets/89b91d4d-5a92-48a9-b947-af8f8b8c842b" width="700">
</p>

*Figure:* Eltro Mark II Information Rate Changer (circa 1960) tape machine provided independent manipulation of pitch and time through a rotating 4-head drum. See [Eltro decription by Wendy Carlos for more information](https://www.wendycarlos.com/other/Eltro-1967/).

#### Main Controls (SW0=L/C)

| KNOB | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K0** | PITCH | Pitch. | Full CCW=−24 semitones (0v), unison at 0.4 (2v), full CW=+12 semitones (3v). Refer to [K0 Zones](#k0-zones) below) for regions above 3v.|
| **K1** | DRIVE | Record drive into the tape. | CCW=clean, CW=hot.|
| **K2** | RETENTION | Decimation, metrical duration and cassette type. See [Retention and Strata](#retention-and-strata). | Discrete or continuous, per **SETTINGS K0**.|
| **K3** | ECHO | Tape echo (print-through) over the K4 loop duration. | CCW=off, CW=full effect.|
| **K4** | LENGTH | Tape loop duration. | CCW=short, CW=long.|
| **K5** | SPEED | Speed and direction of playback. | 
| **K6** | K-FIELD DEPTH | Modulation depth. | CCW=off, CW=full effect.|

#### Alt Controls (SW0=R)

| KNOB | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K4** | SPLICE ANGLE | Tape splice angle. | CCW=20ms; CW=500ms.|
| **K5** | HEAD SPLICING | drum head splices to tape loop length. | 1, 2, 4, 8, 16, 32. Centre=8.|
| **K6** | K-FIELD RATE | Modulation rate. | CCW=slow, CW=fast.|


#### TAPE LEDs

Numbered **0** to **3**, left to right.

| LED | DESCRIPTION |
|---|---|
| **LED0** | Retention stratum, as above.|
| **LED1** | Pitch. 🟢 Unison=Green; ⚪ Octaves=White; 🟠 +5th=Orange; 🔵 −5th=Dark blue; Otherwise dims toward unison.|
| **LED2** | Speed and direction; slice count on SW0=R.|
| **LED3** | Capture. 🔵 Blue when engaged.|

---

### MODE 2: GRAINS (SW1=R)

<p align="left">
<img src="https://github.com/user-attachments/assets/4c8648b5-247e-4b5d-97b9-dd3d2ba2a4b4" width="700">
</p>

*Figure:* The E-mu Emulator II (1985) with a DPCM sampling engine with residual *μ*-law 8-bit companding and slope overload.

#### Main Controls (SW0=L/C)

| KNOB | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K0** | PITCH | Grain pitch (see below). | Full CCW=−24 semitones (0v), unison at 0.4 (2v), full CW=+12 semitones (3v). Refer to [K0 Zones](#k0-zones) below) for regions above 3v.|
| **K1** | WINDOW | Grain envelope shape. | Centre=a plateau of pure Hann. CCW morphs to an exponential decay; CW morphs to its reverse, a swell.|
| **K2** | RETENTION | Capture decimation and metrical duration (see [Retention and Strata](#retention-and-strata) below). | Discrete or continuous, per **SETTINGS K0**.|
| **K3** | DENSITY | Grain overlap (see below). | Centre=maximum overlap; full CCW=minimum isochronous; full CW=minimum random.|
| **K4** | LENGTH | Grain length. | full CCW=50ms,full CW=2s |
| **K5** | SPEED | Speed and direction of playback. | Continuous; centre=0x, full CCW=−2x, full CW=+2x (detents at ±0.5x, ±1x and ±2x).|
| **K6** | SPRAY | Gaussian scatter of grain read positions. | CCW=none (grains follow read head), CW=random position.|

#### Alt Controls (SW0=R)

| KNOB | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K0** | DETUNE | Per-grain pitch deviation. | Centre=off. CCW=continuous spread up to ±12 semitones; CW=discrete interval sets.|
| **K1** | REVERSE | Proportion of grains played backwards. | CCW=all forward, CW=all reverse.|
| **K2** | GLIDE | How fast speed and spacing changes are followed. | CCW=20 ms, CW=1 s.|
| **K3** | SWING / HUMANISE | Grain timing. | CCW of centre=swing; CW of centre=random lateness.|
| **K4** | DISSOLVE | Read point smoothing on write head overtake. | CCW=immediate; CW=full smoothing.|
| **K6** | SPACE | Schroeder allpass diffusion with tank reverb. | CCW to centre=dry to full diffusion; centre to CW=diffusion held full, tank decay 1-9 s.|

*NB: Due to the laws of reality, if you play back audio at **K5**<1x the output reflects material at an increasingly greater delay from the input. Playing back >1x reuses audio in the buffer. Don't be angry about this, we can't control time yet.*

#### **K3**: DENSITY 
* Sets the number and distribution of overlapping grains.
* Maximum density is generated at the centre position. At **K0**=unison, **K5**=1x, and **K6**=0, maximum density is 5, and is increased automatically for cloud coverage, presence of pitch intervals, and **K6**>0.
* Turning either way decreases the number of grains continuously. LED2 blinks slowly at centre (maximum density).
* Anticlockwise settings generate grains at even amplitude and synchronous spacing.
* Clockwise settings generate grains at random amplitudes and asynchronous spacing.
* LED2 blinks at double rate where grains no longer overlap sufficiently to sum smoothly. This point varies with pitch and speed settings.
* At either extreme setting, one grain is generated per four grain lengths.
* With trigger or clock signal in **FSU CV INPUT**, **K3** at min or max triggers grains (min = isochronous, max = random).

#### **K6**: SPRAY 
* Sets deviation of grain read positions from the read head.
* The point at which additional density becomes available varies with grain length, pitch and speed.

#### GRAINS LEDs

Numbered **0** to **3**, left to right.

| LED | DESCRIPTION |
|---|---|
| **LED0** | Retention. 8 colours representing strata; continuous blends between colours.|
▎ **LED1** | Pitch. 🟢 Unison=Green; ⚪ Octaves=White; 🟠 +5th=Orange; 🔵 −5th=Dark blue; Otherwise dims toward unison.|
| **LED2** | Speed and direction, plus density flashing (see above).|
| **LED3** | Capture. 🔵 Blue when engaged.|

**LED2** (with **SETTINGS K5**=Speed):

* 🔴 **0x**: Flashing red.
* 🟢 **±1x**: Green.
* ⚪ **±0.5x and ±2x**: White.
* 🔵 🟠 **Otherwise**: Blue forwards, orange reverse.
* **K3** coverage landmarks (see above).

With **SETTINGS K5**=Position, LED2 instead displays a brightness ramp: off at full CCW, brightening through blue to white at full CW. There are no K3 blinks in position mode.

---

## K0 ZONES

**K0** is 1v/oct. Above the pitch control (0-3v) it enters further zones, at the same voltages in both modes. Entering a zone restarts.

| K0 | GRAINS | TAPE |
|---|---|---|
| **0–3v** | PITCH | −24 to +12 semitones.|
| **3–4v** | SHEPARD | Shepard tones [-12,+24] semitones. See [SHEPARD](#shepard) below.|
| **4–5v** | SEQUENCE | See [SEQUENCE](#sequence) below.|

*NB*: Shepard only exists in **GRAINS**. **TAPE** provides pitch from 0-4v.

---

### SHEPARD

* 3 octave layers sound together, gliding endlessly without leaving the register.
* **K5** sets glide speed and direction; at 0x it holds.
* **LK0** between 3–4v sets focus: CCW = low, CW = adds additional brighter layers.
* **RK0** pitch intervals are bypassed.
* **LED1** ramps 🔵 blue to 🔴 red across each octave.

---

### SEQUENCE

* 12 seeded patterns (n=[0,11]), addressed at (4+n/12)v.
* Seed fixes notes and durations. Loop lengths not all set to bar lengths.
* Seeds: **1–3** return to same note, **4–6** end on fifths, **7–9** three-note cells, and **10–12** fractured.
* Patterns vary on repetition and revert; leaving and re-entering restores original.
* Ornaments (e.g., slides, bends, reversed steps).
* Clock signal at **FSU CV INPUT** syncs sequence; unclocked one step unit = 250 ms.
* **LED1** indicates sequence zone as ⚪ grey; notes indicated with dark led.

---

## RETENTION AND STRATA

| CONTROL | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K2** | RETENTION | Selects stratum with increasing decimation and context. | Continuous or discrete, per **SETTINGS K0**. Discrete = 8 strata from full CW (48 kHz, 1 bar) to full CCW (3 kHz, 12 bars).|
| **FSU CV INPUT** | SYNC | Clock source for capture and grain triggers. | Unsynced defaults to 120 BPM.|

| | RATE | CONTEXT | LED0 |
|---|---|---|---|
| **Full CW** | 48 kHz | 1 bar | <img src="https://placehold.co/12x12/FF0000/FF0000.png"> red |
| | 24 kHz | 2 bars | <img src="https://placehold.co/12x12/00D9FF/00D9FF.png"> cyan |
| | 16 kHz | 3 bars | <img src="https://placehold.co/12x12/FF5900/FF5900.png"> orange |
| | 12 kHz | 4 bars | <img src="https://placehold.co/12x12/2633FF/2633FF.png"> blue |
| | 8 kHz | 6 bars | <img src="https://placehold.co/12x12/FFCC00/FFCC00.png"> yellow |
| | 6 kHz | 8 bars | <img src="https://placehold.co/12x12/FF00B3/FF00B3.png"> magenta |
| | 4 kHz | 10 bars | <img src="https://placehold.co/12x12/1AFF1A/1AFF1A.png"> green |
| **Full CCW** | 3 kHz | 12 bars | <img src="https://placehold.co/12x12/8000FF/8000FF.png"> violet |

Coarser strata reach further back in time, so at a given speed the same phrase gives additional context.

---

## SETTINGS

Parameters affecting module behaviour. Enter with **FSU-hold (3 sec)** and **SW0=C**, or **FSU** held at boot.

*NB*: Avoid CV input modulation while entering, using or exiting.

### SETTINGS LEDs

Numbered **0** to **3**, left to right.

#### FIRMWARE VERSION ####

On entry to **SETTINGS**, LEDs indicates the firmware version. v1 displays: **LED0** = 🔴 dim red with **LED1–3** off. Subsequent versions will be listed here with a change log when available.

Adjusting any knob overtakes the firmware indicator, and LEDs indicate the following:

| LED | DESCRIPTION |
|---|---|
| **LED0** | Brightness ramps during the FSU commit hold (3 sec).|
| **LED1** | Default value of the chosen parameter.|
| **LED2** | Stored user value of the chosen parameter.|
| **LED3** | Live knob position. Flashes when the knob value matches the stored user value.|

| KNOB | SETTING | DESCRIPTION | DEFAULT | RANGE |
|---|---|---|---|---|
| **K0** | GLOBAL RETENTION MODE | Global **K2** Retention control in both modes. | Continuous | 0 = Continuous (smooth transition between strata); 1 = Discrete.|
| **K1** | GLOBAL STEREO SPREAD | Global: Grains sound across the stereo field; Tape pitch modification expands to stereo. | 0.5 (mono) | 0. = mono; 1. = hard L/R.|
| **K2** | DISINTEGRATION | Whether earned wear travels over time or holds where the dial sets it. | On | 0 = On; 1 = Off.|
| **K3** | TAPE SCAN REFERENCE | Speed target of advance. | K0 | 0 = K0; 1 = 1x (unity).|
| **K4** | TAPE RHYTHM | Rhythm derived by tape splicing at highest stratum is inherited by others. | Bar | 0 = Bar; 1 = Memory (rhythm is mapped to context at lower strata).|
| **K5** | POSITION | Grains **RK5** as position control. | Off | 0 = **RK5** mirrors **LK5** speed control; 1 =  **RK5** as position control (**LK5** remains speed).|
| **K6** | GRAINS SYNC | Sync grain spawning to incoming clock at the FSU CV input. | Off | 0 = free-running; 1 = spawn at metrical divisions in **K3** sparse region.|

All parameters except **K1** are binary switches: CCW is 0 (default); CW is 1.

Exit **SETTINGS** with **FSU-hold (3 sec)**. Settings persist across reboot and reflash. On exit, **SW0** position determines save.

| SW0 POSITION | SETTING | DESCRIPTION|
|---|---|---|
| **SW0=L** | NEW USER | Save edits; new user settings are saved and used on restart.|
| **SW0=C** | OLD USER | Cancel; discard changes and reuse saved user settings on restart.|
| **SW0=R** | DEFAULT | Reset to defaults; discard changes and use module defaults on restart.|

---

## EXAMPLES

### GRAINS

#### RECONSTRUCTION

* Set **SW0=L/K0** = unison (**LED1**=green, 0.4), **SW0=R/K0** = centre, **K5** = 1x (0.8), **K6** = full CCW, **SW0=R/K1** = 0. (no reverse). **LED1** is green at unison.

#### PITCH SHIFTING

* Follow above instructions for reconstruction, and modify **K0** to desired pitch. Slight adjustments to other parameters may yield improved results.

#### TIME SCALING

* Similarly, follow above instructions for reconstruction, and modify **K5** to desired speed. Adjustments to other parameters (notably **K4** and **K6**) will result in improved coverage at **K5** nearer to 0x.

---

## DISCLAIMER

Inspiration was drawn from the instruments (specs, user and service manuals) listed in the above; however, a sufficient use of artistic license has been applied throughout an iterative development process, resulting in the amalgamation which is this firmware.

This is an ongoing project, please look out for updates.

*Use at your own risk, but have fun!*



