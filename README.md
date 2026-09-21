# A3Sim // Universal 3GPP LTE / 5G NR Mobility & Retainability Suite

[![3GPP Compliant](https://img.shields.io/badge/3GPP-TS%2036%2F38-blue.svg)](https://www.3gpp.org/)
[![Live Demo](https://img.shields.io/badge/Live-Demo-cyan.svg)](https://ethanfrancisco.github.io/A3Sim/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/Version-v3.7--PRO-cyan.svg)]()

**A3Sim** is a vendor-agnostic, web-based radio network optimization (RNO) and mobility simulator designed to model cellular handovers, Event A3 triggers, and retainability (Radio Link Failure / RLF) across diverse macro-cell and micro-cell propagation environments.

🌐 **[Access the Live A3Sim Dashboard Here](https://ethanfrancisco.github.io/A3Sim/)**

---

## 🚀 Key Features & Capabilities

### 1. 3GPP Compliant Propagation Profiles
Model different deployment topologies with profile-aware path-loss slopes, fading frequencies, and dynamic distance scaling:
* **Urban Macro (UMa - 500m ISD)**: Standard urban macro layout with moderate path loss.
* **Suburban Macro (1km ISD)**: Wide-area suburban deployment with gradual signal degradation.
* **Rural Macro (RMa - 1.5km+ ISD)**: Open-terrain long-range link requiring high link stability and large TTT windows.
* **Urban Micro / Small Cell**: Dense small-cell deployment with rapid signal drops and tight handover boundaries.
* **Microcell Cluster (Ping-Pong Risk)**: Overlapping sectors prone to frequent handovers and potential RLF during fast movement.

### 2. Rigorous Mobility Analytics & Visualization
* **Precision Event A3 Marker**: The green handover success marker explicitly locks onto the exact **A3 Threshold intersection point** (`Serving RSRP + A3 Offset + Hysteresis`), providing true 3GPP mathematical compliance and visual clarity.
* **Retainability & RLF Monitoring**: Real-time tracking of signal drop limits and headroom margins against custom thresholds.
* **Interactive Controls**: Fine-tune parameters instantly using standardized sliders:
  * **A3 Offset (CIO)**: $-12\text{ dB}$ to $+12\text{ dB}$
  * **Hysteresis**: $0\text{ dB}$ to $4\text{ dB}$
  * **Time-To-Trigger (TTT)**: Standard 3GPP TS 36/38 values ($0\text{ ms}$ to $5120\text{ ms}$)
  * **RLF Drop Limit**: $-120\text{ dBm}$ to $-95\text{ dBm}$

### 3. Professional OSS/BSS Interface
* **Dark-Mode Command Center**: Built with Tailwind CSS and styled for telecom and RF engineering workflows.
* **Live Audit Trail Console**: Real-time status stream logging simulation events, scenario switches, and threshold violations.
* **CSV Telemetry Export**: Export complete simulation datasets (Distance, Serving RSRP, Neighbor RSRP) for offline drive-test and post-processing analysis.

---

## 🛠️ Tech Stack

* **Frontend**: HTML5, Vanilla JavaScript (ES6+)
* **Styling**: Tailwind CSS (Dark Theme Configuration)
* **Charting**: Chart.js with responsive multi-axis rendering and custom canvas gradients
* **Typography**: Inter & JetBrains Mono

---

## 🏃‍♂️ Getting Started

You can test the application instantly via the **[Live Demo](https://ethanfrancisco.github.io/A3Sim/)**, or run it locally since it is a fully self-contained, single-file application:

1. **Clone the repository**:
   ```bash
   git clone [https://github.com/your-username/a3-mobility-simulator.git](https://github.com/your-username/a3-mobility-simulator.git)
   cd a3-mobility-simulator
