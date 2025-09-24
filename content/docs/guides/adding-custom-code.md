---
title: "Adding Your Own Code"
weight: 1
---

One of the best features of the Sidekick is its ability to run your own custom MicroPython code. This guide shows you how to create, upload, and run a simple app.

## The `custom_code` Folder

While you can modify any part of the Sidekick's software, the easiest way to add your own functionality is by creating a new file in the `custom_code/` directory of the project's root folder.

## File Naming Convention

The Sidekick's menu system automatically detects any file in the `custom_code/` directory that follows this naming convention:

`custom_code_YourAppName.py`

The `YourAppName` part of the filename is used as the display name for your app in the "Code Loader" menu. For example, a file named `custom_code_MyFirstApp.py` will appear in the menu as `MyFirstApp`.

## The `run(env)` Function

Your custom app file **must** contain a function called `run(env)`. This function is the entry point for your app and is called by the menu system when the user selects it.

It is passed a single argument, `env`, which is a Python dictionary containing references to the initialized hardware objects.

### Available Hardware in `env`

-   `oled`: The OLED display object. Use this to draw text, shapes, and images.
-   `ok_button`: The `OK` button object (`machine.Pin` instance).
-   `menu_button`: The `Menu` button object (`machine.Pin` instance).
-   `upside_down`: A boolean that tells you if the device is in upside-down mode.

## Running Your Code

1.  **Upload Your Code:** After creating your file, upload it to the Sidekick by running `pixi run upload`.
2.  **Navigate to the App Launcher:** From the main menu, select `Code Loader`.
3.  **Select Your App:** Scroll to your app's name and press the `OK` button to launch it.

Ready to write some code? Head over to our **[Hello, World! Tutorial](../../tutorials/hello-world/)** to get started.