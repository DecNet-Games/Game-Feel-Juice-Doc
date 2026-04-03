---
layout: default
title: Ghosting Trails
parent: Features
nav_order: 4
---

# Ghosting Trails
{: .no_toc }

## High-Speed Phantom Effects
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 👻 After-Image Generation
Ghosting trails (often called "Phantoms" or "After-Images") are essential for highlighting fast player movement, dashes, or special attacks.

### 📈 How it Works
1.  **Mesh Snapshot**: When an object moves fast enough, the system takes a "Snapshot" of the current mesh/sprite and its position.
2.  **Pooling**: These snapshots are pooled (recycled) to prevent memory allocation during action.
3.  **Fading**: Each ghost fades out based on a custom alpha curve.

---

## 💻 API Usage

### One-Shot Sequence
Triggers a burst of ghosts for a single dash action.
```csharp
Juice.Ghosting.Spawn(targetObject, 5, 0.05f); // 5 ghosts, every 0.05 seconds
```

### Sustained Ghosting
Enable for a duration (e.g., during "Power-Up" mode).
```csharp
Juice.Ghosting.Enable(targetObject, 2.0f); // Spawn ghosts for 2 seconds
```

---

## ⚙️ Advanced Settings

| Field | Description |
| :--- | :--- |
| **Material Overlay** | The material used for the ghost (usually a transparent additive shader). |
| **Fade Speed** | How quickly each ghost disappears. |
| **Spawn Delay** | Time between each ghost snapshot. |

---

## 🧩 Advanced Use Cases

### Performance-First Ghosting
The `GhostingModule` is optimized for high-density scenarios. Unlike standard Unity trails, it does not use a `TrailRenderer`, but instead draws a fixed set of meshes. This keeps your draw calls and vertex count predictable.

> [!TIP]
> **Pro Tip**: Use ghosting for characters moving at high velocity to give them a sense of extreme speed and power!
