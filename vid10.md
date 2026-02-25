Excellent.
Now we move from theory → hardware → real signals in the air.

This episode should feel exciting but grounded — this is where students see **signal processing leave the notebook and enter the antenna**.

Here is your structured **~12-minute lecture script**.

---

# 🎬 Signals to Stars

## Episode 10: SDR & Real RF Signal Capture — Signals in the Wild

---

## 🎥 [0:00 – 1:20] — Introduction + Recap

Hello everyone,
I’m **Sahil Sawant**, currently pursuing my M.Tech in Computer Engineering at VJTI Mumbai, with a background in Electronics and Telecommunication and research experience in RF systems and radio astronomy.

In this series so far:

* Episode 1: Signals carry information.
* Episode 2: Fourier reveals frequency structure.
* Episode 3: Sampling must respect Nyquist.
* Episode 4: Leakage affects analysis.
* Episode 5: Noise limits performance.
* Episode 6: FIR vs IIR filters involve trade-offs.
* Episode 7: Convolution explains system behavior.
* Episode 8: Spectrogram shows time-frequency evolution.
* Episode 9: Wavelets detect transients.

Today, we step outside theory.

Today, we capture real signals.

Today’s topic:

> Software Defined Radio — and real RF signal acquisition.

---

## 🎥 [1:20 – 2:30] — What Is SDR?

Traditionally, radio receivers were built using:

* Analog filters
* Mixers
* Oscillators
* Hardware demodulators

Each function required dedicated circuitry.

But in Software Defined Radio (SDR):

Most signal processing happens in software.

The hardware does only:

1. RF front-end filtering
2. Down-conversion
3. Analog-to-digital conversion

After that, everything is digital.

Filtering, demodulation, decoding — done in software.

SDR turns radio into a programmable system.

---

## 🎥 [2:30 – 3:45] — Basic SDR Architecture

Let’s understand the signal chain.

1️⃣ Antenna captures electromagnetic waves.
2️⃣ RF front-end filters unwanted bands.
3️⃣ Mixer shifts signal to lower frequency (baseband).
4️⃣ ADC samples the signal.
5️⃣ Digital processing extracts information.

At baseband, signals are represented as:

I (In-phase) and Q (Quadrature) components.

This is called IQ sampling.

IQ allows full representation of amplitude and phase.

Without IQ, modern communication would not exist.

---

## 🎥 [3:45 – 5:00] — What Does Real RF Look Like?

When you open an SDR spectrum viewer, you don’t see silence.

You see:

* FM stations
* Wi-Fi signals
* Mobile signals
* Noise floor
* Random interference

The spectrum is alive.

Every peak represents energy at a frequency.

Instead of textbook sine waves,
you see real-world complexity.

---

## 🎥 [5:00 – 6:00] — Connecting to Fourier

Remember Episode 2?

Fourier transforms time-domain signals into frequency domain.

In SDR software:

FFT runs continuously.

That’s how you see real-time spectrum.

The waterfall display is essentially a spectrogram.

Time on X-axis.
Frequency on Y-axis.
Color represents power.

You are literally seeing Episode 8 in action.

---

## 🎥 [6:00 – 7:00] — Sampling in SDR

Remember Episode 3?

Nyquist.

If you want to observe 1 MHz bandwidth,

You must sample at least 2 MHz.

In practice, SDR devices sample much higher.

Improper sampling in SDR causes aliasing.

Real RF systems are direct applications of sampling theory.

Theory becomes hardware reality here.

---

## 🎥 [7:00 – 8:00] — Noise Floor in Real RF

Remember Episode 5?

Noise is unavoidable.

When you open SDR spectrum,

You always see a baseline.

That baseline is noise floor.

If a signal peak rises significantly above noise floor,

It is detectable.

If not, it’s buried.

This is real SNR in action.

---

## 🎥 [8:00 – 9:00] — Practical Demonstration Structure (What You Can Show)

In this video, you can demonstrate:

Option 1: RTL-SDR (Affordable USB SDR)

* Tune to FM band
* Show spectrum peak
* Play audio

Option 2: Pre-recorded IQ samples

* Load data in Python
* Perform FFT
* Plot magnitude spectrum
* Apply low-pass filter
* Demodulate FM signal

Students see full pipeline:
Signal capture → FFT → Filtering → Output

---

## 🎥 [9:00 – 10:00] — SDR in Engineering Fields

SDR is used in:

📡 Communication systems
📡 Satellite receivers
📡 Radar
📡 Electronic warfare
📡 Amateur radio
🌌 Radio astronomy

At IUCAA and GMRT,
digital backends process huge volumes of radio data.

Modern radio telescopes are essentially massive SDR systems.

The principles are identical.

Scale is different.

---

## 🎥 [10:00 – 10:45] — Why SDR Is Important for Students

Why should engineering students care?

Because SDR teaches:

* Sampling in practice
* Real noise behavior
* Filtering application
* IQ modulation
* System-level thinking

It combines:

Electronics + Signal Processing + Software.

It is interdisciplinary engineering.

---

## 🎥 [10:45 – 11:20] — The Core Insight

If you remember one thing today:

> Signals are not just equations on paper.
> They are electromagnetic energy traveling through space.

And SDR lets you capture them.

Everything we’ve learned so far
comes alive inside SDR.

---

## 🎥 [11:20 – 12:00] — Closing + Teaser

In the next episode, we’ll take this further.

We’ll analyze a real-world case study:

Radio astronomy signal processing.

Because detecting weak cosmic signals
is one of the hardest signal processing challenges.

And it combines everything we’ve learned.

Welcome back to **Signals to Stars**.

---

# 🎬 Suggested Visual Enhancements

* SDR hardware image (RTL-SDR dongle)
* Block diagram animation of SDR chain
* Live spectrum waterfall recording
* Highlight noise floor and signal peaks
* IQ signal visualization (complex plane rotation)

---

If you'd like next:

* I can prepare Episode 11: Radio Astronomy Case Study
* Or create a detailed SDR practical lab script
* Or design a mini-project assignment using SDR data

Now your students are not just learning DSP.

They are seeing the electromagnetic world.

That’s powerful. 🚀
