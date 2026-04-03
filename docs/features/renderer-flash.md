---
layout: default
title: Renderer Flash
parent: Features
nav_order: 3
---

# Renderer Flash
{: .no_toc }

## Efficient Visual Feedback
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## ⚡ The MaterialPropertyBlock System
Traditional sprite flashing in Unity involves switching the material or creating a new material instance (`renderer.material`). **Both are bad for production performance.**

### 📈 Why MPB is Better
-   **No GC Allocation**: No new objects are created at runtime.
-   **No Material Leakage**: Avoids the "Material Inflation" bug in Unity where thousands of materials are created.
-   **Zero-Overhead**: Much faster than traditional material switching.

---

## 💻 API Usage

### Simple Flash
Flashes the target renderer to a bright color.
```csharp
Juice.Flash(myRenderer, Color.white, 0.1f); 
```

### High-Pitched Flicker
For a damage effect that lasts longer:
```csharp
Juice.Flash(myRenderer, Color.red, 0.5f, 5); // 5 rapid flickers
```

---

## ⚙️ Advanced Settings

| Field | Description |
| :--- | :--- |
| **_FlashFade Property** | The name of the shader property that handles the white overlay. |
| **Default Flash Color** | Set a global color (e.g., White) in the Juice Manager. |

---

## 🧩 Advanced Use Cases

### Custom Shaders
The `FlashModule` is compatible with **Universal Render Pipeline (URP)** and **Build-In Render Pipeline** shaders. It works by setting a `_FlashAmount` float on the renderer. Ensure your character shaders support this property for maximum efficiency.

> [!TIP]
> **Pro Tip**: Use a white flash for simple damage, a red flash for low health alerts, and a gold flash for power-ups!
