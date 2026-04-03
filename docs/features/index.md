---
layout: default
title: Features
nav_order: 4
has_children: true
---

# Feature Deep Dive
{: .no_toc }

Explore the technical details and advanced usage of every module in the **Game Feel & Juice System**.

---

## 🛠️ Module Overview

The system is built on a modular "Plugin" architecture. Each module is independent and can be enabled or disabled via the **Juice Manager**.

### [Camera Shake](./camera-shake)
Trauma-based shaking for realistic physics-driven feedback. Learn how to use "Trauma" to create dynamic oscillations.

### [Time Management](./time-management)
HitStop and SlowMo effects. Master the art of "Impact" using millisecond-perfect time scale manipulation.

### [Renderer Flash](./renderer-flash)
The most efficient way to flash sprites and meshes. Uses `MaterialPropertyBlock` for zero-allocation visuals.

### [Ghosting Trails](./ghosting-trails)
Create phantom "After-Image" trails for high-speed characters.

### [UI Juice](./ui-juice)
Add feedback to your interface with animated buttons, scales, and pulses.

---

## 👨‍💻 Deep Technical Details

### Reflection & IL Weaving
The system uses lightweight reflection during initial setup to auto-discover active modules. This reduces manual setup and ensures high-performance runtime execution.

### MaterialPropertyBlock (MPB)
To avoid the "Material Inflation" bug in Unity (where accessing `renderer.material` creates a leak), the **FlashModule** uses MPB. This is the gold standard for production performance.

### Managed Pooling
Ghosting trails and particles are managed via a high-speed internal pooling system to keep GC at zero in high-action scenarios.
