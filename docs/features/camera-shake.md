---
layout: default
title: Camera Shake & FOV Zoom
parent: Features & API Reference
nav_order: 2
---

# 🎥 Trauma-Based Camera Shake & Polish
{: .no_toc }

Based on the industry-standard trauma model ($Trauma^2$ / $Trauma^3$ decay), PULSE delivers natural, physical screen shake that never clips or disorients players.
{: .fs-6 .fw-300 }

---

## 🌪️ The Trauma System

Most legacy camera shakes are linear (simple Perlin noise that fades abruptly). PULSE uses physical **Trauma**:
* **Trauma Range**: Normalized value from $0.0$ to $1.0$.
* **Non-Linear Quadratic Decay**: $Shake = Trauma^2$ or $Trauma^3$. Stacking multiple explosions produces smooth escalation instead of violent jarring.
* **Perlin Frequency Modulation**: Decays smoothly back to zero without offset drift.

---

## 💻 1-Line Code Usage

### 1. Trauma Screen Shake
```csharp
using DecnetGames.Pulse;

// Standard trauma shake
Pulse.ScreenShake(trauma: 0.5f);

// Heavy explosion shake with custom max offset and frequency
Pulse.ScreenShake(trauma: 0.85f, maxOffset: 0.8f, frequency: 30f);

// Immediately stop active screen shake
Pulse.ScreenShakeStop();
```

### 2. Directional Camera Recoil Punch
```csharp
using UnityEngine;

// Recoil kick along firing direction
Vector2 recoilDir = new Vector2(-0.2f, 0.4f);
Pulse.CameraPunch(recoilDir, strength: 0.4f, duration: 0.2f);
```

### 3. Dynamic FOV / Ortho Zoom-Punch
```csharp
// Instant FOV kick on critical hit with smooth exponential return
Pulse.CameraZoomKick(fovDelta: -5f, duration: 0.25f);
```

---

## 🔌 Cinemachine 2.x & 3.x Auto-Bridge

PULSE includes an automated adapter for Cinemachine:
* When `com.unity.cinemachine` is installed, `CinemachineShakeAdapter` automatically binds to your active `CinemachineVirtualCamera` or `CinemachineBrain`.
* Drives the virtual camera's `CinemachineBasicMultiChannelPerlin` noise channels seamlessly.
* Zero manual wiring required—fallback to standard Unity Camera is automatic if Cinemachine is absent.
