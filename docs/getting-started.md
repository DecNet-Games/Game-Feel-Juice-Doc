---
layout: default
title: Getting Started
nav_order: 3
---

# Getting Started with PULSE
{: .no_toc }

## Kickstart Your Game Feel in Under 60 Seconds
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## ⚡ The PULSE Static API Facade

**PULSE** is architected around a unified, ultra-clean static facade: `Juice`. You never need to manage messy singleton references or invoke heavy `GetComponent<T>()` lookups at runtime. Call any game feel effect from anywhere in your C# codebase:

```csharp
using DecNetGames.PULSE;
```

---

## 1. Screen & Directional Shake

Add immediate cinematic weight to explosions, shotgun blasts, and boss stomps using our quadratic trauma model:

```csharp
// 1. Add trauma (0.0 to 1.0) with squared decay
Juice.Shake(0.6f);

// 2. Directional trauma kick (great for weapon recoil or physical collisions)
Juice.Shake(new Vector3(0.8f, 0.2f, 0f), 0.5f);
```

> [!NOTE]
> **Why Trauma Model?** Shaking with raw `Random.insideUnitSphere` feels jittery and disconnected. PULSE uses Perlin noise driven by a `Trauma²` decay curve, ensuring layered impacts blend smoothly without jarring camera flips.

---

## 2. HitStop (Micro-Freezes)

Nothing conveys physical weight like an intentional frame freeze when a blade connects with armor:

```csharp
// Freeze game time for 80 milliseconds (with automatic unscaled restore)
Juice.Time.HitStop(0.08f);
```

---

## 3. Slow-Motion Dynamics

Perfect for tactical pauses, parry windows, bullet-time, or cinematic boss death blows:

```csharp
// Drop time to 15% speed for 1.2 real seconds, with smooth cubic easing recovery
Juice.Time.SlowMo(0.15f, 1.2f);
```

---

## 4. 2nd-Order Spring Dynamics

Make transforms, indicators, and UI elements squishy, alive, and interactive using exact harmonic equations:

```csharp
// Target position with spring parameters (frequency = 12f, damping = 0.5f, response = 1.0f)
Juice.Spring.Position(transform, targetPosition, 12f, 0.5f);

// Quick punch/impulse spring
Juice.Spring.PunchScale(transform, new Vector3(1.4f, 0.7f, 1.4f), 15f, 0.4f);
```

---

## 5. Audio Juice & Pitch Detuning

Avoid machine-gun repetition fatigue with automatic spatial routing and pitch variance:

```csharp
// Play one-shot sound with ±15% procedural pitch variation
Juice.Audio.Play(explosionAudioClip, pitchVariance: 0.15f);

// Trigger full audio juice with low-pass DSP ducking
Juice.Audio.PlayDuck(hitSound, duckDuration: 0.25f, cutoffFrequency: 800f);
```

---

## 6. Floating Combat Text

Spawn high-performance, object-pooled damage numbers and status notifications:

```csharp
// Standard damage popup
Juice.Text.Spawn(hitPoint, "1,450", Color.white);

// Critical hit with bounce animation & golden color
Juice.Text.SpawnCritical(hitPoint, "CRIT! 4,890", Color.yellow);
```

---

## 🏗️ Architecture Overview

PULSE separates runtime logic into zero-overhead specialized modules:

| Module | Core Responsibility | Allocation Profile |
| :--- | :--- | :--- |
| **ShakeModule** | Quadratic trauma Perlin shake & directional punch | **0 KB GC** (Perlin cache) |
| **TimeModule** | Unscaled coroutine-driven HitStop & eased SlowMo | **0 KB GC** (Cached Yield) |
| **SpringModule** | 2nd-order harmonic spring integration (Euler/Verlet) | **0 KB GC** (Struct states) |
| **SquashStretchModule** | Volume-preserving mesh & sprite deformation | **0 KB GC** (Transform matrix) |
| **AudioJuiceModule** | 32-channel pooled audio playback & DSP ducking | **0 KB GC** (Pre-warmed pool) |
| **FloatingTextModule** | TextMeshPro billboard pooling & physics arches | **0 KB GC** (Recycled instances) |
| **GhostingModule** | Phantom mesh snapshots & alpha fading | **0 KB GC** (Mesh ring pool) |
| **TimeRewindModule** | Circular ring buffer state rewind & playback | **0 KB GC** (Fixed capacity) |

---

## 🚀 Next Steps

- [Installing & Configuring PULSE](./installation)
- [Mastering Spring Physics](./features/spring-physics)
- [Volume-Preserving Squash & Stretch](./features/squash-and-stretch)
- [Explore the 50+ Preset Catalog](./features/editor-tools-and-presets)
