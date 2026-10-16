---
layout: default
title: Installation
nav_order: 2
---

# Installation & Pipeline Setup
{: .no_toc }

## Setup PULSE in Any Unity Project
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 📥 Package Import

1. Open your project in **Unity 2021.3 LTS, 2022.3 LTS, or Unity 6 (6000.x)+**.
2. Navigate to **Window > Package Manager**.
3. Select **Packages: My Assets** from the dropdown menu.
4. Locate **PULSE — Game Feel & Polish Engine** and click **Download** then **Import**.
5. Keep all default directories selected (`Assets/DecNetGames/PULSE/`).

---

## ⚙️ Initial Configuration (1-Click Setup Doctor)

PULSE features an automated **Setup Doctor** that validates your scene, active render pipeline, and component bindings with one click:

1. In the top Unity menu, open **Tools > PULSE > Setup Doctor** (or **Window > PULSE > Command Hub**).
2. The Doctor scans your scene for:
   - Camera references (`Camera.main` or Cinemachine Virtual Cameras).
   - Audio listeners & mixer channels.
   - Active render pipeline (Universal Render Pipeline, HDRP, or Built-in).
   - UI Canvas setups for Floating Combat Text.
3. Click **"Auto-Configure Scene"**. The wizard generates the persistent `JuiceManager` hierarchy and warms up the runtime pools.

---

## 📦 Assembly Definitions (`.asmdef`)

PULSE strictly isolates runtime systems from editor tooling to guarantee zero runtime bloat and seamless build compilation:

- **Runtime Assembly**: `DecNetGames.PULSE.Runtime.asmdef`
- **Editor Assembly**: `DecNetGames.PULSE.Editor.asmdef`

If your project utilizes custom Assembly Definitions:
1. Select your project's `.asmdef` file in the Project window.
2. Under **Assembly Definition References**, click **+** and add `DecNetGames.PULSE.Runtime`.
3. Click **Apply**.

---

## 🎨 Render Pipeline Compatibility

### Universal Render Pipeline (URP)
- Fully supported out of the box.
- Radial shockwaves and screen distortion shaders leverage URP Renderer Features or Camera Opaque Textures.
- Ensure **Opaque Texture** is checked in your `UniversalRenderPipelineAsset`.

### Built-in Render Pipeline
- 100% native support using standard Blit and MaterialPropertyBlock pipelines.

### High Definition Render Pipeline (HDRP)
- Fully supported for all core modules, Spring Physics, Audio, TimeScale, and TextMeshPro popups. Custom post-processing volumes can be driven via `Juice.VFX`.

---

## 🎮 Verifying the Installation

To immediately test the entire suite:
1. Navigate to `Assets/DecNetGames/PULSE/Demos/`.
2. Open `3D_Action_Arena.unity` or `2D_Shooter_Playground.unity`.
3. Press **Play**. Use the interactive playground controls to trigger camera shakes, squash/stretch physics, audio ducking, and floating numbers!
