# 🪖 Smart Helmet IoT Safety System — Dual-Unit Embedded Motorcycle Accident Prevention System
### *Smart India Hackathon 2025 Top 50 Submission: Proactive Wireless Ignition Interlock, MQ-3 Alcohol Sensing, IR Wear Verification & Eye-Blink Drowsiness Monitoring*

<p align="center">
  <a href="https://github.com/Tharun4743/AGILE-INNOVATORS-smart-helmet-"><b>📦 GitHub Repository</b></a>
  
</p>

---

## 1. 📌 Problem Statement
Motorcycle accidents cause catastrophic loss of life worldwide, primarily driven by three preventable behaviors: riding without helmets, alcohol-impaired driving (DUI), and driver fatigue leading to micro-sleep at high speeds. Existing motorcycle safety measures are strictly reactive (alerting emergency contacts after a crash has already occurred).

---

## 2. 🔍 Existing Solutions & Critical Gaps
Post-crash SOS beacons and emergency trackers activate only after severe physical impact has taken place. Standalone bike-mounted breathalyzers cannot confirm if a helmet is actually buckled onto the rider's head, and no commercial two-wheelers integrate real-time eye-blink drowsiness detection with wireless ignition cutoffs.

---

## 3. 💡 Proposed Solution
The Smart Helmet IoT Safety System is a proactive dual-unit embedded hardware system engineered by Team Agile Innovators for SIH 2025. It links a sensor-equipped helmet with a motorcycle ignition circuit via 433MHz RF. Motor ignition is enabled ONLY when the helmet is securely buckled AND the rider is sober. If alcohol breath or prolonged eye closure is detected, ignition is cut immediately and alarms sound, backed by a 5-second RF disconnection failsafe.

---

## 4. ⚙️ Technical Approach & System Architecture
* **Helmet Unit (Transmitter):** Arduino UNO/Nano, MQ-3 alcohol sensor, IR proximity sensor (buckle check), IR optical eye-blink sensor, 433MHz ASK RF transmitter (RadioHead RH_ASK), active buzzer. Broadcasts telemetry packets every 100ms.
* **Bike Unit (Receiver):** Arduino UNO/Nano, 433MHz RF receiver, 5V single-channel relay module wired into the ignition circuit, 16x2 I²C LCD display, piezo alert buzzer.
* **Failsafe Protocol:** If the bike ceases receiving wireless RF packets for >5 seconds, the ignition relay automatically trips open.

---

## 5. 📈 Impact & Measurable Benefits
* **Smart India Hackathon 2025 Top 50 (Internal):** Selected in the Top 50 out of 300+ campus teams and nominated for the central SIH portal.
* **Sub-500ms Emergency Ignition Cutoff:** Prevents vehicle acceleration under dangerous intoxication or microsleep conditions.
* **Proactive Life Preservation:** Enforces helmet compliance and sobriety before the vehicle can ever be operated.
* **Real-Time Visual Telemetry:** 16x2 LCD cycles through real-time safety diagnostic pages.

---

## 6. 🚀 Feasibility & Viability Analysis
* **Technical:** Validated with a working physical prototype demonstrating robust RF penetration over vehicle frames.
* **Economic:** Built with low-cost components allowing mass production for under $25 per unit.
* **Commercial Scalability:** Easily integrated as an OEM standard by motorcycle manufacturers (Honda, TVS, Yamaha, Royal Enfield).

---

## 7. 👨‍💻 Author & Intellectual Property License

### Lead Architect & Author
**Tharunkumar K** ([@Tharun4743](https://github.com/Tharun4743))
* B.Tech Information Technology • V.S.B. Engineering College, Karur
* [GitHub Profile](https://github.com/Tharun4743) • [LinkedIn](https://linkedin.com/in/tharunkumark4743) • [Portfolio](https://tharunkumark4743.netlify.app)

### 🔒 Proprietary License Notice (All Rights Reserved)
> [!CAUTION]
> **PROPRIETARY & CONFIDENTIAL INTELLECTUAL PROPERTY**
> 
> All rights reserved. This repository, its architecture, source code, workflows, firmware, and associated documentation are the exclusive intellectual property of **Tharunkumar K**.
> 
> **No entity, organization, or individual is permitted to copy, modify, distribute, publish, commercially exploit, reverse engineer, or deploy any portion of this project without express, prior written permission from the author.**
> 
> **Copyright © 2026 Tharunkumar K. All Rights Reserved.**
