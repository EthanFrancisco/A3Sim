# A3Sim // Universal 3GPP LTE / 5G NR Mobility & Retainability Suite

[![3GPP Compliant](https://img.shields.io/badge/3GPP-TS%2036%2F38-blue.svg)](https://www.3gpp.org/)
[![Live Demo](https://img.shields.io/badge/Live-Demo-cyan.svg)](https://ethanfrancisco.github.io/A3Sim/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/Version-v3.9.3--PRO-cyan.svg)]()

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
* **Precision Event A3 Marker**: Handover success (`HO Event`) and ping-pong (`Ping-Pong Event`) markers explicitly bind to exact coordinates on the A3 threshold curve (`Serving RSRP + A3 Offset + Hysteresis`), guaranteeing mathematical compliance and visual clarity on the canvas.
* **Retainability & RLF Monitoring**: Real-time tracking of signal drop limits and headroom margins against custom thresholds.
* **Interactive Controls**: Fine-tune parameters instantly using standardized sliders:
  * **A3 Offset (CIO)**: $-12\text{ dB}$ to $+12\text{ dB}$
  * **Hysteresis**: $0\text{ dB}$ to $4\text{ dB}$
  * **Time-To-Trigger (TTT)**: Standard 3GPP TS 36/38 values ($0\text{ ms}$ to $5120\text{ ms}$)
  * **RLF Drop Limit**: $-120\text{ dBm}$ to $-95\text{ dBm}$

### 3. Professional OSS/BSS Interface & Mobile Support
* **Dark-Mode Command Center**: Built with Tailwind CSS and styled for telecom and RF engineering workflows.
* **3GPP Audit Trail Console**: Real-time status stream logging simulation lifecycle events, threshold violations, and severity badges (`INFO`, `SUCCESS`, `WARN`, `ERROR`) with automatic auto-scrolling.
* **Fully Responsive Mobile Layout**: Optimized grid layouts, flexible headers, and font scaling designed to run seamlessly across desktop workstations, tablets, and mobile devices.
* **CSV Telemetry Export**: Export complete simulation datasets for offline drive-test and post-processing analysis.

---

## 📐 Mathematical & 3GPP Standards Formulation

A3Sim implements standard 3GPP mobility evaluation criteria (TS 36.331 / TS 38.331) to model realistic radio link behavior:

### 1. Event A3 Condition (Neighbor Becomes Offset Better Than Serving)
A handover trigger condition is met when the neighbor cell's RSRP exceeds the serving cell's RSRP by the configured Offset plus Hysteresis over a sustained duration:
$$RSRP_{neigh} - Hysteresis > RSRP_{serv} + CIO_{offset}$$

### 2. A3 Threshold Curve
The dynamic threshold line plotted on the chart is calculated at each distance step $d$:
$$A3_{thresh}(d) = RSRP_{serv}(d) + CIO_{offset} + Hysteresis$$
* *Note: Precision marker binding locks success (`HO Event`) and ping-pong (`PP Event`) markers directly to `A3_thresh[trigIdx]` at the precise trigger index.*

### 3. Propagation & Signal Degradation
Signal attenuation across distance $d$ follows profile-aware path-loss slopes combined with multi-path fading and pseudo-random noise:
$$RSRP(d) = Base - (Slope \cdot d) - Fading(d) + Noise(d)$$

### 4. Time-To-Trigger (TTT) Filtering
To prevent premature handovers in fluctuating signal conditions, the A3 condition must remain continuously satisfied across consecutive distance steps corresponding to the selected TTT duration ($0\text{ ms}$ to $5120\text{ ms}$).

---

## 🛠️ Tech Stack

* **Frontend**: HTML5, Vanilla JavaScript (ES6+)
* **Styling**: Tailwind CSS (Dark Theme Configuration)
* **Charting**: Chart.js with responsive multi-axis rendering and custom canvas styling
* **Typography**: Inter & JetBrains Mono

---

## 🏃‍♂️ Getting Started

You can test the application instantly via the **[Live Demo](https://ethanfrancisco.github.io/A3Sim/)**, or run it locally since it is a fully self-contained, single-file application (`index.html`):

1. **Clone the repository**:
   ```bash
   git clone [https://github.com/ethanfrancisco/A3Sim.git](https://github.com/ethanfrancisco/A3Sim.git)
   cd A3Sim
