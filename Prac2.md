
# Signals to Stars — Practical Session 2  
## Composite Signals & FFT: Seeing Frequencies Emerge

---

## 👨‍🏫 Instructor Introduction

Hello everyone,  
I’m **Sahil Sawant**, currently pursuing my M.Tech in Computer Engineering at VJTI Mumbai, with a background in Electronics and Telecommunication and research experience in RF systems and radio astronomy.

In the previous lecture, we explored the difference between **time domain and frequency domain** and understood why Fourier analysis exists.

Theory helps us understand concepts, but signal processing must be experienced visually.

This practical demonstrates how multiple frequencies combine into one waveform and how **FFT reveals the hidden structure**.

---

## 🎯 Objectives

In this practical you will:

- Generate multiple sine waves
- Combine them into a composite signal
- Visualize the signal in time domain
- Perform Fast Fourier Transform (FFT)
- Identify frequency peaks
- Verify that FFT reveals original components

---

## 🧠 Concept Recap

A complex signal can often be expressed as a sum of simple oscillations.

Time domain → shows variation  
Frequency domain → shows composition

FFT is the computational tool that converts between these perspectives.

---

## 💻 Software Requirements

You may use:

- Python (NumPy, Matplotlib) ✅ Recommended
- MATLAB
- Google Colab (no installation required)

---

## ⚙️ Experimental Setup

### Parameters

- Sampling Frequency: 500 Hz  
- Duration: 2 seconds  
- Frequencies: 5 Hz, 15 Hz, 40 Hz  

This simulates a real sensor capturing multiple oscillatory sources.

---

## 🧪 Step 1 — Generate Composite Signal (Python)

```python
import numpy as np
import matplotlib.pyplot as plt

fs = 500
t = np.linspace(0, 2, 2*fs)

f1, f2, f3 = 5, 15, 40

signal = np.sin(2*np.pi*f1*t) + np.sin(2*np.pi*f2*t) + np.sin(2*np.pi*f3*t)

plt.plot(t, signal)
plt.title("Composite Signal - Time Domain")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")
plt.show()
````

### Observation

* The waveform appears complex
* Individual frequencies are not easily distinguishable

This demonstrates the limitation of time-domain inspection.

---

## 🧪 Step 2 — Perform FFT

```python
fft_vals = np.fft.fft(signal)
freqs = np.fft.fftfreq(len(signal), 1/fs)

