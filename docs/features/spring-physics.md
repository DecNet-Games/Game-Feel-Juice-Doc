---
layout: default
title: Spring Physics & Oscillators
parent: Features & API Reference
nav_order: 1
---

# 🌀 2nd-Order Harmonic Spring Physics
{: .no_toc }

Say goodbye to robotic linear tweens. PULSE includes a full mathematical 2nd-order differential harmonic oscillator physics engine.
{: .fs-6 .fw-300 }

---

## 📐 The Physics Model

PULSE solves the classic 2nd-order linear differential oscillator equation in real-time with sub-millisecond precision:

$$\ddot{y} + 2\zeta \omega_n \dot{y} + \omega_n^2 y = \omega_n^2 x + 2\zeta \omega_n r \dot{x}$$

Where:
* $f$ = **Natural Frequency**: Speed and snap of the oscillation.
* $\zeta$ = **Damping Ratio**:
  * $\zeta = 0$: Undamped (perpetual oscillation).
  * $0 < \zeta < 1$: Underdamped (bouncy overshoot).
  * $\zeta = 1$: Critically damped (snappy return with zero overshoot).
  * $\zeta > 1$: Overdamped (smooth, gentle deceleration).
* $r$ = **Initial Response**: Controls initial velocity reaction to impulses.

---

## 💻 1-Line Code Usage

### 1. Transform Scale Punch & Springs
```csharp
using DecnetGames.Pulse;
using UnityEngine;

// Quick Snappy Scale Punch
Pulse.Spring.PunchScale(transform, punchAmount: 0.35f, SpringMode.Snappy);

// Bouncy Scale Spring with onComplete callback
Pulse.Spring.Scale(transform, impulseScale: new Vector3(1.4f, 1.4f, 1.4f), SpringMode.Bouncy, () => {
    Debug.Log("Spring completed!");
});
```

### 2. Positional & Rotational Springs
```csharp
// Recoil impulse returning smoothly to original position
Pulse.Spring.Position(transform, offsetImpulse: new Vector3(0, 0, -0.5f), SpringMode.Snappy);

// Angular kick spring
Pulse.Spring.Rotation(transform, eulerOffset: new Vector3(15f, 0, 0), SpringMode.Bouncy);
```

### 3. Native UI Springs (RectTransform & CanvasGroup)
```csharp
using DecnetGames.JuiceSystem;

// UI Button punch
Juice.Spring.AnchoredPosition(rectTransform, impulsePos: new Vector2(0, -10f), restPos: Vector2.zero, SpringSettings.GetPreset(SpringMode.Snappy));

// CanvasGroup Fade Spring
Juice.Spring.Alpha(canvasGroup, impulseAlpha: 0.2f, restAlpha: 1.0f, SpringSettings.GetPreset(SpringMode.Gentle));
```

---

## 🎛️ Interactive Spring Visualizer Studio

Open the visualizer directly in Unity:
**Tools > Pulse Engine > Spring Dynamics Studio**

* Drag damping, frequency, and response sliders.
* Watch the live mathematical curve update in real time.
* Test directly on selected scene transforms before writing any code.
