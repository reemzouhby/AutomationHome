# Automatic Light and Motor Control System



## 📖 Project Overview

This project implements an **automatic lighting and motor control system** based on real-time ambient light intensity using a Light Dependent Resistor (LDR). It utilizes the **ATmega328P** microcontroller and supports both **automatic** and **manual** motor control via a **push button**. The system's status is displayed on an **LCD screen**.

---

## 🎯 Objectives

- Measure light intensity using ADC from LDR
- Control an LED (room light) and a motor based on light levels
- Allow manual motor activation with a push button
- Display status and sensor readings on an LCD

---

## 🧰 Components Used

- ATmega328P Microcontroller
- 16x2 LCD Display
- LDR (Light Sensor)
- LED (for lighting control)
- Motor (or relay for motor control)
- Push Button (for manual control)
- Resistors, Capacitors, Pull-up Resistors

---

## ⚙️ System Functionality

### 1. Light Sensing & Classification

The LDR sensor outputs a voltage based on ambient light, read through the ADC:

| ADC Value Range | Light Level     |
|------------------|------------------|
| 0 – 399          | Low Light        |
| 400 – 799        | Medium Light     |
| 800 – 1023       | High Light       |

---

### 2. Control Logic

| Light Level     | LED State | Motor State (Button Pressed) | Motor State (Button Not Pressed) |
|------------------|-----------|-------------------------------|-----------------------------------|
| Low Light        | ON        | OFF                           | OFF                               |
| Medium Light     | OFF       | OFF                           | OFF                               |
| High Light       | ON        | ON                            | OFF                               |

---

### 3. LCD Display

Displays system information such as:
- "Created by Reem & Majdo"
- "Light Level: Low / Medium / High"
- "Motor: ON / OFF"
- "LED: ON / OFF"

---

## 🔢 Voltage Calculation

To compute actual voltage from ADC readings:
Vout = (ADC_value / 1023) * Vref
Where:
- `ADC_value` is the digital value from the ADC (0–1023)
- `Vref` is the reference voltage = **1.1V**

---

## 🔄 Working Principle

1. Continuously monitor LDR via ADC
2. Determine light level (Low, Medium, High)
3. Decide LED and Motor state based on button input
4. Display status on LCD

---

## 💡 Applications

- Smart Home Automation – Automatically turns on room lights or fans
- Street Lighting – Lights turn on at night, off in daylight
- Greenhouse Automation – Manage artificial lighting and fans
- Energy Efficiency Systems

---

## 📌 Notes

- This project is implemented on AVR microcontrollers (ATmega328P).
- ADC and I/O control are handled using C (AVR-GCC).
- Ideal for learning about ADC, digital I/O, LCD interfacing, and conditional control logic.

