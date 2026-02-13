# 🎬 Signals to Stars

## Episode 5: Noise — The Invisible Enemy

---

## 🎥 [0:00 – 1:20] — Introduction + Recap

Hello everyone,
I’m **Sahil Sawant**, currently pursuing my M.Tech in Computer Engineering at VJTI Mumbai, with a background in Electronics and Telecommunication and research experience in RF systems and radio astronomy.

In Episode 1, we understood:

> A signal is variation that carries information.

In Episode 2, we explored time vs frequency domain.

In Episode 3, we saw how incorrect sampling creates aliasing.

In Episode 4, we discussed spectral leakage — how finite observation distorts frequency analysis.

Today, we talk about something far more fundamental.

Something that exists in every real system.

Noise.

---

## 🎥 [1:20 – 2:30] — What Is Noise?

Textbooks define noise as:

> Any unwanted disturbance that corrupts a signal.

But let’s understand this physically.

Noise is not an accident.

Noise is natural.

It comes from:

* Thermal motion of electrons
* Imperfect components
* Atmospheric disturbances
* Cosmic background radiation
* Quantization in ADCs

Even if your system is perfect,
nature itself introduces noise.

Noise is the cost of reality.

---

## 🎥 [2:30 – 3:45] — A Simple Example

Imagine you're trying to hear someone whisper in a crowded room.

The whisper is your signal.

The crowd chatter is noise.

Now imagine trying to detect a weak radio signal from the Sun.

The Sun emits weak bursts.

But your receiver also picks up:

* Thermal noise from electronics
* Man-made interference
* Background cosmic radiation

Separating signal from noise becomes the real challenge.

Signal processing is often noise management.

---

## 🎥 [3:45 – 5:00] — Types of Noise (Intuitive View)

Let’s classify noise in simple terms.

### 1️⃣ Thermal Noise

Also called Johnson-Nyquist noise.

Caused by random motion of electrons.

Exists in every resistor.

Cannot be eliminated.

Only reduced.

---

### 2️⃣ Shot Noise

Occurs due to discrete nature of charge carriers.

Important in semiconductors and photodetectors.

---

### 3️⃣ Environmental Noise

* Power line interference
* RF interference
* EMI

---

### 4️⃣ Quantization Noise

Occurs during analog-to-digital conversion.

Because digital systems approximate continuous values.

Noise is everywhere — from physics to digital systems.

---

## 🎥 [5:00 – 6:15] — Gaussian Noise (Why It Appears Everywhere)

In many engineering systems, noise appears Gaussian.

Why?

Because of the Central Limit Theorem.

When many small independent disturbances combine,
their sum tends to form a Gaussian distribution.

That’s why we model noise as:

Additive White Gaussian Noise (AWGN).

“White” means equal power at all frequencies.

“Additive” means it adds to signal.

“Gaussian” means its amplitude distribution follows bell curve.

This model simplifies analysis.

---

## 🎥 [6:15 – 7:15] — Signal-to-Noise Ratio (SNR)

Now we introduce one of the most important metrics:

Signal-to-Noise Ratio.

SNR = Signal Power / Noise Power

Usually expressed in decibels:

SNR (dB) = 10 log10 (Signal Power / Noise Power)

Higher SNR → cleaner signal
Lower SNR → buried signal

If SNR is too low,
your system becomes unreliable.

In communication systems:
Low SNR → bit errors.

In biomedical systems:
Low SNR → misdiagnosis.

In astronomy:
Low SNR → false detections.

---

## 🎥 [7:15 – 8:30] — Visual Intuition

Imagine plotting a clean sine wave.

Now start adding noise gradually.

At first:
Signal is clear.

Then:
Signal becomes distorted.

Eventually:
Signal becomes indistinguishable.

That threshold is SNR-dependent.

Engineers must design systems to operate above acceptable SNR levels.

---

## 🎥 [8:30 – 9:30] — Noise in Radio Astronomy (Authority Moment)

Let me connect this to radio astronomy.

When observing weak cosmic signals,
the received power is extremely small.

Sometimes comparable to system noise.

So how do we detect real signals?

We:

* Integrate over time
* Average multiple samples
* Use narrowband filtering
* Apply statistical detection methods

Sometimes we observe for hours just to improve SNR.

That’s how serious noise can be.

---

## 🎥 [9:30 – 10:30] — Can We Eliminate Noise?

Short answer:

No.

We cannot eliminate thermal noise.

We can:

* Reduce bandwidth
* Improve amplifier design
* Use cooling systems (cryogenic receivers in astronomy)
* Increase signal power
* Use filtering
* Apply averaging

Engineering is not about removing noise.

It’s about designing around it.

---

## 🎥 [10:30 – 11:15] — Averaging: A Simple Noise Reduction Trick

If noise is random,
and signal is consistent,

Averaging multiple measurements reduces noise.

Because random components cancel out over time.

But this increases processing time.

Again — trade-offs.

Speed vs accuracy.

---

## 🎥 [11:15 – 11:40] — The Core Insight

If you remember one thing today:

> Noise is not a flaw.
> It is a fundamental part of physical systems.

Signal processing is not just transforming signals.

It is protecting information from noise.

---

## 🎥 [11:40 – 12:00] — Closing + Teaser

In the next episode, we move to something powerful:

Filters.

How do engineers selectively remove unwanted frequencies?

How do we design systems that allow signal to pass but block noise?

That’s where signal processing becomes engineering design.

Welcome back to **Signals to Stars**.

---
