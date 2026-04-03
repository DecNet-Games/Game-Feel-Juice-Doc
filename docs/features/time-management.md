---
layout: default
title: Time Management
parent: Features
nav_order: 2
---

# Time Management
{: .no_toc }

## Impact Through Time
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 🛑 HitStop (Frame Freeze)
HitStop is the most effective way to make a hit feel heavy. When the player strikes an enemy, the game freezes for a moment (milliseconds), letting the impact sink in.

### 📈 Behavior
-   **Timescale**: Drops to 0 instant.
-   **Lerp Out**: Smoothly returns to 1.0 based on settings.

### 💻 API
```csharp
Juice.Time.HitStop(0.12f); // Freeze for nearly 10 frames
```

---

## 🌑 Slow-Motion
Slow-motion can be used for dramatic effects or as a gameplay mechanic (e.g., bullet time).

### 📈 Behavior
-   **Timescale**: Transitions to a custom value (e.g., 0.2).
-   **Duration**: Stays slow for a set duration.
-   **Smooth In/Out**: Configurable lerp durations.

### 💻 API
```csharp
Juice.Time.SlowMo(0.2f, 1.5f); // 20% speed for 1.5 seconds
```

---

## ⚙️ Advanced Settings

| Field | Description |
| :--- | :--- |
| **Fixed Timestep Sync** | Automatically syncs `Time.fixedDeltaTime` to avoid physics jitters. |
| **Smoothing Mode** | Choose between Linear, EaseOut, or None for the transition. |

---

## 🧩 Advanced Use Cases

### Non-Linear Time
The `TimeModule` handles stacking. If you call `SlowMo` while `HitStop` is active, the system manages the priorities correctly, ensuring a smooth transition back to the baseline.

> [!CAUTION]
> **Warning**: Avoid changing `Time.timeScale` manually in your own scripts while using the Juice System, as it may conflict with the internal lerping logic. Use `Juice.Time.Reset()` to force a reset to 1.0.
