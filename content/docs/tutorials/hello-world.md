---
title: "1. Hello, World!"
weight: 1
---

This first lesson will guide you through creating a simple "Hello, World!" app. This will teach you the basic structure of a custom app and how to display text on the screen.

## 1. Create the File

In the `custom_code/` directory, create a new file named `custom_code_HelloWorld.py`.

## 2. Add the Code

Paste the following content into your new file:

```python
# custom_code_HelloWorld.py

from time import sleep_ms

def run(env):
    # Get the hardware objects from the environment dictionary
    oled = env.get('oled')
    ok_button = env.get('ok_button')
    menu_button = env.get('menu_button')

    # Always a good idea to check if hardware is available
    if not all([oled, ok_button, menu_button]):
        print("Missing required hardware")
        return

    # Clear the display (fill with black)
    oled.fill(0)

    # Display the text at coordinates (0, 28)
    oled.text("Hello, World!", 0, 28)
    oled.show()

    # Wait for the OK button to be pressed to exit
    # value() is 1 when not pressed, 0 when pressed
    while ok_button.value() == 1:
        # We can also check for the menu button to exit early
        if menu_button.value() == 0:
            break
        sleep_ms(50) # Small delay to prevent busy-waiting

    # The app exits when the run function returns.
    # The menu system will automatically clear the screen.
```
## 3. Upload and Run 
1. Upload Your Code: Run `pixi run upload` in your terminal to send the new file to the Sidekick.
2. Navigate to the App Launcher: From the main menu, select `Code Loader`.
3. Select Your App: Scroll to `HelloWorld` and press the `OK` button to launch it. You should see "Hello, World!" on the screen.

Congratulations, you've built and run your first custom app!