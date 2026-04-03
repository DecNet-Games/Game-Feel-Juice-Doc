---
layout: default
title: Getting Started
nav_order: 3
---

# Getting Started
{: .no_toc }

## Kickstart Your Game Feel
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## ⚡ The Juice API
The **Game Feel & Juice System** uses a static API facade: `Juice`. This means you can trigger almost any effect from any script without needing to cache references or use `GetComponent`.

### 1. The Simple Shake
Need to add weight to an explosion? Just call:
```csharp
Juice.Shake(0.5f); // 0.5 trauma level
```
> [!NOTE]
> **Trauma vs Shake**: Trauma is a value from 0 to 1 that decays over time. Higher trauma results in more intense, randomized shaking.

### 2. HitStop (The Game Feel King)
To simulate a heavy hit where the game freezes for a moment:
```csharp
Juice.Time.HitStop(0.1f); // Freeze for 0.1 seconds
```

### 3. Slow-Motion Burst
For a cinematic kill or a special move:
```csharp
Juice.Time.SlowMo(0.2f, 1.5f); // 20% speed for 1.5 seconds
```

---

## 🎥 Camera "Juice"
The camera isn't just a viewport; it's a character. Use **Punch** and **Kick** to add reactive motion.

### Camera Punch
Push the camera in a direction and let it snap back:
```csharp
Juice.Camera.Punch(Vector3.back * 2f); 
```

### Camera Kick
Rotate the camera based on an impact:
```csharp
Juice.Camera.Kick(new Vector3(5f, 0, 0));
```

---

## 🏗️ Architecture Overview

The system is modular by design. Each behavior is handled by a specialized **Module**:

| Module | Responsibility |
| :--- | :--- |
| **ShakeModule** | Trauma-based oscillations. |
| **TimeModule** | TimeScale manipulation for HitStop/SlowMo. |
| **FlashModule** | Efficient MaterialPropertyBlock flickering. |
| **GhostingModule** | Phantom trail rendering and pooling. |
| **CameraModule** | Spatial offsets (Punch/Kick). |

> [!TIP]
> **Pro Tip**: You can create your own modules by inheriting from `JuiceModuleBase` and registering them with the `JuiceManager`.

---

## 🚀 Next Steps
- [Explore Camera Shake Deep Dive](./features/camera-shake)
- [Learn about Renderer Flashing](./features/renderer-flash)
- [Master Time Management](./features/time-management)
