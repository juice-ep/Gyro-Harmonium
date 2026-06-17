# G-Harmonium

A browser-based harmonium that uses your device's gyroscope as the bellows.

Built on the original concept by [Gajraj Mohini (gajraj-m/iharmonium)](https://github.com/gajraj-m/iharmonium) — this is an extension of that idea, taking it further into a self-contained, installable instrument you can play anywhere.

---

## Play now

**[juice-ep.github.io/Gyro-Harmonium](https://juice-ep.github.io/Gyro-Harmonium/)**

Tap *Begin Playing* on the screen to start. No login, no install required to play in the browser.

---

## Install as an app (PWA)

Installing puts it on your home screen with no browser chrome, full screen, and offline support.

**Android (Chrome or Edge)**
Settings (⋮) → *Add to Home screen* → Install

**iOS (Safari)**
Share button → *Add to Home Screen*

**Desktop (Chrome / Edge)**
Address bar → install icon (⊕) on the right → Install

Once installed it works offline — samples cache after the first session.

---

## Features

**Gyroscope bellows** — tilt or rock your device to push air through the reeds, the same physical motion as working a real harmonium bellows. Works on any mobile or tablet with a built-in gyroscope. The bubble indicator shows the sensor reading in real time.

**Reed stops** — four pull-knobs modelled on the air-stop registers of a real harmonium:
- *Bass* — one octave below (deep, warm body)
- *Male* — unison pitch, the default natural sound
- *Female* — one octave above (airy, bright)
- *Coupler* — layers an octave above whatever else is active

Pull multiple stops for layered, fuller sound. At least one must stay active.

**Diatonic scale** — the full seven-note scale (Sa Re Ga Ma Pa Dha Ni Sa) across 14 keys: three notes below the tonic, a complete octave, and three notes above. All white keys, all in the scale — no wrong notes.

**Major and minor modes** — toggle between major and natural minor (Aeolian). Each has its own set of enharmonic spellings (F major uses B♭ not A♯, etc.).

**All 24 keys** — scroll through all 12 major and 12 minor roots via the pill selector. The entire keyboard and chromatic view transpose instantly.

**Chromatic view** — 19 keys covering the same range as the diatonic view but with all black and white keys filled in. Starts from the 6th degree of the selected scale (the relative minor root in major keys), runs a full chromatic octave, plus three above. Scale tones are marked with a dot.

**Ragas** — Bhairav (dawn raga) and Yaman (evening raga) layouts with Hindustani sargam notation.

**Play modes**
- *Sustain* — note sounds while key or finger is held, releases on lift
- *Staccato* — auto-cuts at 200ms, good for rhythmic playing
- *Drone* — notes hold indefinitely regardless of finger position, useful for Sa/Pa tanpura-style accompaniment

**Real sampled sound** — the reed sound comes from actual harmonium recordings (CC0 public domain, Yale Euterpea Studio via Freesound). Samples load in the background on first use, then cache for offline play. A bellows-driven lowpass filter opens and closes with air pressure, so pushing harder genuinely changes the timbre — brighter when full, warmer when soft.

---

## Key mapping

**Diatonic scale (14 keys)**

```
Q  W  E  │  A  S  D  F  G  H  J  K  │  L  ;  Z
−3 −2 −1 │  1  2  3  4  5  6  7  8  │  9  10 11
              ↑ tonic                    ↑ octave
```

Example — C major: `G A B │ C D E F G A B C │ D E F`

**Chromatic view** — white keys use the home row (A S D F G H J K L ; Z), black keys use the top row (W E R T Y U I O).

**Octave** — use the − / + buttons on screen to shift the whole keyboard up or down. Range: octaves 2–6.

---

## Bellows — by device type

**Tablet or phone with gyroscope (recommended)**
Tilt or rock the device. The faster and more pronounced the motion, the more air moves. The bellows decays naturally when you hold still, just like resting your hand on the real instrument.

If the gyroscope isn't responding, check browser and page permissions — some browsers deny motion sensor access by default. In the browser's site settings, look for *Motion sensors* or *Device orientation* and set it to Allow, then reload the page. Brave browser in particular blocks this by default (see Settings → Site Settings → Motion Sensors).

Gyro works on devices with a screen-mounted gyroscope — essentially all modern phones and tablets. Laptops and desktop computers do not have a gyroscope.

**Desktop or laptop (keyboard)**
Hold the **Space bar** to pump the bellows. The longer you hold it, the more the bellows fills. Release and it decays naturally. Use your left hand on Space and your right hand on the note keys, or map them however suits you.

**Touch screen without gyro**
The on-screen PUMP button appears on pointer devices. Touch keys on the virtual keyboard work for notes. Touch is functional but not optimised — the gyro or keyboard experience is significantly better for sustained playing.

---

## Best setup

A **tablet with an external Bluetooth keyboard** comes closest to the natural feel of the instrument. The tablet sits in your lap or on a stand, you rock it gently with one hand for bellows movement while playing notes on the keyboard with the other. It mirrors the physical split of pumping with one hand and playing keys with the other on a real harmonium.

---

## Credits

- Original iHarmonium concept: [Gajraj Mohini](https://github.com/gajraj-m/iharmonium) — MIT licence
- Harmonium samples: [donyaquick](https://freesound.org/people/donyaquick/) / [cabled_mess](https://freesound.org/people/cabled_mess/) via Freesound — CC0 public domain
- G-Harmonium extension: this repository — MIT licence
