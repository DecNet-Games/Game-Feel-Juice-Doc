---
layout: default
title: FAQ & Troubleshooting
nav_order: 5
---

# Frequently Asked Questions & Troubleshooting
{: .no_toc }

## Common Questions, Performance Details & Solutions
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 🛠️ General & Compatibility

### Which Unity versions are officially supported?
PULSE is tested and fully supported on **Unity 2021.3 LTS**, **Unity 2022.3 LTS**, and **Unity 6 (6000.x)+**.

### Does PULSE work with Cinemachine?
**Yes.** PULSE includes a native Cinemachine adapter component (`JuiceCinemachineAdapter`). It routes trauma and shake impulses directly into Cinemachine Virtual Camera 6D noise profiles without conflict.

### Can I use PULSE in pure 2D games?
**Yes.** All physics calculations, camera shakes, squashes, stretches, and floating popups feature dedicated 2D operating modes (`XY Plane` constraint). You can use it in 2D platformers, top-down shooters, pixel art games, or full 3D arenas.

### What render pipelines are supported?
PULSE supports **Universal Render Pipeline (URP)**, **High Definition Render Pipeline (HDRP)**, and the **Built-in Render Pipeline**.

---

## ⚡ Performance & Memory

### Does PULSE produce Garbage Collection (GC) allocations?
**0.00 KB GC at runtime.** Every runtime module in PULSE utilizes:
- Pre-warmed object pools for audio channels, combat text, and mesh snapshots.
- `MaterialPropertyBlock` instances to prevent material duplication and GPU state leaks.
- Zero string concatenations in hot loops.
- Value-type struct mathematical evaluations for spring equations.

### Will the Editor tools slow down my game builds?
**No.** All editor scripts, custom inspectors, graph visualizers, and debug overlays reside strictly within `DecNetGames.PULSE.Editor.asmdef`. They are completely stripped from stand-alone player builds by the Unity compiler.

---

## 🆘 Troubleshooting

### My camera won't shake when I call `Juice.Shake()`!
1. Check that a `JuiceManager` exists in your scene. If not, open **Tools > PULSE > Setup Doctor** and click **Auto-Configure Scene**.
2. Verify that your camera has the `JuiceCameraShake` component or that the `JuiceManager` has detected your `Camera.main`.
3. Check the Global Shake Multiplier in **Tools > PULSE > Command Hub** — ensure it is not set to 0.

### The game is stuck in slow motion or frozen!
If an external script throws an unhandled exception during a `HitStop` coroutine, call:
```csharp
Juice.Time.ResetTimeScale();
```
This instantly restores `Time.timeScale` to `1.0f` and resets `Time.fixedDeltaTime` to `0.02f`.

### Combat text numbers are missing or pink!
Ensure you have imported the standard **TextMeshPro Essential Resources** (**Window > TextMeshPro > Import TMP Essential Resources**).

---

## 💬 Support & Community

- **Unity Asset Store Page:** [PULSE on Asset Store](https://assetstore.unity.com/packages/tools/animation/pulse-aaa-game-feel-polish-engine-406136)
- **Official Live Docs:** [https://decnet-games.github.io/Game-Feel-Juice-Doc/](https://decnet-games.github.io/Game-Feel-Juice-Doc/)
- **Publisher Portal & Updates:** [https://decnetgames.com](https://decnetgames.com)
- **Discord Community:** [https://discord.com/invite/FTXfv8mcVh](https://discord.com/invite/FTXfv8mcVh)
- **Direct Support Email:** `support@decnetgames.com`
