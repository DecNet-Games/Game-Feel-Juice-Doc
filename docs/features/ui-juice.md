---
layout: default
title: Juicy UI Suite
parent: Features & API Reference
nav_order: 10
---

# Juicy UI Suite (Interactive Game Feel)
{: .no_toc }

## Tactile UI Feedback for Menus, HUDs & Combat
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## ⚡ Why Stagnant UI Kills Immersion

Static, lifeless UI elements break game feel. When a player hovers, clicks, switches tabs, or takes damage, immediate visual and auditory confirmation reinforces game responsiveness.

PULSE includes drop-in, zero-setup UI components equipped with built-in spring physics, delayed ghosting, sound routing, and haptic triggers.

---

## 🧩 Drop-In Components

### 1. `JuicyButton`
Replaces standard Unity `UnityEngine.UI.Button` with harmonic spring bounce dynamics:
- **Hover Feedback**: Smooth scale expansion (e.g. 1.05x) with frequency damping.
- **Click Feedback**: Immediate punch recoil (0.92x) that bounces back elastically.
- **Integrated Audio**: One-click assignment of hover/click `SoundEffectDefinition` presets.
- **Gamepad / Keyboard Navigation**: Triggers identical spring animations when navigated via controller or keyboard arrows.

### 2. `JuicyHealthBar` (Delayed Ghost Bar)
The gold standard in AAA combat games (Dark Souls, Monster Hunter, Fighting Games):
- **Immediate Primary Bar**: Drops instantly to show damage taken.
- **Catch-Up Ghost Bar**: Remains stationary for a configurable delay (e.g., 0.3s), then smoothly eases down with an elastic or cubic curve.
- **Critical Pulse**: Pulses red or shakes when health drops below an emergency threshold (e.g., 20%).

### 3. `JuicyWindow` (Bouncy Modals)
Popups, pause menus, inventory screens, and loot claim dialogues open with a natural harmonic overshoot and dismiss smoothly without manual Animator keyframing.

---

## 💻 C# API Reference

You can also trigger UI juice programmatically on any arbitrary `RectTransform` or `GameObject`:

```csharp
using DecNetGames.PULSE;

// 1. Elastic punch scale on UI element
Juice.UI.Pulse(buttonRectTransform, targetScale: 1.25f, duration: 0.18f);

// 2. Error / Denied shake (e.g., "Not enough gold" or "Cooldown active")
Juice.UI.Shake(goldCounterRectTransform, intensity: 15f, duration: 0.3f);

// 3. UI sound trigger with pitch variation
Juice.Audio.PlayUI(uiClickSoundClip, pitchRandomness: 0.1f);
```

---

## 🛠️ Performance & Allocation

- **0 GC Allocations**: Uses tween and spring struct updates instead of starting new coroutines or allocating heap objects.
- **Canvas Rebuild Friendly**: Animates `transform.localScale` and anchored offsets directly without forcing heavy canvas hierarchy rebuilds.
