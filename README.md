<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,2,2,5,30&height=200&section=header&text=🪖%20Smart%20Helmet&fontSize=50&fontColor=fff&animation=twinkling&fontAlignY=35&desc=IoT%20Bike%20Safety%20System&descAlignY=58&descSize=22" width="100%"/>
</div>

<div align="center">

![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black)
![RF 433MHz](https://img.shields.io/badge/RF-433MHz-FF6B35?style=flat-square&logo=airplayvideo&logoColor=white)
![IoT](https://img.shields.io/badge/IoT-Safety%20System-2ECC71?style=flat-square&logo=internetexplorer&logoColor=white)
![SIH 2025](https://img.shields.io/badge/SIH%202025-Top%2050%20Nationally-gold?style=flat-square&logo=trophy&logoColor=white)

</div>

<div align="center">

[![GitHub stars](https://img.shields.io/github/stars/Tharun4743/Smart-Helmet-IoT-Safety-System?style=flat-square&color=yellow)](https://github.com/Tharun4743/Smart-Helmet-IoT-Safety-System/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/Tharun4743/Smart-Helmet-IoT-Safety-System?style=flat-square&color=blue)](https://github.com/Tharun4743/Smart-Helmet-IoT-Safety-System/network)
[![GitHub last commit](https://img.shields.io/github/last-commit/Tharun4743/Smart-Helmet-IoT-Safety-System?style=flat-square&color=green)](https://github.com/Tharun4743/Smart-Helmet-IoT-Safety-System/commits)
[![License](https://img.shields.io/github/license/Tharun4743/Smart-Helmet-IoT-Safety-System?style=flat-square)](https://github.com/Tharun4743/Smart-Helmet-IoT-Safety-System/blob/main/LICENSE)

</div>

---

<div align="center">
  <h3>🏆 Smart India Hackathon 2025 — National Top 50 (0.5% acceptance out of 10,000+ teams)</h3>
  <p><i>An intelligent IoT helmet system that proactively prevents accidents by monitoring helmet wear, alcohol levels, and drowsiness — disabling bike ignition on unsafe conditions via RF communication.</i></p>
</div>

---

## 📌 Table of Contents

- [🎯 Overview](#-overview)
- [⚙️ How It Works](#️-how-it-works)
- [✨ Features](#-features)
- [🛠️ Hardware Requirements](#️-hardware-requirements)
- [💻 Software Requirements](#-software-requirements)
- [📂 Project Structure](#-project-structure)
- [🖥️ LCD Display Pages](#️-lcd-display-pages)
- [🚀 Future Scope](#-future-scope)
- [👨‍💻 Authors](#-authors)

---

## 🎯 Overview

The **Smart Helmet IoT Safety System** is a dual-unit embedded system designed to eliminate the three leading causes of two-wheeler accidents:

| Threat | Detection Method | Response |
|--------|-----------------|----------|
| 🪖 No helmet worn | IR/Proximity sensor | Ignition disabled |
| 🍺 Alcohol consumption | MQ-3 alcohol sensor | Ignition disabled |
| 😴 Drowsiness | Eye blink pattern (IR sensor) | Buzzer alert + ignition cut |

The two units communicate wirelessly via **RF 433MHz** — the helmet unit transmits sensor data every **100ms** and the bike unit acts on it in real time.

---

## ⚙️ How It Works

```
┌─────────────────────────────────────────────────┐
│              HELMET UNIT (Transmitter)           │
│                                                  │
│  [MQ-3 Sensor] ──► Alcohol check                │
│  [IR Proximity] ──► Helmet wear check            │
│  [IR Eye Blink] ──► Drowsiness check             │
│                        │                         │
│              [Arduino UNO/Nano]                  │
│                        │                         │
│           [RF Transmitter 433MHz]                │
└────────────────────────┼────────────────────────┘
                         │ RF Signal (every 100ms)
                         ▼
┌─────────────────────────────────────────────────┐
│               BIKE UNIT (Receiver)               │
│                                                  │
│            [RF Receiver 433MHz]                  │
│                        │                         │
│              [Arduino UNO/Nano]                  │
│               /        │        \                │
│    [Relay] [LCD 16x2] [Buzzer]                  │
│       │                                          │
│  [Ignition ON/OFF]                              │
│                                                  │
│  ✅ Helmet ON + No Alcohol → Ignition ENABLED   │
│  ❌ Alcohol / No Helmet  → Ignition DISABLED    │
│  ⚠️  Drowsiness Detected  → Buzzer ALERT        │
│  📡 No Signal for 5s     → Failsafe OFF         │
└─────────────────────────────────────────────────┘
```

---

## ✨ Features

### 🪖 Helmet Unit (Transmitter)

| Feature | Description |
|---------|-------------|
| ✅ Helmet Detection | Ensures rider wears the helmet before starting |
| 🍺 Alcohol Detection | MQ-3 sensor detects alcohol presence, blocks ignition |
| 😴 Drowsiness Detection | Monitors eye blink patterns, triggers buzzer on drowsiness |
| 📡 RF Transmission | Sends sensor data to bike unit every 100ms |
| 🔔 Buzzer Alert | Alerts the rider immediately on drowsiness detection |

### 🏍️ Bike Unit (Receiver)

| Feature | Description |
|---------|-------------|
| 📡 RF Receiver | Continuously receives helmet sensor data wirelessly |
| ⚡ Ignition Control | Relay-based motor ON/OFF based on rider safety status |
| 🖥️ LCD Display | 16x2 I²C LCD shows real-time status with page switching |
| 🔔 Buzzer Alerts | Alerts for alcohol, drowsiness, or communication failure |
| 🛡️ Failsafe Mode | Auto-disables ignition if no RF data received for 5 seconds |

---

## 🛠️ Hardware Requirements

<details>
<summary><b>🪖 Helmet Unit (Transmitter) — Click to expand</b></summary>

| Component | Purpose |
|-----------|---------|
| Arduino UNO / Nano | Main microcontroller |
| MQ-3 Alcohol Sensor | Detects alcohol in breath |
| IR / Proximity Sensor | Detects whether helmet is worn |
| IR Sensor (Eye Blink) | Monitors blink rate for drowsiness |
| Buzzer | Alerts rider on drowsiness |
| RF Transmitter 433MHz | Sends data to bike unit wirelessly |

</details>

<details>
<summary><b>🏍️ Bike Unit (Receiver) — Click to expand</b></summary>

| Component | Purpose |
|-----------|---------|
| Arduino UNO / Nano | Main microcontroller |
| RF Receiver 433MHz | Receives data from helmet unit |
| Relay Module | Controls bike ignition ON/OFF |
| 16x2 I²C LCD (0x27) | Displays real-time safety status |
| Buzzer | Alerts on unsafe conditions |

</details>

---

## 💻 Software Requirements

![Arduino IDE](https://img.shields.io/badge/Arduino_IDE-00979D?style=flat-square&logo=arduino&logoColor=white)

**Libraries required — install via Arduino Library Manager:**

```
RH_ASK.h          → RadioHead RF communication
SPI.h             → SPI driver for RF module
Wire.h            → I²C communication
LiquidCrystal_I2C.h → LCD display control
```

**Install steps:**
1. Open Arduino IDE → **Sketch** → **Include Library** → **Manage Libraries**
2. Search and install each library above
3. Connect your Arduino via USB → select correct **Board** and **Port**
4. Upload `helmet_transmitter.ino` to helmet Arduino
5. Upload `bike_receiver.ino` to bike Arduino

---

## 📂 Project Structure

```
Smart-Helmet-IoT/
│
├── 📁 Helmet_Transmitter/
│   └── 📄 helmet_transmitter.ino     # Helmet-side Arduino code
│
├── 📁 Bike_Receiver/
│   └── 📄 bike_receiver.ino          # Bike-side Arduino code
│
└── 📄 README.md                       # Documentation
```

---

## 🖥️ LCD Display Pages

The bike unit LCD cycles through 3 informational pages:

```
┌──────────────────┐   ┌──────────────────┐   ┌──────────────────┐
│  Page 0          │   │  Page 1          │   │  Page 2          │
│  Helmet : ON ✅  │   │  Sleep  : OK ✅  │   │ Agile Innovators │
│  Alcohol: NO ✅  │   │  Motor  : ON ✅  │   │  Smart Helmet    │
└──────────────────┘   └──────────────────┘   └──────────────────┘
```

---

## 🚀 Future Scope

- 📡 **ESP32 Integration** — Replace RF 433MHz with WiFi/Bluetooth for mobile app connectivity
- 🏥 **Emergency SOS** — Auto-alert system to notify hospitals and police on accident detection
- 📱 **Mobile Dashboard** — Real-time monitoring app for parents/fleet managers
- 🔋 **Power Optimization** — Ultra-low-power design for real-world helmet integration
- 🌐 **Cloud Logging** — Store ride safety data to cloud for analytics

---

## 👨‍💻 Authors

<div align="center">

**Developed by Team Agile Innovators**
*Smart India Hackathon 2025 Submission*

| Developer | Profile |
|-----------|---------|
| Tharunkumar K | [![GitHub](https://img.shields.io/badge/GitHub-Tharun4743-181717?style=flat-square&logo=github)](https://github.com/Tharun4743) [![LinkedIn](https://img.shields.io/badge/LinkedIn-tharunkumark4743-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/tharunkumark4743) |

</div>

---

<div align="center">
  <p>⭐ If this project helped or inspired you, please give it a star!</p>
  <p>
    <a href="https://github.com/Tharun4743">
      <img src="https://img.shields.io/badge/More%20Projects-Tharun4743-181717?style=flat-square&logo=github&logoColor=white"/>
    </a>
    &nbsp;
    <a href="https://tharunkumark4743.netlify.app">
      <img src="https://img.shields.io/badge/Portfolio-tharunkumark4743.netlify.app-00C7B7?style=flat-square&logo=netlify&logoColor=white"/>
    </a>
  </p>
</div>

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,2,2,5,30&height=100&section=footer" width="100%"/>
</div>
