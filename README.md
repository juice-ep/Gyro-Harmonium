# Gyro-Harmonium PWA
A Harmonium emulator using gyroscopic sensor for voice modulation. Works on web browsers and can function as a standalone PWA with keyboard controls as fallback for PCs 

**Remixed from [gajraj-m/iharmonium](https://github.com/gajraj-m/iharmonium)** — original concept by Gajraj Mohini (MacBook lid sensor + WebSocket bellows). This fork replaces the Python backend and Mac-only sensor with a fully client-side PWA using the device gyroscope and a custom wavetable audio engine.

---

## Sound Engine

The original used basic Web Audio oscillators (sawtooth + square). This version replaces that with a **wavetable synthesiser** built directly on the Web Audio `PeriodicWave` API — no samples, no external files, loads instantly and works offline.

### Harmonic recipe

The waveform is constructed from the actual harmonic series of a North Indian harmonium reed, derived from acoustic measurements:

- **Odd harmonics dominate** (1, 3, 5, 7) — this is reed physics; the reed tongue's symmetrical vibration suppresses even partials
- **Rolloff ≈ 1/n^1.3** — slightly steeper than a sawtooth, giving the characteristic softness vs. a harsh synth tone
- **Boosts at 3rd (+35%) and 5th (+15%)** — responsible for the nasal, reedy bite
- **Tiny cosine phase offset** on each partial — adds a subtle "chiff" transient as the reed speaks

### Dual-reed unison

Every note plays two slightly detuned oscillators through the same wavetable:
- Reed 1: +4 cents
- Reed 2: −2 cents

Real harmonium keys have two physical reeds per note, tuned very close but not identical. The beating between them — a slow amplitude shimmer — is the most distinctive quality of the instrument's sustain.

### Bellows → filter (timbral dynamics)

A per-note lowpass filter (Q = 1.4 for slight resonant "honk") maps bellows pressure to brightness:

| Bellows | Filter cutoff | Sound character |
|---------|--------------|-----------------|
| 0%      | ~700 Hz      | Muffled, quiet  |
| 50%     | ~1700 Hz     | Warm, present   |
| 100%    | ~4200 Hz     | Bright, cutting |

This mirrors what actually happens acoustically — higher air pressure forces the reed to vibrate with greater amplitude, exciting more upper partials. The relationship is logarithmic (as perceived pitch is), so the sweep feels natural across the full range.

### Reverb

A short synthetic impulse response (0.9 s exponential decay noise) adds the resonance of a wooden box. Wet/dry: 18% — enough to add body without washing out articulation.

---

## What's different from the original

| Feature | Original | This fork |
|---------|----------|-----------|
| Bellows input | MacBook lid sensor via Python | Device gyroscope (iOS + Android) |
| Backend | Python WebSocket server | None — fully client-side |
| Sound | Sawtooth + square oscillators | Wavetable (reed harmonic series) |
| Timbral dynamics | Volume only | Volume + filter cutoff (bellows → brightness) |
| Dual reed shimmer | No | Yes (two detuned wavetable voices) |
| Reverb | No | Synthetic room IR |
| Scales | Chromatic only | Pentatonic, Chromatic, Bhairav, Yaman |
| Touch input | Pointer events (buggy on mobile) | Pointer capture + `lostpointercapture` (multi-touch correct) |
| Offline | No | Yes (service worker) |
| Installable | No | Yes (PWA manifest) |

---

## Deploy to GitHub Pages

1. Push this folder to a GitHub repo (all files at root)
2. Settings → Pages → Branch: `main` / root
3. Visit `https://yourusername.github.io/repo-name/`

No build step. No dependencies. No server.

---

## Playing

| Device | Bellows | Notes |
|--------|---------|-------|
| Tablet / Phone | Tilt or rock the device | iOS requires one-time motion permission on first tap |
| Desktop | Hold **Space** | The PUMP button also appears for pointer devices |

### Key mapping (Pentatonic default)

```
Keys:  A  S  D  F  G  H  J  K  L  ;
Notes: C  D  E  G  A  C  D  E  G  A
```

### Play modes

- **Sustain** — note plays while key/finger is held, releases when lifted or finger leaves key
- **Staccato** — auto-cuts at 180 ms (good for rhythmic playing)
- **Drone** — notes hold indefinitely regardless of finger position (tanpura-style)

### Octave

Use the − / + buttons to shift the entire keyboard up or down. Range: octaves 2–6.

---

## License

MIT — original code by Gajraj Mohini, remix and audio engine by this fork. Feel free to use and modify.
