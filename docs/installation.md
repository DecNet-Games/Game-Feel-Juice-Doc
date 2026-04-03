---
layout: default
title: Installation
nav_order: 2
---

# Installation
{: .no_toc }

## Getting Started with Juice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 🚫 Purchase Prerequisite
**Game Feel & Juice** is a professional production-ready toolkit and is **not a free asset**. You MUST purchase it from the official Unity Asset Store to receive the `unitypackage` and regular updates.

[Buy on Unity Asset Store](https://assetstore.unity.com/){: .btn .btn-primary .fs-5 }

---

## 📥 Importing the Asset

1.  Open your Unity Project (Unity 2021.3 LTS or newer recommended).
2.  Navigate to **Window > Package Manager**.
3.  Select **Packages: My Assets** from the dropdown.
4.  Find **Game Feel & Juice** and click **Download** then **Import**.
5.  In the Import window, ensure all files under `DecNetGames/JuiceSystem` are selected.

---

## ⚙️ Initial Setup

Once imported, follow these steps to activate the system in your scene:

### 1. The Juice Manager
The **Juice Manager** is a singleton that coordinates all "Wow Factor" effects.

-   Go to **GameObject > DecNetGames > Juice Manager**.
-   This will create a new object in your hierarchy.
-   Ensure the `Main Camera` property is assigned (if it doesn't auto-detect).

### 2. Assembly Definitions
If you use Assembly Definitions (`.asmdef`) in your project:
-   Add a reference to `DecNetGames.JuiceSystem.Runtime` in your custom `.asmdef`.

### 3. Namespace Inclusion
In any script where you want to trigger juice:
```csharp
using DecNetGames.JuiceSystem;
```

---

## 🛠️ Verification
To verify the installation:
1.  Open the `Demo` folder inside the asset.
2.  Load the `Playground` scene.
3.  Press **Play** and use the on-screen buttons to trigger effects. If the screen shakes and the time slows, you're all set!

> [!IMPORTANT]
> **Performance Tip**: Always use the **Juice Profiler** to check for material leakages if you're using high-frequency renderer flashes.
