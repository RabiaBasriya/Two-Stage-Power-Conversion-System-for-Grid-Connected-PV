# Two-Stage-Power-Conversion-System-for-Grid-Connected-PV
## 📌 Project Overview
This project presents the design and simulation of a **50 kW two-stage grid-connected photovoltaic (PV) power conversion system**. The system converts solar energy into grid-compatible AC power using a **DC–DC boost converter** followed by a **three-phase PWM inverter with PLL-based grid synchronization and closed-loop control**.

The primary objectives of this project are:
- Maximum power extraction from the PV array
- Stable DC-link voltage regulation
- Accurate synchronization with the utility grid
- High-quality AC power injection with unity power factor

---

## ⚙️ System Architecture






---

## 🔢 System Specifications

| Parameter | Value |
|---------|------|
| Rated Power | 50 kW |
| Maximum Solar Irradiance | 1000 W/m² |
| PV Output Voltage | 400 V |
| Boost Converter Output | 800 V |
| Switching Frequency | 5 kHz |
| Inverter Type | 3-Phase PWM Inverter |
| MPPT Algorithm | Perturb & Observe (P&O) |
| Grid Synchronization | Three-Phase SRF-PLL |
| Control Strategy | dq-axis Current Control with PI |
| Grid Frequency | 50 Hz |
| Power Factor | Unity (iq_ref = 0) |

---

## ☀️ PV Array Modeling
The PV array is modeled to deliver a rated power of **50 kW** under standard test conditions with a maximum solar irradiance of **1000 W/m²**. The array operates around a nominal voltage of **400 V**, which is suitable for DC–DC boost conversion.

---

## 🔁 DC–DC Boost Converter with MPPT
A **DC–DC boost converter** is used to step up the PV voltage from **400 V to 800 V**, forming a stable DC-link for inverter operation.

### MPPT Technique: Perturb & Observe (P&O)
The P&O algorithm:
- Continuously perturbs the PV operating voltage
- Observes the resulting change in output power
- Adjusts the duty cycle of the boost converter
- Ensures operation at the **maximum power point** under varying irradiance conditions

This technique is simple, robust, and widely used in practical PV systems.

---

## 🔌 DC-Link Voltage Control
The DC-link voltage is regulated at **800 V** using a PI controller.  
The DC-link voltage error generates the **d-axis current reference (id_ref)**, which directly controls the active power injected into the grid.

---

## ⚡ Three-Phase PWM Inverter & Grid Synchronization
A **three-phase PWM inverter** converts DC power into AC power suitable for grid connection.

### Grid Synchronization using PLL
- A **three-phase Synchronous Reference Frame Phase-Locked Loop (SRF-PLL)** is used
- The PLL extracts the grid voltage phase angle and frequency from measured grid voltages (Vabc)
- Ensures inverter currents are phase-aligned with the grid for smooth and stable power injection

---

## 🎛 dq-Axis Current Control
- **d-axis current (id)** controls active power flow
- **q-axis current reference (iq_ref = 0)** ensures unity power factor operation
- PI controllers are used for both d and q axes
- Park and inverse Park transformations are performed using the PLL-generated angle

This control strategy ensures accurate power control and grid-compliant operation.

---

## 🌊 Filter Circuit
A filter is placed between the inverter and the grid to:
- Reduce switching harmonics
- Improve current waveform quality
- Reduce Total Harmonic Distortion (THD)
- Meet grid interconnection standards

---

## 📊 Performance Measurement
The system includes:
- Three-phase voltage and current measurement
- Active and reactive power calculation
- Grid frequency and phase monitoring
- Total Harmonic Distortion (THD) analysis

---

## 🔮 Future Enhancements
- Integration of a **Battery Energy Storage System (BESS)** capable of providing up to **3-day backup**
- Bidirectional DC–DC converter for battery charge and discharge control
- Advanced energy management system
- Mitigation techniques for PV performance degradation due to dust, insects, and partial shading
- Smart monitoring and predictive maintenance

---

## 🧑‍💻 Tools & Platform
- MATLAB / Simulink
- Simscape Electrical
- Control System Toolbox

---


## 📜 License
This project is intended for **academic and research purposes**.
