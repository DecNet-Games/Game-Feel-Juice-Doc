---
layout: default
title: FAQ
nav_order: 5
---

# Frequently Asked Questions
{: .no_toc }

## Common Support Questions
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 🛠️ General Questions

### Does this asset support URP?
**Yes.** The **Game Feel & Juice System** is fully compatible with both the **Universal Render Pipeline (URP)** and the **Built-in Render Pipeline**. For URP, ensure your shaders support the `_FlashAmount` property if you're using the **FlashModule**.

### Can I use this for 2D games?
**Absolutely.** Almost all systems (Shake, Time, Flash, UI, Ghosting) work perfectly in 2D. For 2D-specific camera shakes, ensure the **ShakeModule** is set to "XZ Plane" or "XY Plane" mode.

### Is it performance-friendly?
**Yes.** We prioritize **zero-allocation** code. Key features (like Flashing and Ghosting) use `MaterialPropertyBlock` and object pooling to prevent garbage collection spikes during intense action phases.

---

## 🛑 Comparison & Compatibility

### Why is this better than manually shaking the camera?
Manually shaking the camera with random offsets often feels "jittery" or disconnected. This system uses a **Trauma Model**, allowing shakes to bleed into one another naturally and decay realistically, just like physical oscillations.

### Does it work with Cinemachine?
**Yes.** The **Juice Shake Component** can be attached to the Cinemachine Virtual Camera's noise profile or used via a custom noise extension.

---

## 🆘 Troubleshooting

### My camera won't shake!
1.  Ensure you have a **Juice Manager** in your scene.
2.  Check that your **Main Camera** is assigned to the Manager's `targetCamera` slot.
3.  Verify the `Shake Intensity` isn't set to 0.

### The time-scale is stuck at 0.
This usually happens if an error occurs during a `HitStop` lerp. Call `Juice.Time.Reset()` to force the timescale back to 1.0.

> [!TIP]
> **Pro Tip**: Use the **Debug Dashboard** inside the Juice Manager to see real-time trauma levels and module status.
