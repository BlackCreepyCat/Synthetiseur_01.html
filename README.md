🎛️ WEIRD-01 — Experimental Web Synthesizer
A full-featured polyphonic synthesizer, sequencer and tape recorder running entirely in your browser. One HTML file. Zero dependencies. Zero installs.

Version License Audio

WEIRD-01 is a self-contained experimental synthesizer built as a single HTML file. Open it in any modern browser, hit POWER ON, and you have a complete music studio:
two oscillators with exotic waveforms, a resonant filter, LFO modulation, drive & bitcrusher, stereo delay, convolution reverb, a 16-step sequencer with pattern 
chaining, a tape recorder with bit-perfect WAV export, an oscilloscope, spectrum analyzer and stereo PPM — all wrapped in a retro studio-rack interface with three switchable skins.

<img width="881" height="1060" alt="image" src="https://github.com/user-attachments/assets/7375bbeb-3bdc-4c53-a430-906d6085130e" />

✨ Features
🔊 Synthesis Engine
2 oscillators with 10 waveforms: 4 classic (Sine, Square, Saw, Triangle) + 6 exotic waveforms built from additive harmonic tables (Alien, Bell, Vox, Metal, Demon, Chaos)
Unison per oscillator (1–4 detuned voices with spread control)
Noise generator (white / pink, Paul Kellet filter)
Pitch envelope (for laser sweeps, bubbles, pitch-drops)
ADSR envelope with click-free releases
Resonant filter: Low Pass / High Pass / Band Pass / Notch, with its own envelope
LFO routable to Pitch, Filter Cutoff and Tremolo — including a random waveform mode
Glide (portamento) between notes
Real Waveshaper drive and bitcrusher
Stereo delay with feedback + convolution reverb
Master compressor and voice stealing (max 8 simultaneous notes)

🎹 Playing
On-screen 25-key keyboard (drag for glissando, touch-friendly)
Computer keyboard mapping (AZERTY & QWERTY compatible)
Arpeggiator (Up / Down / Up-Down / Random, 1–3 octaves)
The keyboard auto-follows the sequencer octave — you literally watch the sequence play

🎚️ Patch Bank — 46 Factory Patches
8 categories of hand-tuned presets:

Category
Highlights
🌿 NATURE	Cricket, Frog, Whale Song, Birdsong, Zephyr, Thunder, Sonar
👾 RETRO	Arcade Coin, 8-Bit Jump, Game Over, Power-Up, Casio 1985, Modem 56K, Moog 74
🎬 CINEMA	Suspense drone, Terror Sting, Epic Braaam, Shimmer, Nuke Siren
🛸 SFX	UFO, Invader, Laser, Bubble, Robot, Plasma
🎸 BASS	Acid 303, Wobble, Growl Sub, Reez
🚀 LEADS	Crystal Pluck, Shrill Lead, Alien Flute, Haunted Organ
☁️ PADS	Ghost, Dream, Angelic Choir, Neon Drone
🥁 DRUMS	Deep Kick, Noisy Snare, Ghost Hat, Cinema Boom

The currently selected patch shows a lit LED indicator. Your own tweaked settings can be saved to the browser (💾 SAVE THIS PATCH).

🎼 Sequencer
16-step piano-roll grid × 12 semitones
4 velocity levels per cell: note → accent → ghost → off (click to cycle, right-click to erase, drag to paint)
Tempo (40–240 BPM), Swing, Gate length
Transposable (root note + octave), 🎲 Dice generator constrained to a chosen scale (Minor/Major pentatonic, Major, Chromatic)
4 pattern slots (A/B/C/D), switchable live while playing
⛓ Pattern Chain: build songs up to 16 bars by placing patterns per bar, with live bar highlighting
Everything auto-saves to local storage

📼 Tape Deck
Record your performance (keyboard, arpeggiator or sequencer) with exact timing and velocity
Play back with transport controls, optional ⟳ Loop mode — jam over the loop while it plays

⤓ Export as .WAV — and here's the cool part:
🔬 Bit-perfect export. The WAV is rendered offline with the exact same signal chain, the same deterministic reverb/LFO/noise (seeded PRNG), the same sample rate as your audio device. What you heard is what you get.

The tape LCD shows a running counter; reels and tape strip animate during REC/PLAY

📺 Monitor
Oscilloscope (real-time waveform, skin-colored CRT grid)
Spectrum analyzer (36 log-spaced LED-segmented bars)
Stereo PPM with dB scale (-48 → 0), peak-hold and clip LED

🎨 Interface
3 skins: MIDNIGHT (cyan/amber), VINTAGE (wood & warm amber), NEON (magenta) — persisted between sessions
Studio-rack aesthetic: brushed metal plates, screws, LCD readouts, magnetic tape reels
Fully responsive (desktop + tablet)

🚀 Getting Started
Download synth.html (or clone the repo)
Open it in any modern browser — Chrome, Edge, Firefox, Safari

Click ⏻ POWER ON (browsers require a user gesture before audio)
Play with your keyboard (A Z E R T Y / Q W E R T Y rows), or hit ▶ SEQ ON and the Acid pattern starts grooving
That's it. No server, no build step, no dependencies.

⌨️ Keyboard Shortcuts
Key Action
A S D F G H J K L (+ W E T Y U O P)	Play notes (piano layout)
↑ / ↓	Shift keyboard octave
Space	Play / stop the recorded take
R	Toggle recording
Esc	Panic — stop everything, kill all voices

🖱️ Knob Controls
Gesture Action
Drag up/down	Adjust value
Mouse wheel	Fine steps
Shift + drag	Precision mode
Double-click	Reset to default

🔬 Technical Highlights
100% Web Audio API — oscillators, BiquadFilters, WaveShaper curves, ConvolverNode, DynamicsCompressor, OfflineAudioContext
Exotic waveforms generated with createPeriodicWave from hand-crafted harmonic tables
Deterministic audio: reverb impulse response, random LFO and noise buffers are generated with a seeded PRNG (mulberry32) so live playback and offline export are identical
Anti-click engineering: cancelAndHoldAtTime with analytic envelope reconstruction fallback, guaranteed decay-to-silence before oscillator stops, click-free gain automation everywhere
Sample-accurate sequencer: lookahead scheduler (120 ms) driven by the audio clock, not setTimeout
Memory-safe: voice lifecycle tracking, ended-voice purging, scheduled-voice cancellation, curve caching
Chrome-tier robustness: audio context wake-up after mobile interruptions, cross-tab focus handling, legacy Safari fallback
