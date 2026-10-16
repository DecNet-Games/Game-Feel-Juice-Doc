---
layout: default
title: GPU Shockwaves & Shaders
parent: Features & API Reference
nav_order: 6
---

# 💥 GPU Shockwaves, Screen Glitch & Flash
{: .no_toc }

Turn simple weapon impacts and explosions into visual spectacles without fill-rate bottlenecks.
{: .fs-6 .fw-300 }

---

## ⚡ Shaders Included in PULSE

1. **`JuiceShockwave.shader`**: High-performance radial screen refraction with chromatic aberration fringing (URP & Built-in).
2. **`JuiceScreenFlash.shader`**: Additive and multiplicative screen tinting.
3. **`JuiceGlitch.shader`**: Cyberpunk horizontal RGB channel splitting and scanline glitch.

---

## 💻 Code Usage

### 1. Radial World Shockwave
```csharp
using DecnetGames.Pulse;
using UnityEngine;

// Triggers a 3D expanding shockwave ring in world space
Pulse.VFX.Shockwave(explosionPosition, radius: 1.2f);
```

### 2. Screen Flash & Glitch
```csharp
// Full screen red damage flash
Pulse.VFX.ScreenFlash(Color.red, intensity: 0.8f, duration: 0.2f);

// Heavy impact glitch burst
Pulse.VFX.Glitch(intensity: 0.7f, duration: 0.25f);
```

### 3. Post-Processing Volume Bursts (URP & Built-in Stack v2)
```csharp
// Chromatic Aberration pulse
Pulse.VFX.ChromaticBurst(intensity: 1.0f, duration: 0.2f);

// Red damage vignette pulse
Pulse.VFX.VignettePulse(intensity: 0.5f, duration: 0.3f, Color.red);

// Lens distortion kick (concave zoom warp)
Pulse.VFX.LensDistortionKick(intensity: -0.4f, duration: 0.25f);

// Bloom flash on critical spell/explosion
Pulse.VFX.BloomFlash(intensity: 2.5f, duration: 0.2f);
```
