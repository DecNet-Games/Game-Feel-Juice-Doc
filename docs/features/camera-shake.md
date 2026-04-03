---
layout: default
title: Camera Shake
parent: Features
nav_order: 1
---

# Camera Shake
{: .no_toc }

## Trauma-Based Shaking
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 🌪️ The Trauma System
Most camera shakes in Unity are linear (a simple Perlin noise that fades). This system uses **Trauma**, a realistic physical model.

### 📈 Decay Curve
-   **Trauma**: A value between 0 and 1.
-   **Shake**: Trauma squared (exponential intensity).
-   **Decay**: Trauma reduces linearly by a set amount per second (default: 1.0).

This results in a shake that starts strong and smooths out naturally.

---

## 💻 API Usage

### Simple Shake
Adds to the current trauma level.
```csharp
Juice.Shake(0.4f); // Adds 0.4 trauma
```

### Heavy Impact
Useful for explosions or screen-wide events.
```csharp
Juice.Shake(0.8f); 
```

### From Position
Shake only if the player is within range.
```csharp
Juice.ShakeAt(explosionSource, maxRadius);
```

---

## ⚙️ Settings

You can customize the shake behavior in the **Juice Manager**:

| Setting | Description |
| :--- | :--- |
| **Max Radius** | Maximum movement offset on X/Y. |
| **Max Rotation** | Maximum rotation angle. |
| **Trauma Decay** | How fast the trauma "cools down". |
| **Frequency** | The speed of the randomized noise. |

---

## 🧩 Advanced Use Cases

### Object Shake
You don't just have to shake the camera. You can attach a `JuiceShakeComponent` to any Transform (like a barrel or a vibrating machine) and it will respond to trauma events.

> [!TIP]
> **Pro Tip**: Use a high frequency (30+) for small, high-pitched vibrations (like an engine) and a low frequency (5-10) for heavy earth-shaking effects.
