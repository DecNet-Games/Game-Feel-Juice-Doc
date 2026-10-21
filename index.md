---
layout: default
title: Home
nav_order: 1
description: "PULSE: The definitive AAA Game Feel & Polish Engine for Unity."
permalink: /
---

# PULSE — Game Feel & Polish Engine
{: .fs-9 }

Turn stiff, floaty prototypes into punchy, addictive gameplay with zero-GC 2nd-order harmonic springs, trauma-based screen shake, frame-perfect hitstop, volume-preserving squash & stretch, and 50+ battle-tested presets.
{: .fs-6 .fw-300 }

[Purchase on Asset Store](https://assetstore.unity.com/packages/tools/animation/pulse-aaa-game-feel-polish-engine-406136){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [Getting Started](./docs/getting-started){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## ⚡ The "Stiff Game" vs. "PULSE" Difference

| Default Stiff Unity | With PULSE Engine |
| :--- | :--- |
| **Floaty Combat**: Attacks feel like paper. No impact, zero tactile weight. | **Visceral Impact**: Frame-perfect HitStop, camera recoil punch, chromatic burst, and trauma shake in 1 line of code. |
| **Linear Tweens**: Robotic and rigid movement that feels artificial. | **2nd-Order Harmonic Springs**: Physical mass, damping ratio ($\zeta$), angular frequency ($f$), and overshoot dynamics. |
| **Mobile GC Stutters**: Constant heap allocations cause frame drops during firefights. | **Zero-GC Architecture**: Circular ring buffers, pooled audio channels, and MaterialPropertyBlock flash tints (0 B garbage). |
| **Manual Wiring Hell**: Days spent hooking up coroutines and component references. | **1-Line Static Facade**: Access everything globally via `Pulse.*` or `Juice.*`. |

---

## 💎 8 Powerhouse Core Modules

### 🌀 2nd-Order Harmonic Spring Physics
Exact mathematical damped harmonic oscillator physics driving Transforms and UI RectTransforms without keyframes.

### 🎥 Trauma-Based Camera Polish & Cinemachine
Squared trauma decay curve with directional kick, dynamic FOV zoom-punch, and auto-bridging to Cinemachine 2 & 3.

### ⏱️ Frame-Perfect HitStop & Time-Rewind
Microsecond-accurate freeze frames on heavy weapon impacts, smooth SlowMo easing, and built-in circular buffer Time-Rewind.

### 🧪 Volume-Conserving Squash & Stretch
Mathematical volume and area preservation ($S_x \cdot S_y = 1$ in 2D, $S_x \cdot S_y \cdot S_z = 1$ in 3D) along arbitrary impact vectors.

### 💥 GPU Impact VFX & Screen Shaders
Radial screen distortion shockwave shaders, chromatic aberration bursts, glitch blits, and zero-allocation renderer flashes.

### 🔊 Zero-GC Audio & DSP Low-Pass Ducking
32 pre-warmed audio channels, randomized pitch detuning ($1.0 \pm 0.1$), and dynamic low-pass DSP filter muffling.

### 🏷️ TextMeshPro Damage Popups & Drop-In UI
Pooled billboarded combat numbers and drop-in tactile UI components (`JuicyButton`, `JuicyHealthBar`, `JuicySlider`, `JuicyWindow`).

### 🎛️ Cyberpunk Dark Tech Editor Suite
Central Command Dashboard, 1-Click Scene Setup Doctor, Interactive Spring Visualizer, and Scene View Floating HUD.

---

## 📚 Quick Documentation Links

- [Installation & Setup](./docs/installation)
- [Quick Start Guide](./docs/getting-started)
- [Features & API Reference](./docs/features/)
- [Interactive Demo Showcases](./docs/demos)
- [Frequently Asked Questions](./docs/faq)
