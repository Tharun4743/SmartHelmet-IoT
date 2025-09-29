🚨 Smart Helmet + IoT Bike Safety System

This project is an IoT-based Smart Helmet system that ensures rider safety by monitoring alcohol levels, helmet usage, and drowsiness. The system uses RF communication between a helmet unit (transmitter) and a bike unit (receiver).

If unsafe conditions are detected (alcohol, no helmet, or drowsiness), the bike ignition is disabled, and alerts are triggered.

📌 Features
Helmet Unit (Transmitter)

✅ Helmet Detection – Ensures the rider wears the helmet before starting.

✅ Alcohol Detection – Prevents ignition if alcohol is detected.

✅ Drowsiness Detection – Monitors blink patterns & triggers buzzer alerts.

✅ RF Transmission – Sends sensor data to the bike unit every 100ms.

✅ Buzzer Alert – Alerts the rider if drowsiness is detected.

Bike Unit (Receiver)

✅ RF Receiver – Continuously receives helmet sensor data.

✅ Ignition Control – Turns ON/OFF motor via a relay based on rider status.

✅ LCD Display – 16x2 I²C LCD shows real-time status with page switching.

✅ Buzzer Alerts – Alerts if alcohol, drowsiness, or communication failure is detected.

✅ Failsafe Mode – Turns off ignition if no data is received for 5 seconds.

🛠️ Hardware Requirements

Helmet Unit (Transmitter)

Arduino (UNO/Nano)

MQ-3 Alcohol Sensor

IR/Proximity sensor (helmet wear detection)

IR sensor (eye blink/drowsiness detection)

Buzzer

RF Transmitter module (433 MHz)

Bike Unit (Receiver)

Arduino (UNO/Nano)

RF Receiver module (433 MHz)

Relay module (for ignition control)

I²C 16x2 LCD Display (0x27 address)

Buzzer

⚡ Software Requirements

Arduino IDE

Libraries Used:

RH_ASK.h (RadioHead RF communication)

SPI.h (for RF driver)

Wire.h (I²C communication)

LiquidCrystal_I2C.h (LCD display)

📂 Project Structure
Smart-Helmet-IoT/
│
├── Helmet_Transmitter/
│   └── helmet_transmitter.ino   # Helmet-side code
│
├── Bike_Receiver/
│   └── bike_receiver.ino        # Bike-side code
│
└── README.md                    # Documentation

🚴 Working Principle

Helmet Unit reads sensor values:

Helmet not worn → sends 0.

Alcohol detected → sends 1.

Drowsy (eye blinks above threshold) → sends 1.

Data is transmitted via RF module every 100ms.

Bike Unit receives data:

If helmet = ON and alcohol = 0 → ignition enabled.

If alcohol = 1 or helmet = OFF → ignition disabled.

If drowsiness = 1 → buzzer alert.

If no data received for 5s → system goes offline, ignition OFF, buzzer ON.

🖼️ LCD Pages

Page 0 → Helmet Status + Alcohol Status

Page 1 → Sleep Status + Motor Status

Page 2 → Branding ("Agile Innovators - Smart Helmet")

🚀 Future Scope

📡 Replace RF with Bluetooth/WiFi (ESP32) for mobile app integration.

🏥 Auto-alert system to send accident data to hospitals/police.

🔋 Power optimization for real-world helmet integration.

👨‍💻 Authors

Developed by Agile Innovators Team 🧑‍💻🎓
Smart India Hackathon 2025 Submission
