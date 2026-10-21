---
layout: default
title: Interactive Playgrounds & Demos
nav_order: 6
has_children: true
---

# 🎮 Interactive Demos & Playgrounds
{: .no_toc }

PULSE includes multi-genre interactive demo environments right inside the package. Test and experience every game feel module in action before writing a single line of code.
{: .fs-6 .fw-300 }

---

## 🕹️ Included Demo Scenes

### 1. 3D Combat Action Arena
- **Path:** `Assets/DecNetGames/PULSE/Demos/3D_Action_Arena.unity`
- **Showcase:**
  - Dynamic shotgun recoil with directional camera kicks.
  - Heavy hammer smash with frame-perfect 120ms **HitStop**, screen shockwave distortion, and quadratic camera trauma.
  - Floating combat damage numbers with bounce physics and critical hit golden popups.
  - Zero-allocation white hit-flash on enemy meshes using `MaterialPropertyBlock`.
  - Phantom dash ghost trails behind the player during dodge-rolls.

### 2. 2D Top-Down Shooter Playground
- **Path:** `Assets/DecNetGames/PULSE/Demos/2D_Shooter_Playground.unity`
- **Showcase:**
  - 2D-constrained camera shakes (XY plane locked).
  - Volume-preserving squash and stretch on bullet impacts ($S_x \cdot S_y = 1$).
  - Procedural pitch randomization on rapid-fire weapons preventing ear fatigue.
  - Screen-space radial shockwaves originating from projectile explosion points.

### 3. Tactile UI & Menu Showcase
- **Path:** `Assets/DecNetGames/PULSE/Demos/Demo_Tactile_UI.unity`
- **Showcase:**
  - `JuicyButton`: Harmonic spring bounce on hover and elastic punch on click.
  - `JuicyHealthBar`: AAA delayed catch-up ghost health bar with low-health alert pulsing.
  - `JuicyWindow`: Bouncy modal dialog animations with harmonic overshoot.
  - Procedural audio clicks and invalid-action warning shakes.

---

## 🚀 Running the Demos

1. In Unity, open the scene from `Assets/DecNetGames/PULSE/Demos/`.
2. Press **Play**.
3. Use the on-screen interactive control panel or keyboard hotkeys (Space to shoot, Shift to dash, Right Click for heavy smash) to trigger instant juicy feedback!
