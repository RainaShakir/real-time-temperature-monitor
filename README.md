# 🌡️ Real-Time Temperature Monitoring System
### Measurement & Instrumentation Lab — Course Engineering Project (CEP)
**Pakistan Institute of Engineering & Applied Sciences (PIEAS)**
---

## 📋 Project Overview

This project implements a **real-time temperature monitoring and data logging system** using a K-type thermocouple sensor, a National Instruments DAQ device, and a LabVIEW-based virtual instrument (VI). The system continuously acquires temperature data, displays it on a live waveform chart and thermometer indicator, compares it against a user-defined reference threshold, and logs all data to a TDMS file for post-analysis.

This was developed as the **Course Engineering Project (CEP)** for the Measurement & Instrumentation (M&I) Lab during the 5th semester of BS Electrical Engineering at PIEAS.

---

## 🎯 Objective

To design and implement a complete instrumentation pipeline that:
- Acquires real-time temperature data from a physical thermocouple sensor via a DAQ system
- Displays live readings using multiple visual indicators (waveform chart + thermometer)
- Triggers a visual **WARNING alert** when temperature exceeds a user-defined threshold
- Logs all acquired data continuously to a **.tdms file** for record-keeping and analysis

---

## ⚙️ System Architecture

The system follows a standard **Sensor → Signal Conditioning → DAQ → Processing → Display** pipeline:

```
K-Type Thermocouple
        │
        ▼
  DAQ Assistant (NI)
  [Signal Acquisition]
        │
        ├──────────────────────┐
        ▼                      ▼
  Temperature Display     Waveform Chart
  + Thermometer           [Real-time Plot]
        │
        ▼
  Threshold Comparison
  [Temperature > Reference?]
        │
        ▼
  WARNING Indicator (LED)
        │
        ▼
  TDMS File Logger
  [Data Storage]
```

---

## 🛠️ Tools & Technologies

| Component | Details |
|-----------|---------|
| **Software** | National Instruments LabVIEW |
| **DAQ Module** | NI DAQ Assistant |
| **Sensor** | K-Type Thermocouple |
| **Data Format** | TDMS (Technical Data Management Streaming) |
| **Platform** | Windows |
| **Technique** | While Loop, Data Flow Programming |

---

## 🖥️ Implementation

### Block Diagram
The LabVIEW Block Diagram shows the complete data flow logic of the system — from DAQ signal acquisition to display, threshold comparison, and TDMS file logging.

![Block Diagram](Block_Diagram.png)

**Key components visible in the Block Diagram:**
- **DAQ Assistant** — acquires analog input from the thermocouple
- **Waveform Chart** — plots temperature in real time
- **Thermometer indicator** — provides visual gauge display
- **Comparison node (`>`)** — compares live temperature against the reference threshold
- **Boolean LED (WARNING!)** — activates when threshold is exceeded
- **TDMS Write node** — continuously logs data to file
- **While Loop with STOP button** — keeps the VI running until manually stopped

---

### Front Panel
The Front Panel is the user interface of the system — what the operator sees and interacts with during live operation.

![Front Panel](images/Front_Panel.png)

**Key elements on the Front Panel:**
- **Temperature display** — shows current numeric reading
- **Thermometer gauge** — visual analog-style indicator
- **Waveform Chart** — live scrolling graph of temperature over time
- **Reference Temperature knob** — user sets the alert threshold (set to 30°C in screenshot)
- **WARNING! LED** — turns green/red when threshold is breached
- **File path selector** — user specifies where TDMS file is saved
- **STOP button** — safely terminates the VI

---

## 📊 Results

The system successfully demonstrated:
- ✅ Continuous real-time temperature acquisition from the K-type thermocouple
- ✅ Live waveform plotting showing temperature variation over time
- ✅ Correct threshold comparison — WARNING LED activated when temperature exceeded reference
- ✅ Stable TDMS data logging throughout the measurement session
- ✅ Clean, user-friendly front panel interface for operator interaction

---

## 📁 Repository Structure

```
real-time-temperature-monitor/
│
├── README.md                  ← This file
├── images/
│   ├── Block_Diagram.png      ← LabVIEW Block Diagram screenshot
│   └── Front_Panel.png        ← LabVIEW Front Panel screenshot
└── docs/
    └── (lab report not available — see note below)
```

---

## ⚠️ Note on Project Files

> The original LabVIEW `.vi` project files and the formal lab report for this project were lost due to a storage issue. This repository documents the project through available implementation screenshots, which clearly show the complete Block Diagram logic and Front Panel interface. The system design, working principle, and results are fully described in this README based on the completed work.

---

## 📚 Concepts Demonstrated

- **Data Acquisition (DAQ)** — using NI hardware and LabVIEW DAQ Assistant
- **Sensor Interfacing** — K-type thermocouple signal acquisition
- **Real-Time Monitoring** — live waveform charting and indicator updates
- **Threshold-Based Alarming** — Boolean comparison logic for alert triggering
- **Data Logging** — TDMS file write for persistent storage
- **LabVIEW G Programming** — dataflow-based visual programming paradigm

---

## 👤 Author

**Raina Shakir**
BS Electrical Engineering — 5th Semester
Pakistan Institute of Engineering & Applied Sciences (PIEAS), Islamabad

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Raina_Shakir-0077B5?style=flat&logo=linkedin)](https://linkedin.com/in/raina-shakir)
[![GitHub](https://img.shields.io/badge/GitHub-RainaShakir-181717?style=flat&logo=github)](https://github.com/RainaShakir)

---

*This project was completed as part of the Measurement & Instrumentation Lab curriculum at PIEAS.*

