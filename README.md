# Temperature-Controlled Oven

## Description
A discrete analog/digital oven controller that automatically runs a predefined temperature sequence (50°C → 70°C → 90°C) with a stable hold period at each step. The system was built entirely from discrete components and ICs — no microcontroller.

## Features
- Automatically switches between 50°C, 70°C, and 90°C in a fixed sequence
- Holds each temperature stable for 57 seconds
- Heating rate of approximately 0.5°C/s
- Status display (LED) shows the current state (heating, stable, done)
- Deviation display (LED bar) shows the difference from the target temperature
- Closed-loop feedback control using a comparator and ADC

## System Design
The system is built around a state machine that controls the heating,
stabilization, and switching sequence. A digital oscillator and a timer
provide precise timing. The measured temperature is compared with the
target value using a comparator and ADC, and the deviation is shown on
the deviation display. Analog control and a voltage divider regulate the
heating to achieve the desired dynamics and stability.

Main blocks:
- Digital oscillator
- Timer
- State machine
- Voltage divider
- Analog control
- Comparator
- Oven driver
- ADC
- Status display
- Deviation display

## Results
The measured temperature response shows the system reaching and holding
the three target temperatures across two test cycles. Significant
overshoot was observed in the constant-temperature phases, indicating an
unstable control loop, mainly caused by noise in the comparator circuit
leading to unwanted fast switching of the MOSFET.

## Demo
[YouTube demo link here]

## Concepts
- Analog and digital circuit design
- Closed-loop feedback control
- State machine design
- ADC and comparator usage
- Timing with oscillator and timer
- MOSFET-based oven driver
- LED status and deviation displays

## Project Structure
- `docs/Poster.pdf` — project poster (full report)
- `schematics/` — selected circuit schematics:
  - `adc0804.png` — ADC0804 analog-to-digital converter circuit
  - `74hc238-display.png` — 74HC238 decoder driving the LED display matrix
  - `voltage-divider-buffer.png` — equivalent voltage divider with MCP602 buffer
  - `difference-amplifier-comparator.png` — difference amplifier and comparator for feedback control

## Note
Group project (Group 10). Team members: Xingjia Yu, Eva Ziyan Liu, Pelle Cajus.