Excellent.
Now we move into **real engineering design**.

This episode should feel practical, grounded, and slightly analytical — because this is where students begin to think like system designers.

Below is your structured **~12-minute lecture script**.

---

# 🎬 Signals to Stars

## Episode 6: Filters — FIR vs IIR (Engineering Trade-Offs)

---

## 🎥 [0:00 – 1:20] — Introduction + Recap

Hello everyone,
I’m **Sahil Sawant**, currently pursuing my M.Tech in Computer Engineering at VJTI Mumbai, with a background in Electronics and Telecommunication and research experience in RF systems and radio astronomy.

In this series so far:

* Episode 1: Signals are variation carrying information.
* Episode 2: Fourier reveals hidden frequency structure.
* Episode 3: Incorrect sampling causes aliasing.
* Episode 4: Finite observation causes spectral leakage.
* Episode 5: Noise is unavoidable — and SNR defines system performance.

Today, we move from analysis…

To design.

Today’s topic:

> Filters — and the engineering trade-off between FIR and IIR.

---

## 🎥 [1:20 – 2:30] — Why Filters Exist

Let’s ask a simple question:

Why do we need filters?

Because in real systems:

* Signals mix with noise.
* Multiple frequency components coexist.
* Systems have bandwidth limits.

A filter allows certain frequencies to pass
and suppresses others.

Examples:

* Audio equalizer
* RF band-pass filter
* ECG low-pass smoothing
* Anti-aliasing filter before ADC

Filters shape signals.

---

## 🎥 [2:30 – 3:45] — Types of Basic Filters (Quick Overview)

Before FIR vs IIR, let’s classify by behavior:

* Low-pass → passes low frequencies
* High-pass → passes high frequencies
* Band-pass → passes a frequency band
* Band-stop → rejects a frequency band

That’s functional classification.

Now we go deeper into structural classification.

---

## 🎥 [3:45 – 5:15] — FIR Filters (Finite Impulse Response)

Let’s start with FIR.

FIR stands for:

Finite Impulse Response.

That means:

If you apply an impulse input,
the output settles to zero in finite time.

Mathematically:

Output depends only on current and past inputs.

No feedback.

Structure:
y[n] = Σ b[k] x[n−k]

Important characteristics:

* Always stable
* Can achieve exact linear phase
* Usually requires more coefficients

Linear phase means:
All frequency components are delayed equally.

This preserves waveform shape.

That’s important in:

* Audio
* Biomedical signals
* Data communications

---

## 🎥 [5:15 – 6:30] — IIR Filters (Infinite Impulse Response)

Now IIR.

IIR stands for:

Infinite Impulse Response.

If you apply impulse input,
output theoretically continues forever.

Why?

Because IIR uses feedback.

Output depends on:

* Current input
* Past inputs
* Past outputs

Structure:
y[n] = Σ b[k] x[n−k] − Σ a[k] y[n−k]

Because of feedback,
IIR can achieve sharp filtering with fewer coefficients.

Advantages:

* Computationally efficient
* Requires lower order
* Faster roll-off

But…

They may become unstable.
And typically do not have linear phase.

---

## 🎥 [6:30 – 7:30] — Engineering Trade-Offs

Now we compare.

| Property       | FIR             | IIR               |
| -------------- | --------------- | ----------------- |
| Stability      | Always stable   | Can be unstable   |
| Phase Response | Linear possible | Usually nonlinear |
| Complexity     | Higher order    | Lower order       |
| Efficiency     | Slower          | Faster            |

So which one is better?

Wrong question.

Correct question:

Which one suits your application?

Engineering is about context.

---

## 🎥 [7:30 – 8:45] — Real-World Example: Audio Processing

In audio systems:

Waveform shape matters.

Phase distortion can change sound quality.

So FIR filters are preferred when linear phase is important.

But in real-time embedded systems:

Memory and CPU are limited.

IIR filters are computationally efficient.

So embedded control systems often use IIR.

---

## 🎥 [8:45 – 9:45] — RF & Communication Example

In RF systems:

Analog filters are often IIR-like in behavior.

Digital baseband processing may use IIR for efficiency.

But in data transmission systems:

Pulse shaping often uses FIR filters
because linear phase preserves symbol timing.

Again — trade-offs.

---

## 🎥 [9:45 – 10:45] — Stability: The Hidden Risk in IIR

Here’s something important.

IIR filters have poles.

If poles lie outside unit circle,
system becomes unstable.

Output grows without bound.

This is not theoretical.

Improper coefficient design can break real systems.

FIR filters don’t have this issue.

They are inherently stable.

Sometimes safety matters more than efficiency.

---

## 🎥 [10:45 – 11:15] — Computational Perspective

From implementation view:

FIR:

* More multiplications
* More memory
* Parallelizable easily

IIR:

* Fewer coefficients
* Feedback loop
* Sensitive to numerical precision

In fixed-point systems,
IIR rounding errors may accumulate.

Designers must consider hardware limitations.

---

## 🎥 [11:15 – 11:40] — The Core Insight

If you remember one thing:

> FIR vs IIR is not about which is superior.
> It is about understanding system requirements.

Do you need:

* Linear phase?
* Guaranteed stability?
* Low computational cost?
* Fast roll-off?

Your answer determines your filter choice.

That is engineering thinking.

---

## 🎥 [11:40 – 12:00] — Closing + Teaser

In the next episode, we go deeper into something fundamental:

Convolution and system response.

Because filters are just systems —
and convolution explains how systems shape signals.

Welcome back to **Signals to Stars**.

---

# 🎬 Suggested Visual Enhancements

* Animated frequency response plots
* Step response comparison (FIR vs IIR)
* Pole-zero diagram for IIR
* Linear vs nonlinear phase illustration
* Side-by-side filtering effect on noisy signal

---

If you’d like next:

* I can prepare Episode 7: Convolution & Impulse Response
* Or create a live coding demo structure for FIR vs IIR
* Or design a mini practical lab assignment for students

Now the course has moved from understanding signals…
to designing systems.

Exactly where engineers should be. 🚀
