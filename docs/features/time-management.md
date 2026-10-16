---
layout: default
title: HitStop & Slow-Motion
parent: Features & API Reference
nav_order: 4
---

# ⏱️ Frame-Perfect HitStop & Slow-Motion
{: .no_toc }

Control the temporal flow of your game with microsecond accuracy to deliver visceral crunch and cinematic bullet-time.
{: .fs-6 .fw-300 }

---

## 🛑 HitStop (Impact Frame Freeze)

HitStop temporarily freezes scene time on sword slashes, bullet impacts, or parries. This lets the player's brain register the contact, multiplying perceived impact force tenfold.

### 💻 1-Line Code Usage
```csharp
using DecnetGames.Pulse;

// Freeze frame for 80 milliseconds (standard AAA melee crunch)
Pulse.HitStop(duration: 0.08f);

// Heavy boss impact hitstop
Pulse.HitStop(duration: 0.15f);
```

---

## 🌑 Slow-Motion Bullet-Time

Smoothly transitions into slow motion and restores time scale without physics jitter.

### 💻 1-Line Code Usage
```csharp
// Transition to 30% speed for 1.0 second with default easing
Pulse.SlowMo(timeScale: 0.3f, duration: 1.0f);

// Custom cubic ease-in and ease-out curves
Pulse.SlowMo(timeScale: 0.2f, duration: 2.0f, easeIn: 0.15f, easeOut: 0.3f);

// Immediately cancel active slow motion
Pulse.SlowMoStop(easeOut: 0.2f);
```

---

## ⚙️ Physics & Audio Synchronization

* **`fixedDeltaTime` Sync**: Automatically scales `Time.fixedDeltaTime` during time-warps to keep Unity physics simulation stable and prevent clipping.
* **DSP Audio Low-Pass Auto-Muffle**: Automatically engages the audio filter during SlowMo so sound effects lower in pitch and muffle realistically.
