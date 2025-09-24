---
title: "Personality Cores"
weight: 2
---

# Personality Cores

Your Sidekick's emotional responses are not fixed. You can completely change its personality by creating and switching between different **Personality Cores**. A core is a single Python file that defines a set of emotions, their decay rates, and how the Sidekick reacts to certain feelings.

## Core Concepts

-   **Emotions have intensity:** Every emotion is a number between 0.0 (not feeling it) and 1.0 (feeling it intensely).
-   **Emotions decay over time:** Feelings fade. If left alone, your Sidekick's emotional state will slowly return to a neutral baseline.
-   **Thresholds can trigger actions:** You can make the Sidekick react automatically when a feeling gets strong enough.

## Creating a Personality Core

Creating a new personality is as simple as adding a new Python file to the `emotion_cores/` directory.

1.  **Create a new file:** For example, `emotion_cores/sarcastic.py`.
2.  **Define a `load(personality)` function:** This function is required. It will be passed the global `Personality` instance.
3.  **Register emotions and handlers:** Inside the `load` function, use `personality.register()` and `personality.on_threshold()` methods.

### Example: Sarcastic Core

```python
# emotion_cores/sarcastic.py

def load(personality):
    """Loads the sarcastic personality."""
    personality.register('agitated', intensity=0.7, decay_rate=0.01)
    personality.register('curious', intensity=0.6, decay_rate=0.02)
    
    def on_agitated(mood, intensity):
        print(f"Sarcastic Core: Oh, great. More shaking. Just what I needed.")

    personality.on_threshold('agitated', 0.8, on_agitated)
```

## Switching Personalities

1. Press the `Menu` button on your Sidekick.
2. Select Personality and press `OK`.
3. Choose a core from the list and press `OK`. The new personality will be loaded and saved as the new default.