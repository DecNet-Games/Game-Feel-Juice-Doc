---
layout: default
title: Renderer Flash
parent: Features & API Reference
nav_order: 9
---

# Renderer Flashing (Zero-Allocation Damage Feedback)
{: .no_toc }

## Efficient Visual Hit Feedback
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## ⚡ The MaterialPropertyBlock Architecture

In standard Unity tutorials, flashing a sprite or mesh white upon taking damage often looks like this:
```csharp
// 🛑 BAD: Allocates a new cloned Material instance every time!
GetComponent<Renderer>().material.color = Color.white;
```
Accessing `renderer.material` creates a cloned copy of the material in memory. In an action game with dozens of projectiles and enemies, this results in:
1. Massive memory leakage ("Material Inflation").
2. Broken GPU batching (cloned materials cannot be dynamically batched).
3. Frequent Garbage Collection hitches.

### The PULSE Solution
**PULSE** uses pre-allocated `MaterialPropertyBlock` (MPB) instances cached per renderer. It passes color tints and overlay intensity values directly to the GPU without touching material instances:
- **0.00 KB GC Allocation** per flash call.
- Preserves GPU instancing and batching.
- Instant fallback for SpriteRenderer, SkinnedMeshRenderer, and standard MeshRenderer.

---

## 💻 C# API Reference

### 1. Simple Hit Flash
```csharp
using DecNetGames.PULSE;

// Flash enemy white for 100 milliseconds
Juice.Flash(targetRenderer, Color.white, 0.1f);
```

### 2. Multi-Pulse Danger Flicker
Ideal for invulnerability frames, shield overloads, or low-health warnings:
```csharp
// Flash red with 4 rapid flickers over 0.5 seconds
Juice.Flash(targetRenderer, Color.red, duration: 0.5f, pulses: 4);
```

### 3. Procedural Tint Ramp
```csharp
// Flash custom hex color (e.g. poison green or electric cyan)
Juice.Flash(targetRenderer, new Color(0.2f, 1f, 0.3f, 1f), 0.15f);
```

---

## ⚙️ Shader Property Compatibility

The Flash module communicates with shaders using standard property identifiers:
- `_FlashColor` (Color)
- `_FlashAmount` (Float: 0.0 to 1.0)
- `_Color` / `_BaseColor` (Fallback tint modulation)

Works seamlessly with Unity URP Lit, Simple Lit, Sprites-Default, and Built-in Standard shaders.
