---
layout: default
title: TextMeshPro Damage Popups
parent: Features & API Reference
nav_order: 8
---

# 🏷️ Floating Combat Damage Popups
{: .no_toc }

Render pooled, billboarded TextMeshPro combat numbers with physics-accurate parabolic trajectories.
{: .fs-6 .fw-300 }

---

## 💻 1-Line Code Usage

```csharp
using DecnetGames.Pulse;
using UnityEngine;

Vector3 hitPoint = enemyTransform.position + Vector3.up * 1.5f;

// 1. Regular Damage Number
Pulse.Text.SpawnDamage(damage: 45, hitPoint, isCritical: false);

// 2. Critical Strike Popup (larger bounce & distinctive color)
Pulse.Text.SpawnDamage(damage: 180, hitPoint, isCritical: true);

// 3. Healing Popup (green floating number)
Pulse.Text.SpawnHeal(healAmount: 50, playerTransform.position);

// 4. Custom Text (e.g., "MISS", "BLOCKED", "LEVEL UP")
Pulse.Text.Spawn("BLOCKED!", hitPoint);
```

---

## ⚙️ Trajectory & Pooling Features

* **Vertical Rise**: Floats upward smoothly with exponential decay.
* **Parabolic Bounce**: Simulates gravity bounce arcs (left/right random scatter).
* **Sine Wave Drift**: Drifts with oscillating frequency for magical floating buffs.
* **100% Pre-Warmed Pooling**: Zero runtime GC allocations when spawning dozens of numbers per second.
