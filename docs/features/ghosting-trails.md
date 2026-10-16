---
layout: default
title: Ghosting Dash Trails
parent: Features & API Reference
nav_order: 10
---

# 👻 Ghosting After-Image Dash Trails
{: .no_toc }

Render high-performance after-image trails for sprints, dashes, and teleports using pre-warmed mesh pooling.
{: .fs-6 .fw-300 }

---

## ⚡ How It Works

* **Snapshot Capture**: Bakes current mesh/sprite pose and world transform into pooled mesh renderer instances.
* **Zero Allocation**: Avoids garbage collection during high-speed combat.
* **Alpha Decay**: Smoothly fades out with custom tint colors and customizable lifetime.

---

## 💻 1-Line Code Usage

```csharp
using DecnetGames.Pulse;
using UnityEngine;

public Renderer playerRenderer;

// Spawn an after-image ghost with custom cyan tint and 0.25s lifetime
Pulse.VFX.Ghost(playerRenderer, tint: Color.cyan, duration: 0.25f);

// Default ghost snapshot
Pulse.Ghost(playerRenderer);
```
