# HX711 Scale Calibration Sketch

A simple Arduino sketch to find the correct `calibration_factor` for a scale using a load cell and an HX711 amplifier.

Русская версия

## Description

This project helps you calibrate your DIY scale. By loading the sketch and using the Serial Monitor, you can place a known weight on the scale and interactively adjust the calibration factor until the reading on the monitor matches your known weight. The final factor can then be used in your other scale-related projects.

## Hardware Requirements

*   Arduino board (e.g., Uno, Nano)
*   HX711 Load Cell Amplifier module
*   Load Cell (any capacity)
*   A weight of a known mass (e.g., a 100g calibration weight, a can of soda, etc.)
*   Jumper wires

## Libraries

This sketch requires the "HX711 Arduino Library". You can install it from the Arduino Library Manager or download it from here:
*   HX711 Arduino Library by bogde

## Wiring

Connect the HX711 module to your Arduino as follows. **Note:** The pins used in the code (`A0`, `A1`) are the correct ones.

| HX711 Pin | Arduino Pin |
| :-------: | :---------: |
|   `VCC`   |     `5V`    |
|   `GND`   |     `GND`   |
|   `DT`    |     `A1`    |
|   `CLK`   |     `A0`    |

## How to Use

1.  **Wire** your components according to the table above.
2.  **Install** the required HX711 library in your Arduino IDE.
3.  **Upload** the `main.cpp` sketch to your Arduino.
4.  **Open** the Serial Monitor (`Tools -> Serial Monitor` or `Ctrl+Shift+M`).
5.  **Set** the baud rate to `9600`.
6.  You will see instructions printed in the monitor. Make sure there is **no weight** on the scale when it starts. The scale will perform a `tare` operation to set the zero point.
7.  Once you see weight readings appear, **place your known weight** on the center of the scale.
8.  The reading will likely not match your known weight. To adjust it:
    *   Press `+` or `a` and hit `Enter` to **increase** the calibration factor.
    *   Press `-` or `z` and hit `Enter` to **decrease** the calibration factor.
9.  Continue adjusting until the `Reading` value shown in the Serial Monitor matches the mass of your known weight.
10. **Note down** the final `calibration_factor`. You can now use this value in any sketch to get accurate weight readings from your scale.