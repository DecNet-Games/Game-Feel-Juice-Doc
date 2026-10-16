---
layout: default
title: Volume Squash, Stretch & Wobble
parent: Features & API Reference
nav_order: 3
---

# 🧪 Volume-Conserving Squash, Stretch & Wobble
{: .no_toc }

Physical realism requires volume conservation. When a mass compresses in one axis, it must expand in perpendicular axes.
{: .fs-6 .fw-300 }

---

## 📐 Conservation Physics

When characters squash or stretch, PULSE automatically calculates the exact perpendicular dimensions:

* **In 2D Sprites ($Area = S_x \cdot S_y = 1$):**
  $$S_y = \frac{1}{S_x}$$
* **In 3D Meshes ($Volume = S_x \cdot S_y \cdot S_z = 1$):**
  $$S_\perp = \frac{1}{\sqrt{S_\parallel}}$$

This prevents models from looking deflated or rubbery—they retain physical mass.

---

## 💻 Code Examples

### 1. Volume Squash & Stretch
```csharp
using DecnetGames.Pulse;

// Ground landing squash (flattens vertically, bulges horizontally)
Pulse.Motion.Squash(transform, factor: 0.7f, axis: Vector3.up, duration: 0.25f);

// Jump stretch (elongates vertically, narrows horizontally)
Pulse.Motion.Stretch(transform, factor: 1.35f, axis: Vector3.up, duration: 0.3f);
```

### 2. Arbitrary Impact Axes
```csharp
// Squash against an angled wall or slope normal
Vector3 wallNormal = hit.normal;
Pulse.Motion.Squash(transform, factor: 0.65f, axis: wallNormal, duration: 0.2f);
```

### 3. Decaying Sinusoidal Wobble / Jiggle
```csharp
// 3D Rotational jiggle on heavy impact
Pulse.Motion.Wobble(transform, amplitude: new Vector3(10f, 15f, 5f), frequency: 25f, duration: 0.4f);

// 2D Angular wobble around Z-axis (ideal for 2D sprites & UI)
Pulse.Motion.Wobble2D(transform, angleDegrees: 20f, frequency: 30f, duration: 0.35f);
```
