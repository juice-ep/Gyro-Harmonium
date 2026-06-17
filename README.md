# G-Harmonium

A gyroscope-powered harmonium built on Gajraj Mohini's iHarmonium project — extended into a fully client-side, installable instrument.

---

**▶ 🎹 Play now!**
[juice-ep.github.io/Gyro-Harmonium](https://juice-ep.github.io/Gyro-Harmonium/)

---

## Install (PWA)

| Platform | Steps |
|----------|-------|
| Android Chrome/Edge | Menu (⋮) → Add to Home screen |
| iOS Safari | Share → Add to Home Screen |
| Desktop Chrome/Edge | Install icon (⊕) in address bar |

Works offline after first session — samples cache automatically.

---

## Sound engine

Real CC0 harmonium recordings (Yale Euterpea Studio / Freesound) pitch-shifted across a sparse sample set. A bellows-driven lowpass filter maps air pressure to timbral brightness — soft pump = warm, full pump = bright and cutting. Short synthetic room reverb adds wooden-cabinet body.

**Reed stops** — pull-knob registers, same as a physical harmonium:

| Stop | Pitch | Character |
|------|-------|-----------|
| Bass | −1 octave | Deep, warm |
| Male | Unison | Natural — default |
| Female | +1 octave | Airy, bright |
| Coupler | +1 octave | Doubles any active stop |

At least one stop must stay active. Multiple stops layer simultaneously.

---

## Scales

**Diatonic** — full 7-note scale (Sa Re Ga Ma Pa Dha Ni Sa), 14 keys: 3 below tonic + octave + 3 above. Supports all 24 keys (12 major, 12 minor) via the root pill selector.

**Chromatic** — 19 keys, same range, all semitones filled in. Starts from the 6th degree of the selected root (relative minor). Scale tones marked with a dot. Shares the diatonic root selector — transpose both views together.

**Ragas** — Bhairav (dawn) and Yaman (evening) in Hindustani sargam notation.

---

## Key mapping

```
Q  W  E  │  A  S  D  F  G  H  J  K  │  L  ;  Z
          │  1  2  3  4  5  6  7  8  │
          ↑ tonic                    ↑ octave
```
C major: `G A B │ C D E F G A B C │ D E F`

Chromatic — white keys: `A S D F G H J K L ; Z` · black keys: `W E R T Y U I O`

Octave shift: − / + buttons on screen (range: 2–6).

**Play modes:** Sustain (held) · Staccato (auto-cut 200ms) · Drone (holds indefinitely)

---

## Bellows

| Device | Method | Notes |
|--------|--------|-------|
| Phone / tablet | Tilt or rock the device | Gyroscope required — all modern mobiles/tablets |
| Desktop / laptop | Hold **Space bar** | Longer hold = fuller bellows |
| Touch (no gyro) | On-screen PUMP button | Functional, not optimised |

**Gyro not responding?** Check browser site permissions — motion sensor access is sometimes denied by default. Go to site settings → Motion sensors → Allow, then reload. Brave browser blocks this by default: Settings → Site Settings → Motion Sensors.

**Best experience:** tablet + external Bluetooth keyboard. Rock the tablet for bellows with one hand, play keys with the other — close to the real split-hand technique.

---

## Credits

- Original concept: [Gajraj Mohini / iharmonium](https://github.com/gajraj-m/iharmonium) — MIT
- Samples: [donyaquick](https://freesound.org/people/donyaquick/) / [cabled_mess](https://freesound.org/people/cabled_mess/) — CC0
- G-Harmonium: this repo — MIT

