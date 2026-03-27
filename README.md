# ⚡ CSE251 — Power Supply Section Design & Implementation

<div align="center">

![EWU](https://img.shields.io/badge/East%20West%20University-CSE%20Department-003087?style=for-the-badge)
![Course](https://img.shields.io/badge/Course-CSE251%20Electronic%20Circuits-0078D4?style=for-the-badge)
![Semester](https://img.shields.io/badge/Semester-Summer%202025-28a745?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

**To Design, Implement and Performance Study of a Power Supply Section**

</div>

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Team Members](#-team-members)
- [Objectives](#-objectives)
- [Circuit Components](#-circuit-components)
- [Working Principle](#-working-principle)
- [Experimental Data](#-experimental-data)
- [Results & Analysis](#-results--analysis)
- [Conclusion](#-conclusion)
- [Supervisor](#-supervisor)

---

## 🔍 Project Overview

This project involves the design and practical implementation of a **Zener diode-based regulated DC power supply** on a breadboard. The circuit converts **220V AC mains voltage** into a stable **5.6V–5.7V DC output** using the following stages:

```
AC Mains (220V)
      │
      ▼
 [Transformer]  ──→  Steps down to low-voltage AC (6V–16V)
      │
      ▼
  [Rectifier]   ──→  Converts AC to pulsating DC (Full-Wave)
      │
      ▼
  [Capacitor]   ──→  Filters ripple → Smooth DC
      │
      ▼
 [Zener Diode]  ──→  Regulates to constant 5.6V output
      │
      ▼
    LOAD (Regulated DC Output ✅)
```

---

## 👥 Team Members

| Name | Student ID |
|------|-----------|
| Belal Hossain | 2023-2-60-010 |
| Noor Mohammad | 2023-3-60-396 |
| Rezwan Ahmed | 2023-3-60-418 |

> **Lab Group:** 03 | **Section:** 01  
> **Submission Date:** 01 September 2025

---

## 🎯 Objectives

- ✅ Design a DC power supply that converts standard AC mains voltage into regulated DC
- ✅ Implement using readily available components (diodes, capacitors, resistors, Zener diode)
- ✅ Analyze performance by observing response to different load resistances
- ✅ Understand rectification, filtering, and voltage regulation through practical implementation
- ✅ Study output voltage and current behavior under varying load conditions

---

## 🔧 Circuit Components

| # | Component | Specification | Function |
|---|-----------|---------------|----------|
| 1 | **Transformer** | Center-Tapped, 6V–16V | Steps down 220V AC to low-voltage AC |
| 2 | **Rectifier Diodes** | 1N4007 × 2 | Full-wave rectification (AC → DC) |
| 3 | **Filter Capacitor** | 470µF–1000µF, 25V | Smooths pulsating DC (removes ripple) |
| 4 | **Zener Diode** | 5.6V breakdown | Voltage regulation |
| 5 | **Series Resistor R1** | 220Ω, 1W | Current limiting for Zener diode |
| 6 | **Load Resistors** | 1kΩ, 5kΩ, 10kΩ | Simulate varying load conditions |
| 7 | **LED** | Standard | Power indicator |
| 8 | **Breadboard** | Full-size | Circuit prototyping |
| 9 | **Multimeter** | Digital/Analog | Voltage & current measurement |
| 10 | **Power Source** | AC mains | Input supply |

---

## ⚙️ Working Principle

### 1. 🔌 Transformer — Voltage Step-Down
A center-tapped transformer reduces 220V AC mains to a safer low-voltage AC (6V–16V). The center-tap enables full-wave rectification using only two diodes.

### 2. 🔁 Rectifier — AC to DC
Two **1N4007** diodes form a full-wave rectifier. Each diode conducts on alternate half-cycles, ensuring that both positive and negative halves of the AC waveform contribute to the output — producing pulsating DC.

### 3. 🔋 Capacitor — Filtering
A **470µF electrolytic capacitor** charges to the peak rectified voltage and discharges during troughs, effectively smoothing out the ripple and producing a stable DC input for the regulator.

### 4. ⚡ Zener Diode — Voltage Regulation
The Zener diode (5.6V) operates in **reverse breakdown mode**. When input voltage exceeds 5.6V, it conducts and clamps the output to a fixed voltage, absorbing any excess current and keeping the output stable.

### 5. 💡 LED — Status Indicator
Lights up when the circuit is powered and output voltage is within the correct range.

---

## 📊 Experimental Data

> Measurements taken across 13 different load resistance values.

| # | Resistance (Ω) | Output Current Iₒ (mA) | Output Voltage Vₒ (V) | Region |
|---|---------------|------------------------|----------------------|--------|
| 1 | 250 Ω | 7.6 mA | 3.8 V | ⚠️ Drop-Out |
| 2 | 500 Ω | 6.2 mA | 4.9 V | ⚠️ Drop-Out |
| 3 | 1,000 Ω | 4.6 mA | 5.4 V | ⚠️ Drop-Out |
| 4 | 2,200 Ω | 2.7 mA | **5.6 V** | ✅ Regulation |
| 5 | 3,300 Ω | 1.7 mA | **5.7 V** | ✅ Regulation |
| 6 | 4,700 Ω | 1.3 mA | **5.65 V** | ✅ Regulation |
| 7 | 5,000 Ω | 1.1 mA | **5.62 V** | ✅ Regulation |
| 8 | 6,000 Ω | 0.9 mA | **5.68 V** | ✅ Regulation |
| 9 | 6,700 Ω | 0.8 mA | **5.6 V** | ✅ Regulation |
| 10 | 7,000 Ω | 0.7 mA | **5.62 V** | ✅ Regulation |
| 11 | 8,300 Ω | 0.6 mA | **5.65 V** | ✅ Regulation |
| 12 | 9,300 Ω | 0.55 mA | **5.6 V** | ✅ Regulation |
| 13 | 10,000 Ω | 0.5 mA | **5.7 V** | ✅ Regulation |

---

## 📈 Results & Analysis

### ✅ Regulation Region (R ≥ 2.2 kΩ)
- Output voltage held stable between **5.6V and 5.7V**
- Load regulation calculated at approximately **1.8%** — excellent for a simple shunt regulator
- Current demand remained low (≤ 2.55 mA), suitable for low-power circuits
- Zener diode successfully operated in reverse breakdown, clamping output voltage

### ⚠️ Drop-Out Region (R < 2.2 kΩ)
- Output voltage dropped significantly as load resistance decreased:
  - At **1 kΩ** → 5.4V
  - At **500 Ω** → 4.9V
  - At **250 Ω** → 3.8V
- Increased current demand caused a larger voltage drop across the series resistor R1
- Zener diode could no longer maintain conduction → regulator "dropped out"

### 🔑 Key Formula Used
```
Ohm's Law:   I = V / R
Load Regulation = (V_no_load - V_full_load) / V_full_load × 100%
               ≈ (5.7 - 5.6) / 5.6 × 100% ≈ 1.8%
```

---

## 🏁 Conclusion

- The Zener diode-based power supply **successfully regulated output** to 5.6V–5.7V for load resistances ≥ 2.2 kΩ
- The design is well-suited for **low-power electronic applications**
- The **Drop-Out Region** revealed the fundamental limitation of shunt regulators under high current demand
- **Future improvement:** Adding a pass transistor (e.g., BC547 or 2N2222) in series would significantly improve current handling while retaining the Zener diode for reference voltage — forming a more robust linear regulator

---

## 👨‍🏫 Supervisor

**Dr. Md. Habibur Rahman**  
Adjunct Faculty, Department of CSE, East West University  
Professor & Chairman, Department of EEE, University of Dhaka

---

## 📁 Repository Structure

```
CSE251-Power-Supply-Project/
│
├── README.md                  # This file
├── Project_Report.pdf         # Full project report
├── images/
│   ├── circuit_on.jpg         # Operational circuit (ON)
│   ├── circuit_off.jpg        # Operational circuit (OFF)
│   └── working_diagram.jpg    # Hand-drawn circuit schematic
└── data/
    └── experimental_data.csv  # Voltage & current measurements
```

---

<div align="center">

**East West University · CSE Department · Summer 2025**  
*CSE251: Electronic Circuits — Lab Group 03*

</div>
