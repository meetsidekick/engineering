---
title: "Hardware Specs & Wiring"
weight: 1
---

This page contains the detailed technical information for the Sidekick hardware.

## Required Components

To build your Sidekick, you'll need these common hobbyist electronic components:

-   **ESP32 Development Board:** The brains of the operation.
-   **ADXL345 Accelerometer:** To detect movement.
-   **SSD1306 OLED Display (0.96")**: For displaying expressions and information.
-   **Buzzer:** To make some noise.
-   **Buttons (x2):** For user input.
-   **Breadboard and Jumper Wires:** For connecting everything together.
-   **A Micro-USB cable:** To connect the ESP32 to your computer.

## Wiring Diagram

Connect the components to your ESP32 board as follows. **Ensure the board is not powered while you are wiring.**

### I2C Devices (Display & Accelerometer)

Both the OLED display and the ADXL345 accelerometer use the I2C protocol and can share the same SCL/SDA pins.

| Component Pin | ESP32 Pin |
| :--- | :--- |
| VCC | 3v3 |
| GND | GND |
| SCL | GPIO 5 |
| SDA | GPIO 4 |

> You can change the SCL and SDA pins in `main.py` if your board requires different pins.

### Buzzer

| Component Pin | ESP32 Pin |
| :--- | :--- |
| Positive (+) | GPIO 8 |
| Negative (-) | GND |

> The buzzer pin can be changed in `pin_values.py`.

### Buttons

| Button | ESP32 Pin | Connected to |
| :--- | :--- | :--- |
| Menu Button | GPIO 1 | GND |
| OK Button | GPIO 0 | GND |