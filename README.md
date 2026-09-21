# A3Sim: Universal 3GPP LTE / 5G NR Handover & Retainability Simulator

**A3Sim** is a lightweight, professional-grade, vendor-agnostic web application designed to simulate Radio Network Optimization (RNO) handover events (Event A3), Time-To-Trigger (TTT), hysteresis, and Radio Link Failure (RLF) retainability KPIs based on **3GPP TS 36.331 / TS 38.331 specifications**.

Built with single-file portability in mind, it requires no backend installation, making it instantly accessible across desktop browsers and mobile devices.

---

## 🚀 Live Demo
Access the live simulator hosted on GitHub Pages:
👉 **[https://ethanfrancisco.github.io/A3Sim/](https://ethanfrancisco.github.io/A3Sim/)**

---

## 📡 Key Features
* **Universal 3GPP Standards Compliance:** Universally applicable across major RAN vendors (Ericsson, Nokia, Huawei, Samsung, and Open RAN architectures).
* **Real-Time Telemetry & KPI Cards:** Live numerical indicators tracking Serving RSRP, Neighbor RSRP, A3 Margin, TTT progression, and RLF headroom.
* **Interactive Parameter Tuning:** Adjust physical and logical parameters on the fly via responsive range sliders:
  * Serving & Neighbor Reference Signal Receive Power (RSRP)
  * A3 Offset (dB)
  * Hysteresis (dB)
  * Time-To-Trigger (ms)
* **Dynamic Charting:** Interactive gradient waveform rendering via Chart.js with visual trigger indicators and drop markers.
* **Live Audit Console:** Built-in operations center log detailing simulation events, parameter adjustments, and handover transitions.
* **CSV Telemetry Export:** Export real-time simulation datasets for offline post-processing and analysis.
* **Fully Responsive UI:** Optimized for desktop command centers, tablets, and mobile smartphones.

---

## 🧠 Technical Overview & 3GPP Compliance

The simulator models the classic handover triggering condition governed by **3GPP specifications**:

$$Mp + Ocp + Hys < Mn + Ocn - Off$$

Where:
* **$Mp / Mn$:** Measured RSRP of the Serving cell and Neighbor cell respectively.
* **$Ocp / Ocn$:** Cell-specific offsets.
* **$Hys$:** Hysteresis parameter preventing ping-pong handovers.
* **$Off$:** A3 Offset defining the threshold margin required for triggering Event A3.

If the condition holds continuously for the duration of the **Time-To-Trigger (TTT)** timer, a successful handover is executed. If the serving cell signal degrades below the **RLF Threshold** before a handover completes, a Radio Link Failure (retainability drop) is logged.

---

## 🛠️ Tech Stack
* **HTML5 / Single-Page Architecture**
* **Tailwind CSS** (for enterprise OSS/NMS dark-mode styling)
* **Chart.js** (for high-performance telemetry visualization)
* **GitHub Pages** (for static hosting)

---

## ⚙️ Local Installation & Usage

Because `A3Sim` is completely self-contained within a single `index.html` file, running it locally requires zero complex build pipelines or node module installations.

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/](https://github.com/)<your-username>/A3Sim.git
   cd A3Sim
