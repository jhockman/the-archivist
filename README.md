# The Archivist

Firmware for the [Noise Engineering Versio](https://noiseengineering.us/pages/world-of-versio/) from [Detuned Transmissions (DTND)](https://detunedtransmissions.com/).

*Recollection* is a re-presentation, the elapsed object reproduced and posited as having been, at will and repeatably. *Retention* exists as an axis of strata with the just-elapsed object held in the active present within the context of previously perceived experience. Each successive stratum retains those before it, the elapsed receding through a continuum towards an indistinct horizon. 

As an agent of recollection and retention, **The Archivist** is a compact performance processor for capturing and manipulating sound in 10hp. It offers two modes of sonic manipulation from distinct eras: **TAPE** emulates early tape splicing procedures, while **GRAINS** affords modern Roads-ian microsound exploration.

Each mode has a specialised capture engine constructed from a tuned misuse of various technologies from its era, resulting in unique aesthetic colouration across memory recall. **TAPE** recreates analogue properties of capture and user parameterisation on reel-to-reel and cassette storage, emulating various cassette recording (EQ, saturation, noise), playback (wow/flutter, head tracking errors), splicing (looping) and effects processing (tape echo, *k*-field modulation); **GRAINS** utilises 1980s/1990s digital techniques for decimation, bit reduction, and efficient storage (DPCM with residual *μ*-law companding and slope overload), additionally providing controls for granular synthesis parameters over a live input.

## Manual

*Video manual to follow; hardware panel imminent...*

### Mode Selection

**SW1**: **L** (or **C**) = **TAPE**, **R** = **GRAINS**.

**SW0**: control page. **L** (or **C**) = main page; **R** = alt page, where some knobs take on a second job — four of them in **GRAINS**, one in **TAPE**. Values are held while a knob is on the page it isn't controlling, and are adopted again on passthrough.  Versio knobs are centred slightly right of the noon position.

### FSU Button

| GESTURE | RESULT |
|---|---|
| **Tap** | Freeze. The engine stops taking new input and keeps playing what it already has.|
| **Hold 3 sec, SW0=C** | Reboots into the **SETTINGS PAGE**.|
| **Hold 3 sec, SW0=L or R** | Clears working memory.|

Freeze clears itself when you change engine, since neither engine can play the other's material.

---

## MODE 1: TAPE (SW1=L or C)

### Main page (SW0=L / C)

| KNOB | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K0** | SPEED | Varispeed control of tape playback (interacts with K4 loop). | Centre=full stop; CCW reverse, CW forwards. Detents at 0, ±0.5x, ±1x and ±2x.|
| **K1** | DRIVE | Record drive into the tape. | CCW=clean, CW=hot.|
| **K2** | RETENTION | Capture decimation, metrical duration and cassette type. See Decimation and Duration below. | Discrete or continuous, per **SETTINGS K0**.|
| **K3** | ECHO | Tape echo (print-through) over the K4 loop duration. | CCW=off, CW=full effect.|
| **K4** | LENGTH | Shortens the tape loop. | The further CCW, the shorter the loop.|
| **K5** | WARBLE RATE | Rate of the *k*-field warble sitting on the output. | CCW=a slow drift, CW=a fast one.|
| **K6** | WARBLE DEPTH | Depth of that warble. | CCW=off, CW=full effect.|

Cassette type rides on retention: each stratum is a different machine, coarser strata being more tired ones, and **LED2** shows which. Wow, flutter and head scrape come with the cassette and with the transport speed rather than from a knob — they are the tape's condition, not a performance control. The warble on **K5** and **K6** is the one that is yours to play.

### Alternate page (SW0=R)

| KNOB | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K4** | SPLICE | The loop's join. | CCW=a 20 ms splice; CW lengthens it toward a quarter-bar dissolve — about half a second at the unclocked tempo, and it follows the sync signal when patched.|

---

## MODE 2: GRAINS (SW1=R)

### Main page (SW0=L / C)

| KNOB | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K0** | PITCH | Grain pitch. See below. | Full CCW=−24 semitones, unison at 0.775, full CW=+12 semitones.|
| **K1** | WINDOW | Grain envelope shape. | Centre=a plateau of pure Hann. CCW morphs to an exponential decay; CW morphs to its reverse, a swell.|
| **K2** | RETENTION | Capture decimation and metrical duration. See Decimation and Duration below. | Discrete or continuous, per **SETTINGS K0**.|
| **K3** | DENSITY | Grain overlap. See below. | Centre=fullest cloud; either extreme=one grain per four grain-lengths.|
| **K4** | LENGTH | Grain length. | 50 ms at full CCW to 2 s at full CW, exponentially.|
| **K5** | MODIFY | Speed and direction of playback, or read position — see **SETTINGS K5**. | Continuous; centre=0x, full CCW=−2x, full CW=+2x, with detents at ±0.5x, ±1x and ±2x.|
| **K6** | SPRAY | Gaussian scatter of grain read positions. | CCW=none (grains follow the read head), CW=maximum scatter.|

### Alternate page (SW0=R)

| KNOB | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K0** | DETUNE | Per-grain pitch deviation. | Centre=off. CCW=continuous spread up to ±12 semitones; CW=discrete interval sets.|
| **K1** | REVERSE | Proportion of grains played backwards. | CCW=all forward, CW=all reverse.|
| **K2** | GLIDE | How fast speed and spacing changes are followed. | CCW=20 ms, CW=1 s.|
| **K3** | SWING / HUMANISE | Grain timing. | CCW of centre=swing; CW of centre=random lateness.|
| **K4** | SPLICE | Softens the join when the read point wraps. See below. | CCW=a hard jump; CW=a wider smear.|

K5 and K6 keep their main-page jobs on both pages.

### K4: the wrap, and softening it

Played below 1x, **GRAINS** reads the buffer more slowly than the input fills it, so the read point falls further and further behind until it runs out of room and jumps forward. That is unavoidable — half-speed consumes material at half the rate it arrives, and no buffer is deep enough to hold the difference forever. What you can change is how the jump sounds.

At full CCW it is a clean cut, which is how the module has always behaved. Turning **K4** up spreads the join across several grains: new grains begin appearing at the new position while the ones already sounding play out where they were, so the change arrives as a dissolve rather than an edit.

It is measured as a **share of the time between jumps**, not as a length. Slow down and the gap between jumps grows, and the smear grows with it — so the proportion of blurred to settled stays wherever you left the knob, and the feel of playing slowly survives. A fixed length could not do that: it would be invisible near 1x and would swallow everything near a standstill.

Nothing is recovered by any of this. The material still skips; you simply stop being told about it.

At very sparse **K3**, or at speeds close to 1x where jumps are rare, there may not be enough grains passing through the join for a dissolve to mean anything. The knob switches itself off there rather than producing a smear too thin to hear.

### K0: the pitch marks

**LED1** marks five pitches: unison, and a fifth and an octave either side of it. They are marks and nothing more — the knob does not stiffen or snap, the pitch runs straight through each one, and everything in between is reachable.

Unison is the exception. It latches exactly, with a small hysteresis band so it holds once caught, and that matters because it is one of the conditions for the null below.

### K3 and K6: density and spray

These are separate controls over the same cloud, and they behave differently.

**K3** sets how many grains overlap. It is thickest at dead centre and thins as you turn either way, and the two halves cover the same ground in opposite directions, so what follows describes both. Working out from centre:

* **Centre to 0.38 / 0.62** — the plateau. Density falls from 20 overlapping grains at dead centre to its base of 5 at the edge. That is about a quarter of the knob's travel, and it is the whole of the thickening range. **LED2 blinks slowly** at the edge.
* **Past the plateau** — sparse, but still continuous. Fewer grains, no gaps, no rhythm, just a thinning texture.
* **LED2 blinks twice as fast** where grains stop overlapping enough to sum smoothly. Turn further and you begin to hear gaps between them. This point moves with pitch and speed, since a grain covers more or less material depending on both — which is why it is shown on the LED rather than printed here as a number.
* **Full CCW / full CW** — the sparsest setting. One grain per four grain lengths: separate events with silence between them.

Both blinks are on **LED2** and keep whatever colour K5 has put there. K3's value is held on the alternate page, so they stay put while you are over there. Neither appears when K5 is set to position.

The two halves of K3 are not mirror images. The **CCW** half spawns grains at a strictly regular interval. The **CW** half spawns them stochastically and gives each grain a random amplitude, so the same density reads as looser and more scattered.

**K6** sets how far grains are thrown from where the read head would otherwise place them. It does not change how many there are. At minimum, spray is not quite zero: a small amount always remains, sized to whatever gap has opened between where the module is writing and where it is reading, so that gap cannot comb the sound. At the null there is no gap, so nothing remains and spray genuinely is off.

The two interact in one place, deliberately. **The plateau does nothing while K6 is at minimum** — sweep it from edge to centre with no spray and you will hear no change at all, since density stays at its base of 5 the whole way. Extra grains only help if there is something separating them; twenty grains landing on an evenly spaced ladder comb rather than thicken. So the plateau is held shut until there is enough scatter to carry it, and it opens as K6 comes up. Where it opens is not a fixed knob position — it depends on grain length, pitch and speed, because the same amount of spray means very different things at a 50 ms grain and a 2 s one.

Density also rises on its own where continuity demands it. Pitching down or speeding up means the material runs past faster than the grains read it, so the count is multiplied to keep coverage: an octave down doubles it, two octaves quadruples it. Pitching **up** does not, since each grain then covers more material, not less. The 20-grain ceiling is a CPU limit and it is shared, so if coverage has already spent the headroom, K3's plateau has less to give — at the bottom of K0's range the coverage requirement alone reaches the ceiling and the plateau gives nothing.

### Reconstruction

**GRAINS** passes the input through unchanged when nothing is asking it not to: **K0** at unison (latched), **K5** at exactly 1x, **K6** at minimum, no detune, no reverse, and the rung not mid-blend. **LED1** flashes blue when all of those hold. The null needs **SETTINGS K5**=Speed: in Position mode there is no read rate for the pitch to match, so it cannot be reached at all.

K3 is not one of the conditions — at the null every grain reads the same sample, so density makes no difference to the result. Neither is stereo spread: the panning is an equal-power coin toss, so the mono sum is unaffected and the null survives at any width.

*NB: Due to the laws of reality, if you play back audio at <1x the output reflects material at an increasingly greater delay from the input. Playing back >1x reuses audio in the buffer. Don't be angry about this, we can't control time yet.*

---

## LEDs

Numbered **0** to **3**, left to right.

### GRAINS

| LED | DESCRIPTION |
|---|---|
| **LED0** | Retention. Blends between colours when the retention is continuous.|
| **LED1** | Pitch. Steady bright blue at unison, and **the same blue flashing when the null holds**. Grey-white at the octaves, orange at the fifth up, deep blue at the fifth down. Elsewhere it dims toward unison, warm below it and cool above.|
| **LED2** | Speed and direction, plus K3's two blinks.|
| **LED3** | Freeze. Icy blue when engaged.|

**LED2** in detail, with **SETTINGS K5**=Speed:

* **Stopped** — flashing red.
* **±1x** — green.
* **±0.5x and ±2x** — white.
* **Everywhere else** — blue forwards, orange in reverse, brighter the faster it goes.
* **K3's two marks blink this LED on and off** without changing its colour, so you can read speed and K3 at once. Slowly at the edge of K3's plateau, twice as fast where gaps start.

With **SETTINGS K5**=Position, LED2 is a brightness ramp instead: off at the bottom of the travel, dim blue just above it, brightening through blue to white at the far end. There are no K3 blinks in position mode.

### TAPE

| LED | DESCRIPTION |
|---|---|
| **LED0** | Retention rung, as above.|
| **LED1** | Speed. Flashing red at the stop, flashing blue at ±1x, white at ±0.5x and ±2x. Between those the hue names the quarter of the knob you are in — red, magenta, yellow, blue — and brightness rises as you approach the nearest ±1x.|
| **LED2** | Cassette type, drawn on the retention palette.|
| **LED3** | Freeze. Icy blue when engaged.|

---

## Decimation and Duration Mapping

| CONTROL | SETTING | DESCRIPTION | RANGE |
|---|---|---|---|
| **K2** | RETENTION | Sets capture decimation and metrical duration. | Discrete or continuous, per **SETTINGS K0**. Discrete gives 8 steps from full CW (48 kHz, 1 bar) to full CCW (3 kHz, 12 bars).|
| **FSU CV INPUT** | SYNC | Clock source for capture and grain triggers. | Unsynced defaults to 120 BPM.|

| | RATE | REACH |
|---|---|---|
| **Full CW** | 48 kHz | 1 bar|
| | 24 kHz | 2 bars|
| | 16 kHz | 3 bars|
| | 12 kHz | 4 bars|
| | 8 kHz | 6 bars|
| | 6 kHz | 8 bars|
| | 4 kHz | 10 bars|
| **Full CCW** | 3 kHz | 12 bars|

A coarser rung reaches further back in time, so at a fixed speed the same phrase gives you more notes the further CCW you go.

---

## SETTINGS PAGE

Seven parameters affecting module behaviour. Enter with **FSU-hold (3 sec)** and **SW0=C**, or by booting with **FSU** held.

*NB*: Avoid CV input modulation while entering, using or exiting.

On entry, **LED_0** shows dim red and **LED_1–3** are off until a knob moves.

| LED | DESCRIPTION |
|---|---|
| **LED_0** | Brightness ramps during the FSU commit hold (3 sec).|
| **LED_1** | Default value of the chosen parameter.|
| **LED_2** | Stored user value of the chosen parameter.|
| **LED_3** | Live knob position. Flashes when the knob value matches the stored user value.|

| KNOB | SETTING | DESCRIPTION | DEFAULT | RANGE |
|---|---|---|---|---|
| **K0** | RETENTION MODE | **K2** Retention control in both modes. | Continuous | Continuous = a smooth sweep between strata; Discrete = 8 stepped strata.|
| **K1** | STEREO SPREAD | Both engines: grains scatter across the field, tape opens its wobble out. | 0 (mono) | 0 = mono; increasing to hard L/R at full CW.|
| **K2** | TAPE SCAN | Where the tape loop sits. | Scan | Scan = roams the memory's whole reach; Loop = sits at the write head.|
| **K3** | SCAN REFERENCE | What the scan is referenced to. | K0 | K0 = the speed knob; 1x = unity.|
| **K4** | RHYTHM TRANSFER | Whether a rhythm found at one memory survives being carried to another. | Bar | Bar = divides the bar, so **K4** means one length at every memory and a rhythm found at 48 kHz survives a **K2** sweep; Memory = divides the reach, so each memory's bar count flavours the ladder and a **K2** sweep carries the rhythm with it.|
| **K5** | K5 FUNCTION | What **K5** does in **GRAINS**. | Speed | Speed = playback rate and direction; Position = read position within the buffer.|
| **K6** | GRAIN SYNC | Grains sync to incoming clock at the FSU CV input. | Off | Off = free-run; On = grain spacing snaps to metrical divisions in K3's sparse region.|

All parameters except **K1** are binary switches: the CCW half is the default, the CW half is the alternative.

*NB* on **K6**: with grain sync on (see **SETTINGS**) and a clock sync in **FSU INPUT**, the outermost regions of K3 snap to divisions (nearest to centre remains continuous).

Exit with **FSU-hold (3 sec)**. Settings persist across reboot and reflash. On exit, the **SW0** position decides what is kept:

| SW0 POSITION | SETTING | DESCRIPTION|
|---|---|---|
| **SW0=L** | NEW USER | Save edits; new user settings are saved and used on restart.|
| **SW0=C** | OLD USER | Cancel; discard changes and reuse saved user settings on restart.|
| **SW0=R** | DEFAULT | Reset to defaults; discard changes and use module defaults on restart.|

---

## Flash

1. Download `the-archivist.bin` from the repository.
2. Put your Versio into DFU mode (see the NE Versio firmware wizard for instructions).
3. Load the `.bin` using either the NE Versio firmware wizard on the [NE Versio page](https://noiseengineering.us/pages/world-of-versio/) or the [Electrosmith Daisy Bootloader page](https://flash.daisy.audio/).

## Disclaimer

**Known (*but possibly enjoyable*) behaviour:**

* In **GRAINS**, the alignment search that keeps consecutive grains in phase can only reach a fixed distance, while the error it corrects grows with grain length. At long grains it stands down, so pitch and speed offsets that sound clean at short grains may need **K4** brought down to stay tidy.

* At the far ends of **K3** you are hearing individual grains with silence between them. That is the intent, but the window shape set by **K1** is much more exposed there than it is in the middle of the knob.

*Use at your own risk, but have fun!*
