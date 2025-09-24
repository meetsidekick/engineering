---
title: "Getting Started"
weight: 1
---

Welcome to your Sidekick! Let's get it set up and running. This guide covers the initial software installation and firmware flashing.

## Flashing the Firmware

To get the latest software on your device or to start from scratch, you'll need to flash the firmware.

### The Easy Way (Recommended)

This project uses the `pixi` tool to automate the setup and flashing process. It's the fastest way to get up and running. It assumes you've already flashed micropython using esptool or thonny! This will be added later to the wiki. 

1.  **Navigate to your project folder** in your terminal.
2.  **Install Dependencies:** Run `pixi install`. This will set up the environment and download necessary tools.
3.  **Upload the Code:** Connect your Sidekick via USB and run `pixi run upload`.

This command will handle flashing the firmware and uploading all the necessary MicroPython files to your device.

### The Manual Way

If you prefer not to use `pixi`, you can flash the firmware manually using a tool like [Thonny IDE](https://thonny.org/).

1.  **Clone the Repository:** Download the project code from the [GitHub repository](https://github.com/meetsidekick/code).
2.  **Open in Thonny:** Open the project folder in the Thonny IDE.
3.  **Connect to Device:** Plug in your Sidekick and ensure Thonny connects to the ESP32 (check the interpreter in the bottom-right corner).
4.  **Upload Files:** Use Thonny's upload feature to transfer the `lib` folder and all the `.py` files to your ESP32.

Once the firmware is flashed, you're ready to start using and customizing your Sidekick!