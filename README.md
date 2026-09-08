# Harmonic EQ

**Intelligent harmonic-tracking parametric EQ by Aeons Light**

Harmonic EQ automatically detects the fundamental frequency of your audio and positions EQ bands at exact harmonic multiples — shaping individual harmonics in real-time as the pitch changes.

![Harmonic EQ](images/harmonic-eq-tracking-no-eq.png)

## Features

- **Follows Every Note** — bands lock onto the fundamental and ride the harmonic series in real time
- **8 Configurable Bands** - any harmonic, sub-harmonic, musical interval or custom multiplier, as a
  bell, shelf, notch, high pass or low pass, at 6 to 48 dB/oct
- **Dynamic Mode** — per-band threshold gating applies EQ only when harmonics exceed your set level
- **Live Spectrum Analyzer** — pre/post FFT display with draggable nodes and bell curve visualization
- **Solo Audition** — isolate any band to hear exactly what the EQ is doing
- **Frequency Lock** — manual frequency override for drones, synths, and single-note processing
- **Sidechain or MIDI** - take the pitch from another track, or from MIDI notes where detection
  would struggle: a chord, a noisy mic, heavy distortion
- **Pitch-to-MIDI** - export the tracked note as MIDI, with level-based velocity and attack retriggering.
- **79 Factory Presets** - vocal, guitar, bass, drums, de-harsh, creative, mastering, advanced, plus
  band layouts that place the bands and leave the sound alone

### EQ with Harmonic Tracking

![EQ Applied](images/harmonic-eq-eq-applied.png)

### Dynamic Mode

![Dynamic EQ](images/harmonic-eq-dynamic.png)

### Solo Audition

![Solo](images/harmonic-eq-solo.png)

### Higher Harmonics

![Higher Harmonics](images/harmonic-eq-higher-harmonics.png)

## Download

### Latest Release

