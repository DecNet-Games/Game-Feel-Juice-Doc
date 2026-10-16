---
layout: default
title: Audio Polish & DSP Ducking
parent: Features & API Reference
nav_order: 7
---

# 🔊 Zero-GC Spatial Audio & DSP Ducking
{: .no_toc }

Audio provides 50% of game feel. PULSE includes a complete procedural audio engine optimized for zero heap allocations.
{: .fs-6 .fw-300 }

---

## ⚡ Core Features

* **32 Pre-Warmed Channels**: Audio sources are pooled on startup—never instantiate an `AudioSource` at runtime.
* **Smart Pitch & Volume Detuning**: Random variations prevent "machine-gun" audio ear fatigue.
* **Dynamic Low-Pass DSP Ducking**: Smoothly muffles world audio during slow-motion, death, or underwater scenes.

---

## 💻 Code Examples

### 1. Play One-Shot Audio with Pitch Variation
```csharp
using DecnetGames.Pulse;
using UnityEngine;

public AudioClip gunshotSound;

// Procedural pitch randomization (+/- 10%)
Pulse.Audio.PlayOneShot(gunshotSound, volume: 1.0f, pitchVariation: 0.1f);
```

### 2. Spatial 3D Audio at World Position
```csharp
// Plays audio at explosion position with 3D attenuation
Pulse.Audio.Play(soundDef, explosionPosition);
```

### 3. Dynamic Low-Pass Ducking (Muffle Effect)
```csharp
// Temporarily muffle world audio for 0.6 seconds (e.g., near-miss explosion)
Pulse.Audio.Duck(duration: 0.6f);

// Toggle low-pass filter permanently (e.g., when player pauses or enters water)
Pulse.Audio.SetLowPass(muffled: true);
```
