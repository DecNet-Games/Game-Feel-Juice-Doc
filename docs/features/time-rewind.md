---
layout: default
title: Circular Time-Rewind
parent: Features & API Reference
nav_order: 5
---

# ⏱️ Zero-Allocation Circular Time-Rewind
{: .no_toc }

Record and reverse gameplay physics, positions, rotations, velocities, and custom script parameters without Garbage Collection overhead.
{: .fs-6 .fw-300 }

---

## ⚡ Architecture

Unlike basic record systems that allocate memory on every frame, PULSE utilizes a **pre-allocated circular buffer ring (`CircularBuffer<T>`)**:
* **Sub-frame interpolation**: Slerp and Lerp ensure silky smooth playback even at low recording intervals.
* **Physics preservation**: Stores angular and linear velocities so characters resume motion naturally when rewind terminates.
* **Zero GC**: Pre-warms frames in memory during startup.

---

## 💻 Code Usage

### 1. Make any GameObject Rewindable
Attach the `TimeRecordable` component to your player, vehicle, or physics object.

### 2. Trigger Rewind in Code
```csharp
using DecnetGames.JuiceSystem;

// Start rewinding time
TimeRewindManager.Instance.StartRewind();

// Stop rewinding and resume normal gameplay
TimeRewindManager.Instance.StopRewind();
```

### 3. Record Custom Variables via Interface
```csharp
using DecnetGames.JuiceSystem;
using UnityEngine;

public class PlayerHealth : MonoBehaviour, ITimeRecordable
{
    public float currentHealth = 100f;

    public void OnSaveState(TimeFrame frame)
    {
        frame.SetFloat("hp", currentHealth);
    }

    public void OnLoadState(TimeFrame frame)
    {
        currentHealth = frame.GetFloat("hp");
    }

    public void OnInterpolateState(TimeFrame older, TimeFrame newer, float t)
    {
        currentHealth = Mathf.Lerp(older.GetFloat("hp"), newer.GetFloat("hp"), t);
    }
}
```
