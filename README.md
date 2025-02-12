# Emission_Control_System

## Overview
The **Carbon Emission Monitor** is a logic circuit-based system designed to classify vehicle emissions based on different environmental and driving conditions. The classification is done using **AND** and **OR** logic gates, and the output is indicated using **LEDs**.

## Components
- **9 Slide Switches** (Input selectors)
- **1 × 74HC32** (OR Gate IC)
- **2 × 74HC08** (AND Gate IC)
- **3 LEDs** (Red, Yellow, Green for emission levels)
- **9V Battery** (Power source)
- **1 × LM7805** (5V Regulator)
- **Breadboard** (Circuit assembly)
- **Jumper Wires** (Connections)
- **9 × 10kΩ Resistors** (Pull-down resistors for switches)
- **3 × 330Ω Resistors** (Current limiting for LEDs)

## Switch Configuration

| Switch | Function |
|--------|----------|
| **S1** | Petrol |
| **S2** | Diesel |
| **S3** | EV (Electric Vehicle) |
| **S4** | Light Traffic |
| **S5** | Moderate Traffic |
| **S6** | Heavy Traffic |
| **S7** | Nighttime |
| **S8** | Idle Time |
| **S9** | Distance |

#### *Switch States*
- **S7: Nighttime** → `1 = Yes`, `0 = No`
- **S8: Idle Time** → `1 = Long`, `0 = Short`
- **S9: Distance** → `1 = Long`, `0 = Short`

## Logic Gate Implementation

### AND Gate Logic
The following conditions are implemented using **AND gates**:
1. **AND 1**: `S1 • S8 → 01`
2. **AND 2**: `S2 • S9 → 02`
3. **AND 3**: `S3 • S7 → 03`
4. **AND 4**: `S4 • S8 → 04`
5. **AND 5**: `S5 • S9 → 05`
6. **AND 6**: `S6 • S7 → 06`

### OR Gate Logic
The following conditions are implemented using **OR gates**:
1. **OR 1**: `01 + 02 → 07`
2. **OR 2**: `03 + 04 → 08`
3. **OR 3**: `05 + 06 → 09`

## Output Classification
The system classifies emissions into three levels:
- **Low Emission (Green LED)** → `07`
- **Moderate Emission (Yellow LED)** → `08`
- **High Emission (Red LED)** → `09`

## How to Use
1. Set the **switches** according to vehicle type and traffic conditions.
2. Observe the **LED output** to determine emission classification.
3. Adjust inputs to test different conditions.

## Future Enhancements
- Implementing **microcontroller-based** logic instead of discrete gates.
- Adding a **real-time sensor** input for accurate monitoring.
- Extending classification criteria for more refined results.

---
### Contributions & Feedback
Feel free to contribute, report issues, or suggest improvements!

