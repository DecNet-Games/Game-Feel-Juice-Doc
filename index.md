---
layout: default
title: Home
nav_order: 1
description: "Game Feel & Juice: The ultimate 'Wow Factor' toolkit for Unity developers."
permalink: /
---

# Game Feel & Juice System
{: .fs-9 }

Better game feel shouldn't take weeks. Stop manual work—automate the "Wow Factor" with a production-ready toolkit designed for professional Unity developers.
{: .fs-6 .fw-300 }

[Purchase on Asset Store](https://assetstore.unity.com/){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View Demo](https://decnet-games.github.io/Game-Feel-Juice-Doc/demo){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## The "Pain" vs. The "Solution"

| Manual Work (The Pain) | Juice System (The Solution) |
| :--- | :--- |
| **Boring Combat**: Attacks feel like paper. No impact, no weight. | **High-Impact Feedback**: Instant HitStop, SlowMo, and Screen Shake with one line of code. |
| **Floating Characters**: Movement feels disconnected from the world. | **Trauma-Based Motion**: Realistic camera leaning, punch-back, and movement juice. |
| **Static Visuals**: Renderers don't react to damage or interaction. | **Dynamic Rendering**: MaterialPropertyBlock-based flashes and high-performance ghosting trails. |
| **Complex Setup**: Spending hours wiring up event listeners for simple juice. | **Static API**: `Juice.Shake()` or `Juice.Time.SlowMo()`—call from anywhere instantly. |

---

## Core Features

### 🌪️ Trauma-Based Shake
Realistic, non-linear camera and object shaking using a trauma model. Perfect for explosions, land-mines, and heavy hits.

### ⏱️ Time-Warp Management
Precise HitStop (frame freezing) and SlowMo control that doesn't break your physics or logic.

### 👻 Ghosting Trails
High-performance "Phantom" trails for fast-moving characters. Zero-allocation rendering using advanced pooling.

### ⚡ Renderer Flashing
The most efficient way to flash renderers. Uses `MaterialPropertyBlock` to avoid material leakage and GC pressure.

---

## Quick Links

- [Installation Guide](./docs/installation)
- [Getting Started](./docs/getting-started)
- [API Reference](./docs/features/)
- [FAQ](./docs/faq)

> [!TIP]
> **Pro Tip**: Use the **Juice Manager** to globally toggle effects during performance testing.
