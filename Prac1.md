# Signals to Stars  
## Practical 1A — Visualizing Signals in Time Domain

---

## 🎯 Objective

In this practical session, we move from theory to visualization.

We will:

- Generate a sine wave  
- Generate a square wave  
- Generate random noise  
- Plot signals in the time domain  
- Add noise to a sine wave and observe distortion  

This practical demonstrates the core idea from Lecture 1:

> A signal is variation that carries information.

---

## 🧠 Concept Overview

We simulate three fundamental signal types:

### 1. Sine Wave
- Deterministic  
- Periodic  
- Ideal representation of structured information  

### 2. Square Wave
- Digital switching behavior  
- Contains multiple frequency components  
- Common in embedded and communication systems  

### 3. Random Noise
- Unpredictable variation  
- Present in all real-world systems  
- Degrades signal quality  

Finally, we combine signal and noise to simulate realistic measurements.

---

## 🛠 Software Requirements

- Python (recommended via Anaconda or Google Colab)

### Required Libraries
- NumPy  
- Matplotlib  
- SciPy  

Install if needed:

```bash
pip install numpy matplotlib scipy
```




Perfect. This is **Practical 1A** — it should feel structured, professional, and calm.
Not chaotic coding. Not rushed typing. You’re guiding engineers.

Below is a **~12-minute practical session script** aligned with Episode 1.

---

# 🎬 Signals to Stars

## Practical 1A — Visualizing Signals in Time Domain

---

## 🎥 [0:00 – 1:20] — Opening + Context

Hello everyone,
Welcome back to **Signals to Stars**.

I’m Sahil Sawant.

In the previous lecture, we discussed something very important:

> A signal is variation that carries information.

We understood signals as physical variations — voltage, light intensity, pressure, electromagnetic fields.

But today, we move from concept to visualization.

Because unless you see a signal,
you never truly understand it.

So in this practical session, we will:

* Generate a sine wave
* Generate a square wave
* Generate random noise
* Plot them in the time domain
* Then add noise to a sine wave and observe distortion

We will use Python for demonstration, but the logic applies exactly the same in MATLAB.

Let’s begin.

---

# 🎥 [1:20 – 2:30] — Concept Before Code

Before we write code, let’s understand what we’re doing.

We are going to simulate three types of signals:

1️⃣ A pure sine wave → deterministic, periodic
2️⃣ A square wave → digital-like switching behavior
3️⃣ Random noise → unpredictable variation

And then we will combine signal + noise.

Why?

Because real-world signals are never perfectly clean.

Every engineering system deals with noise.

This practical shows visually what we discussed theoretically.

---

# 🎥 [2:30 – 4:00] — Step 1: Importing Libraries

Now let’s move to code.

We’ll use:

* NumPy → for numerical computation
* Matplotlib → for plotting

```python
import numpy as np
import matplotlib.pyplot as plt
```

What does this do?

* NumPy allows us to create arrays and mathematical signals.
* Matplotlib helps us visualize signals in time domain.

Simple. Clean.

---

# 🎥 [4:00 – 5:30] — Step 2: Create a Time Axis

A signal needs time.

We define:

* Sampling frequency
* Duration
* Time array

```python
fs = 1000        # Sampling frequency (samples per second)
t = np.linspace(0, 1, fs)   # Time from 0 to 1 second
```

Explanation:

* fs = 1000 means we are taking 1000 samples per second.
* np.linspace creates evenly spaced time values.

Remember:

> A signal is variation with respect to time.

So time must exist first.

---

# 🎥 [5:30 – 6:45] — Step 3: Generate a Sine Wave

Now we generate a sine wave of 5 Hz.

```python
f = 5   # Frequency in Hz
sine_wave = np.sin(2 * np.pi * f * t)
```

Explanation:

The formula:

sin(2πft)

This gives a periodic oscillation.

Now let’s plot it.

```python
plt.figure()
plt.plot(t, sine_wave)
plt.title("Sine Wave")
plt.xlabel("Time")
plt.ylabel("Amplitude")
plt.show()
```

🔎 What should you observe?

* Smooth oscillation
* Perfect periodic pattern
* Clean waveform

This is an ideal signal.

In textbooks, most signals look like this.

In reality? Rarely.

---

# 🎥 [6:45 – 7:45] — Step 4: Generate a Square Wave

Now we generate a square wave.

```python
from scipy import signal
square_wave = signal.square(2 * np.pi * f * t)
```

Plot it:

```python
plt.figure()
plt.plot(t, square_wave)
plt.title("Square Wave")
plt.xlabel("Time")
plt.ylabel("Amplitude")
plt.show()
```

🔎 What do you see?

* Sudden transitions
* Sharp edges
* Digital-like switching

This resembles:

* Clock signals
* Digital systems
* PWM signals

Important insight:

Square waves are not smooth — they contain multiple frequency components.

We’ll explore that in later episodes.

---

# 🎥 [7:45 – 8:45] — Step 5: Generate Random Noise

Now we generate noise.

```python
noise = np.random.normal(0, 0.5, fs)
```

Explanation:

* Mean = 0
* Standard deviation = 0.5
* fs samples

Plot it:

```python
plt.figure()
plt.plot(t, noise)
plt.title("Random Noise")
plt.xlabel("Time")
plt.ylabel("Amplitude")
plt.show()
```

🔎 What do you observe?

* No pattern
* No periodicity
* Completely unpredictable

This is noise.

And noise exists in every system:

* Thermal noise
* Electronic interference
* Cosmic background radiation

---

# 🎥 [8:45 – 10:00] — Step 6: Add Noise to Sine Wave

Now the important part.

Real-world signals are not clean.

Let’s combine sine wave + noise.

```python
noisy_signal = sine_wave + noise
```

Plot it:

```python
plt.figure()
plt.plot(t, noisy_signal)
plt.title("Sine Wave with Noise")
plt.xlabel("Time")
plt.ylabel("Amplitude")
plt.show()
```

🔎 What do you see?

* The sine wave is still there.
* But it’s distorted.
* The waveform looks rough.

This is a realistic signal.

And this is what engineers actually process.

---

# 🎥 [10:00 – 11:00] — Interpretation

Now pause and think.

In the first lecture, I said:

> A signal is variation that carries information.

Here:

* The sine wave carries structured information.
* The noise does not carry meaningful information.
* But noise corrupts the signal.

Signal processing is the art of:

1. Detecting signal
2. Separating signal from noise
3. Recovering useful information

What you just created is a simplified version of:

* Radio reception
* Biomedical signal acquisition
* Astronomical measurements

This is not toy coding.

This is engineering reality.

---

# 🎥 [11:00 – 12:00] — Closing + Assignment

Before ending this session, I want you to try:

🔹 Increase noise amplitude
🔹 Change sine frequency
🔹 Reduce sampling frequency
🔹 Observe how waveform changes

Ask yourself:

* When does signal become unrecognizable?
* When does noise dominate?
* Can you still visually detect the sine?

In the next practical, we will move to frequency domain.

And you will see something powerful:

Even if the signal looks messy in time domain,
it may be clear in frequency domain.

That’s where Fourier enters.

Until then — experiment.

Signals are not to be memorized.

They are to be explored.

See you in Practical 1B.

---

---

# 🎓 Professional Tip for Recording

* Use dark theme IDE
* Increase font size
* Zoom in on plots
* Slow typing, explain while writing
* Keep screen clean

---

If you want next:

* I can prepare **Practical 1B: FFT visualization**
* Or create a **student assignment sheet PDF**
* Or design a **GitHub repo structure for this course**

Your engineering classroom is officially live. 🚀
