# Real-Time Colour Detection System Using FPGA

## Overview

This project implements a **real-time colour detection system** on an FPGA platform. Using a Nexys A7 FPGA development board, the system identifies the presence of primary colors—**Red, Green, and Blue (RGB)**—in streaming pixel data. The design and logic are written in **Verilog**.

## Features

- **Real-time processing:** Detects RGB colors from incoming pixel data without perceptible delay.
- **Primary color identification:** Specifically targets and distinguishes Red, Green, and Blue channels.
- **FPGA implementation:** Utilizes the Nexys A7 board for high-speed, parallel processing.
- **Verilog-based design:** Modular and synthesizable hardware description for easy modification and scalability.

## Hardware Used

- **FPGA Board:** Digilent Nexys A7 (Artix-7 FPGA)
- **Input:** Pixel data stream (can be sourced from camera, HDMI, or test patterns)
- **Output:** Detected color signals (can be LEDs, display, or other peripherals)

## How It Works

1. **Pixel Data Input:** Pixel data is fed into the FPGA, typically as RGB values (8 bits per channel).
2. **Color Detection Logic:** The Verilog code compares each pixel’s RGB values against preset thresholds to determine if the pixel represents Red, Green, or Blue.
3. **Output:** For each pixel, the system asserts an output signal corresponding to the detected color.

## Block Diagram

```
+----------------+     +--------------------+     +--------------------+
| Pixel Data In  | --> | Colour Detection   | --> | Output (e.g. LEDs, |
| (RGB Stream)   |     | Logic (Verilog)    |     | display, etc.)     |
+----------------+     +--------------------+     +--------------------+
```

## Verilog Code Structure

- **colour_detection.v:** Main module for RGB detection
- **top.v:** Top-level module interfacing with FPGA I/O
- **testbench.v:** Simulation testbench

## Example: Colour Detection Logic (Pseudocode)

```verilog
if (R > threshold && G < threshold && B < threshold)
    color_detected = RED;
else if (G > threshold && R < threshold && B < threshold)
    color_detected = GREEN;
else if (B > threshold && R < threshold && G < threshold)
    color_detected = BLUE;
else
    color_detected = NONE;
```

## How to Run

1. **Clone this repository.**
2. **Open the project in your preferred FPGA design tool (Vivado recommended).**
3. **Synthesize and implement the design.**
4. **Program the Nexys A7 board.**
5. **Feed pixel data into the board and observe the output signals.**

## Applications

- Basic computer vision for robotics
- Educational FPGA projects
- Real-time hardware color filtering

## Future Improvements

- Support for secondary colors (CMY, etc.)
- Adjustable thresholds (via switches or software)
- Integration with camera modules for live video