plt.plot(freqs[:len(freqs)//2], np.abs(fft_vals[:len(fft_vals)//2]))
plt.title("Frequency Spectrum")
plt.xlabel("Frequency (Hz)")
plt.ylabel("Magnitude")
plt.show()
```

---

## 📊 Expected Result

You should observe clear peaks near:

* **5 Hz**
* **15 Hz**
* **40 Hz**

These correspond to the original signal components.

FFT has revealed the signal structure.

---

## 🧠 Interpretation

* Time domain hides composition
* Frequency domain exposes composition
* Peak height corresponds to signal strength
* Noise would raise background but peaks remain detectable

This is how:

* Spectrum analyzers work
* RF receivers detect channels
* Astronomers detect spectral lines

---

## 🧪 MATLAB Equivalent

```matlab
fs = 500;
t = linspace(0,2,2*fs);

signal = sin(2*pi*5*t) + sin(2*pi*15*t) + sin(2*pi*40*t);

fft_vals = fft(signal);
freqs = (0:length(signal)-1)*(fs/length(signal));

plot(freqs, abs(fft_vals));
title('Frequency Spectrum');
xlabel('Frequency (Hz)');
ylabel('Magnitude');
```

---

## ✅ Conclusion

This experiment verifies a fundamental principle:

A complex waveform is often a combination of simple oscillations.

FFT does not create frequencies —
it reveals what already exists.

This idea forms the foundation of:

* Communication systems
* Audio processing
* Biomedical analysis
* Radar
* Radio astronomy

---

## 📝 Student Tasks

1. Change amplitudes of each frequency and observe peak heights
2. Add noise and observe spectrum changes
3. Try different sampling rates
4. Add a fourth frequency
5. Compare MATLAB vs Python output

---

## 🚀 Next Practical Preview

In the next session we will explore:

* Sampling mistakes
* Aliasing
* How incorrect sampling produces false frequencies

This is where real engineering failures begin.

---

## 📌 Key Insight

**Frequency domain is a lens that reveals hidden structure in signals.**

```
```







Great — this becomes **Practical Session 2** of your series.
Tone: calm, lab-style, professional but friendly.
Length target: ~12 minutes (~2400 words).
Structured for recording + screen demo.

---

# 🎬 Signals to Stars — Practical 2

## Composite Signals & FFT: Seeing Frequencies Emerge

---

## 🎥 [0:00 – 1:15] — Introduction + Context

Hello everyone,
I’m **Sahil Sawant**, M.Tech Computer Engineering at VJTI Mumbai, with a background in Electronics and Telecommunication and research experience in RF systems and radio astronomy.

In the previous lecture, we explored one of the most important ideas in signal processing:

Time domain shows how a signal changes.
Frequency domain reveals what oscillations exist inside it.

We discussed Fourier Transform conceptually.

But signal processing is not something you understand by theory alone.

You must see it.

That’s why today we begin our second practical session.

We will create a signal ourselves — a composite signal made of multiple frequencies — and then use FFT to reveal those hidden components.

---

## 🎥 [1:15 – 2:30] — Concept Covered in This Practical

In this session we will:

1. Generate three sine waves of different frequencies
2. Combine them into a single waveform
3. Observe the signal in time domain
4. Apply Fast Fourier Transform
5. Identify frequency peaks

The goal is simple but powerful:

To prove that frequency domain correctly reveals the building blocks of a signal.

This experiment is foundational for communication, audio engineering, RF, biomedical signals, and astronomy.

---

## 🎥 [2:30 – 4:00] — Software Setup

You can perform this practical using:

* Python with NumPy and Matplotlib (recommended)
* MATLAB using built-in FFT functions
* Google Colab if you don’t want installation

Today I’ll demonstrate using Python because it is accessible to everyone.

The workflow is identical in MATLAB.

Before writing code, understand what we need:

* Sampling rate
* Time vector
* Frequencies of individual signals
* Signal combination

We are essentially simulating a real sensor measurement.

---

## 🎥 [4:00 – 6:00] — Creating the Composite Signal (Code Explanation)

We choose:

Sampling frequency: 500 Hz
Duration: 2 seconds
Frequencies: 5 Hz, 15 Hz, 40 Hz

That means our signal contains three oscillations.

### Python Code

```python
import numpy as np
import matplotlib.pyplot as plt

fs = 500
t = np.linspace(0, 2, 2*fs)

f1, f2, f3 = 5, 15, 40

signal = np.sin(2*np.pi*f1*t) + np.sin(2*np.pi*f2*t) + np.sin(2*np.pi*f3*t)

plt.plot(t, signal)
plt.title("Composite Signal - Time Domain")
plt.xlabel("Time (s)")
plt.ylabel("Amplitude")
plt.show()
```

What this does:

* Generates three pure tones
* Adds them together
* Displays one complex waveform

Students should notice:

You cannot visually separate the three frequencies.

Time domain hides structure.

---

## 🎥 [6:00 – 8:30] — Performing FFT (Code + Explanation)

Now we apply FFT.

FFT converts the signal from time to frequency domain.

### Code

```python
fft_vals = np.fft.fft(signal)
freqs = np.fft.fftfreq(len(signal), 1/fs)

plt.plot(freqs[:len(freqs)//2], np.abs(fft_vals[:len(fft_vals)//2]))
plt.title("Frequency Spectrum")
plt.xlabel("Frequency (Hz)")
plt.ylabel("Magnitude")
plt.show()
```

Explanation:

* FFT calculates contribution of each frequency
* We plot only positive frequencies
* Magnitude shows strength of each component

This is exactly how spectrum analyzers work.

---

## 🎥 [8:30 – 10:00] — Interpreting the Output

When you run this, you will see peaks.

Where?

Near:

5 Hz
15 Hz
40 Hz

This confirms something profound:

Even though time domain looked messy, the signal was structured.

Frequency domain revealed the truth.

If amplitudes were different, peak heights would change.

If noise were added, peaks would still emerge — but with background variation.

This is the foundation of detection systems used in RF receivers and telescopes.

---

## 🎥 [10:00 – 11:15] — MATLAB Equivalent (Brief)

In MATLAB, the process is identical.

Core commands:

* sin()
* fft()
* abs()
* plot()

Students can replicate the same experiment using:

```matlab
fft_vals = fft(signal);
```

The interpretation remains the same.

Software changes.
Signal theory does not.

---

## 🎥 [11:15 – 12:00] — Closing Insight

Today you observed something fundamental:

A complex waveform is often a combination of simple oscillations.

FFT does not invent frequencies.
It reveals what already exists.

This single idea powers:

* Audio compression
* Wireless communication
* Medical diagnostics
* Radar
* Radio astronomy

In the next practical session, we will intentionally break things.

We will sample signals incorrectly and observe aliasing.

That’s where real engineering mistakes begin.

Welcome back to **Signals to Stars — Practical Series**.

---

If you want next, I can provide:

✅ Episode 3 lecture script (Sampling mistakes)
✅ Practical 3 aliasing demo
✅ Ready Colab notebook template
✅ Visual overlays for editing
✅ Assignment questions for students

Just tell me 👍

If you want next, I can provide:

✅ Episode 3 lecture script (Sampling mistakes)
✅ Practical 3 aliasing demo
✅ Ready Colab notebook template
✅ Visual overlays for editing
✅ Assignment questions for students

Just tell me 👍
If you want next, I can provide:

✅ Episode 3 lecture script (Sampling mistakes)
✅ Practical 3 aliasing demo
✅ Ready Colab notebook template
✅ Visual overlays for editing
✅ Assignment questions for students

Just tell me 👍
If you want next, I can provide:

✅ Episode 3 lecture script (Sampling mistakes)
✅ Practical 3 aliasing demo
✅ Ready Colab notebook template
✅ Visual overlays for editing
✅ Assignment questions for students

Just tell me 👍
If you want next, I can provide:

✅ Episode 3 lecture script (Sampling mistakes)
✅ Practical 3 aliasing demo
✅ Ready Colab notebook template
✅ Visual overlays for editing
✅ Assignment questions for students

Just tell me 👍
If you want next, I can provide:

✅ Episode 3 lecture script (Sampling mistakes)
✅ Practical 3 aliasing demo
✅ Ready Colab notebook template
✅ Visual overlays for editing
✅ Assignment questions for students

Just tell me 👍
If you want next, I can provide:

✅ Episode 3 lecture script (Sampling mistakes)
✅ Practical 3 aliasing demo
✅ Ready Colab notebook template
✅ Visual overlays for editing
✅ Assignment questions for students

Just tell me 👍
If you want next, I can provide:

✅ Episode 3 lecture script (Sampling mistakes)
✅ Practical 3 aliasing demo
✅ Ready Colab notebook template
✅ Visual overlays for editing
✅ Assignment questions for students

Just tell me 👍
If you want next, I can provide:

✅ Episode 3 lecture script (Sampling mistakes)
✅ Practical 3 aliasing demo
✅ Ready Colab notebook template
✅ Visual overlays for editing
✅ Assignment questions for students

Just tell me 👍