| Platform | Download |
|----------|----------|
| **Windows** | [Download Installer (.exe)](https://github.com/aeons-light/harmonic-eq-releases/releases/latest/download/HarmonicEQ-Windows-Installer.exe) |
| **macOS** | [Download Installer (.pkg)](https://github.com/aeons-light/harmonic-eq-releases/releases/latest/download/HarmonicEQ-macOS-Installer.pkg) |
| **Linux** | [Download VST3](https://github.com/aeons-light/harmonic-eq-releases/releases/latest/download/HarmonicEQ-Linux-VST3.zip) · [Download CLAP](https://github.com/aeons-light/harmonic-eq-releases/releases/latest/download/HarmonicEQ-Linux-CLAP.zip) |

> Try it free with full functionality. Purchase a license at [aeonslight.com](https://www.aeonslight.com) to unlock.

## Changelog

### v1.1.0 (2026-09-08)

**Added**
- Export pitch as MIDI: the tracked note goes out as MIDI, with velocity following your level.
- Retriggering: a fresh attack at the same pitch starts a new note, with sensitivity and timing controls.
- Right-click the pitch readout to show note names instead of Hertz.

**Improved**
- MIDI note stability reaches 75 cents for deep vibrato, and leaps always switch instantly.
- The VST3 parameter list is 2048 entries shorter.

Note: the new MIDI output appears after a plugin rescan in your DAW.

### v1.0.6 (2026-08-31)

**Added**
- Right-click any knob to type an exact value.
- ×64 in the harmonic menu, and custom multipliers up to ×256.
- Four extreme Creative presets that arm auto gain on load.
- Vocal Presence now comes in Male and Female voicings.

**Improved**
- Thirty presets re-spread so air, grit, sibilance and pick-attack bands sit where their names say.
- Preset cycling follows the menu's category order.
- Auto-enable fires once and unchecks itself; the clipper's is now off by default.

**Fixed**
- Vocal Telephone is now a true tracked bandpass.

Note: the wider multiplier range remaps any existing multiplier automation lanes; saved sessions and presets are unaffected.

### v1.0.5 (2026-08-30)

**Added**
- SCALE knob: sizes the whole EQ from 50% to 200%, replacing 200% mode; old sessions migrate automatically.
- HQ and sidechain share one split button, and the settings gear glows when an update is available.

**Improved**
- The auto gain algorithm has been further fine-tuned and improved.

**Fixed**
- At 0% MIX the output is now the bit-exact input; output gain and auto gain shape only the processed signal.

### v1.0.4 (2026-08-28)

**Improved**
- Band gain readouts show the applied value when 200% mode scales it.

### v1.0.3
**New**
- Auto gain: right-click the OUT knob for loudness compensation that never pumps
- Soft clipper, off by default: rounds off peaks past full scale
- Clip meter: clipping now shows on the dBFS scale in red
- The dry/wet knob now caps at 100% by default
- 200% mode is exposed via right-click on MIX and provides up to 72 dB of gain
- Step a selected band through the harmonics with + and -

**Improved**
- Band headers show interval names, and the settings menu ticks the current value

**Fixed**
- The slope menu listed Standard twice on bells, shelves and notches

### v1.0.2
**Improved**
- A band boosts as far as it cuts, to +36 dB. It stopped at +12, which also meant MIX above 100% did
  little to a large boost, since the doubled value was clipped back
- The analyser grows its scale to suit: +12 as before, stretching to +24 or +36 when a band goes that
  far, animated, with 0 dB moving toward the middle as the two halves even up

**Fixed**
- Dragging a node was capped at +12 dB even once the scale had grown

### v1.0.1
**Fixed**
- A momentary dropout while tracking. A filter could run away internally when a new pitch arrived
  while its state was still settling, and the safeguard that caught it silenced the whole plug-in for
  one processing block.

### v1.0.0
**New**
- MIDI as a pitch source - right-click SC to track notes instead of audio, for material where
  detection struggles, or for exact placement on a sequenced part
- An 18 dB/octave slope, between the existing 12 and 24
- A/B comparison, holding two complete settings with a copy between them
- Band layout presets - even and odd harmonic sets, major and minor scales - which place the bands
  without touching the sound
- The interface picks a size to suit your display on first launch
- Update notices, when a newer version is out

**Improved**
- Redrawn interface throughout
- Q no longer spikes the corner when a band is switched to a shelf or rolloff, and it now works at
  24 and 48 dB/oct, where it previously did nothing
- High and low pass nodes can be dragged to set corner resonance
- A notch is drawn as the break it is, rather than a shallow dip
- The vertical scale is smooth, so a curve no longer kinks where the resolution changes
- Clicking anywhere on a band's strip selects it

**Fixed**
- A filter could diverge to infinity when tracking remodulated its coefficients, reaching the host as
  a silenced block. It is now caught in the band that causes it, costing one sample
- The gate's threshold line is gone from the analyser: it read about 23 dB high, because the gate
  measures broadband peak while the analyser draws per-bin levels. The knob's arc shows it instead
- A JSON file that was not a preset could load as a nameless one and apply zeroes to everything

### v0.2.17
**New**
- A detector gate rolloff of 18 dB/octave

**Fixed**
- Non-finite samples can no longer reach the host

### v0.2.15
**New**
- Six band types - bell, low shelf, high shelf, notch, high pass and low pass - selectable per band
- Four filter slopes per band, setting dB/octave for high and low pass, and how wide the plateau is for bells, shelves and notches
- A detector gate, so quiet bleed and room noise can no longer retune the EQ, with the threshold drawn across the analyser and the incoming level shown on the knob
- Interface scaling at 100%, 125%, 150% and 200%, in the About dialog
- A level scale down the right-hand side of the analyser, so the spectrum and the gate threshold can be read in dB

**Improved**
- The frequency lock moved into the FREQ knob - click the centre to lock, and it captures the pitch it last detected
- The window is 95px shorter, with the Q and gain knobs interlocked and each band's frequency shown inside its Q knob
- Q now responds proportionally to the scroll wheel, at the same rate on the knob and on the analyser node
- The EQ curve is drawn from the actual filter coefficients, so shelves, notches and rolloffs show their true shape
- The analyser's vertical range now extends far enough that loud material is no longer flattened against the top
- The pitch readout follows detection at a consistent speed regardless of your screen's refresh rate
- Tooltips size themselves to their text rather than cutting off the longer ones

**Fixed**
- Various fixes and refinements

### v0.2.14
**New**
- An output gain knob, so you can trim the plugin's level by -24 to +12 dB

### v0.2.13
**Fixed**
- Soloing more than one band at a time now works correctly, with each band heard at its own frequency
- Auto-bypass no longer clicks as it engages or releases, in both standard and HQ modes
- Following a new note no longer produces a faint click, which was most audible when auditioning a single band with Solo

### v0.2.12
**Improved**
- The Windows installer is now signed, so it installs without security warnings

### v0.2.11
Various bug fixes and refinements.

### v0.2.10
**Improved**
- The macOS installer is now signed and notarized by Apple, so it installs without security warnings

### v0.2.9
**Improved**
- Pitch readout moved to the header, colour-coded to show tracking state at a glance
- Sensitivity knob rescaled for finer control in the useful range

Various bug fixes and refinements.

### v0.2.8
**Improved**
- The EQ graph now draws one continuous curve with band colours blending together

Various bug fixes and stability improvements. Updating is recommended for anyone using HQ mode.

### v0.2.7
**Improved**
- Band nodes stay at their gain setting in Dynamic mode, making them easier to drag

Various bug fixes.

### v0.2.6
**New**
- HQ mode adds 8x oversampling for higher quality processing
- Analyzer status messages for unpitched audio and auto-bypass

Various bug fixes and refinements.

---

## System Requirements

- Windows 10+ (64-bit)
- macOS 11+ (Intel & Apple Silicon)
- Linux (64-bit)
- Any DAW supporting VST3, CLAP, or AU

## License

$50 — Pay once, keep your license forever.

[Buy Now](https://buy.stripe.com/6oU9AS4KTckCg5UfKZ3cc01)

---

© 2026 Aeons Light. All rights reserved.
