---
layout: default
title: UI Juice
parent: Features
nav_order: 5
---

# UI Juice
{: .no_toc }

## Making Your Interface Alive
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## ⚡ UI Animation & Feedback
Stagnant UI buttons feel broken. Add "Juice" to your buttons, icons, and menus to make the player feel every click.

### 📈 Behavior
-   **Scale Pulse**: Briefly pulse the scale of an element when hovered or clicked.
-   **Shake**: Add a small, high-frequency shake to buttons for a negative response (e.g., "Insufficient gold").

---

## 💻 API Usage

### Button Click Pulse
Add an immediate pulse to a button's icon.
```csharp
Juice.UI.Pulse(myButton.gameObject, 1.2f, 0.15f); // Pulse to 120% for 0.15s
```

### UI Shake
Shake a UI element (like a popup window) to draw attention.
```csharp
Juice.UI.Shake(myInputWindow, 0.5f);
```

---

## ⚙️ Advanced Settings

| Field | Description |
| :--- | :--- |
| **Ease Mode** | Choose between Easing modes (Linear, EaseOut, etc.) for animations. |
| **Default Scale** | The baseline scale to return to (usually 1,1,1). |

---

## 🧩 Advanced Use Cases

### Hover Highlights
Use the `JuiceUIComponent` on your UI prefabs to automatically handle hover and click transitions without writing a single line of state-machine logic.

> [!TIP]
> **Pro Tip**: Use a subtle shake when the player tries to click a "Disabled" button. It's a great non-verbal way to signal that something is wrong.
