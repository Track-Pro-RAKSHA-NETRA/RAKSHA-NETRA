RAKSHA-NETRA

Edge-AI Enabled Multimodal Trace Screening System

RAKSHA-NETRA is a rugged, handheld, Edge-AI-enabled presumptive trace-screening system designed to assist rapid field screening of suspected narcotic and explosive threats across railway luggage, parcels, and surfaces.

«Collect → Analyze → Alert → Securely Record → Report»

---

🚨 The Problem

Railway security personnel require rapid field-level screening capabilities that can operate with:

- Limited connectivity
- Time-sensitive inspections
- Portable equipment
- Secure and traceable event records

Conventional approaches may require centralized analysis and can be difficult to deploy for immediate field screening.

---

💡 Our Solution

RAKSHA-NETRA combines multimodal chemical sensing, Edge AI, secure logging, GPS, and wireless communication into a portable platform.

How It Works

1. Collect
Suspected sample collected using a controlled swab-based process.

2. Analyze
Multiple sensor modalities capture chemical and optical responses.

3. Fuse
STM32 + Raspberry Pi 5 process and combine sensor data.

4. Classify
TensorFlow Lite performs on-device Edge-AI inference.

5. Alert
Audio, visual, and vibration alerts indicate a presumptive threat condition.

6. Securely Record
Events are protected using cryptographic security mechanisms.

7. Report
Relevant event information can be transmitted to the monitoring dashboard.

---

🔬 Multimodal Sensing

BME688 + SGP40
VOC response sensing

SPCE + AD5940
Electrochemical response sensing

TCS34725 + Camera
Colorimetric and optical analysis

⬇️

Multi-Modal Chemical-Response Fingerprinting

Multiple sensor responses are combined to provide a richer input for Edge-AI classification.

---

🧠 Edge-AI Architecture

MULTIMODAL SENSORS
        ↓
     STM32
Sensor Acquisition & Control
        ↓
  RASPBERRY PI 5
Preprocessing + Sensor Fusion
        ↓
  TENSORFLOW LITE
  Edge-AI Inference
        ↓
PRESUMPTIVE THREAT

---

🔐 Secure Event Logging

RAKSHA-NETRA incorporates:

AES-256 Encryption
SHA-256 Hashing
Hash-Chained Event Records
GPS + Timestamp + Device ID
Offline Local Storage

This enables a cryptographically verifiable event history for screening events.

---

📡 Offline-First

The system is designed to continue functioning when network connectivity is unavailable.

NO NETWORK
    ↓
LOCAL STORAGE
    ↓
SECURE EVENT LOG
    ↓
CONNECTIVITY AVAILABLE
    ↓
SECURE SYNCHRONIZATION
    ↓
RPF DASHBOARD

---

📊 Monitoring Dashboard

The proposed RPF dashboard can provide:

- Screening event information
- Presumptive threat alerts
- Device ID
- Timestamp
- GPS location
- Event status
- Secure event history

---

⚙️ Core Technologies

Component| Technology
MCU| STM32
Edge Computer| Raspberry Pi 5
AI| TensorFlow Lite
VOC Sensors| BME688 + SGP40
Electrochemical| SPCE + AD5940
Optical| TCS34725 + Camera
Security| AES-256 + SHA-256
Communication| Wi-Fi / 4G / MQTT / REST
Prototype| Figma
PCB| EasyEDA

---

🎨 Prototype

Figma Prototype:
Wokwi Prototype:
EasyEDA Prototype:

---

🎯 Intended Application

RAKSHA-NETRA is designed as a rapid presumptive screening and decision-support prototype for railway security environments.

Potential applications include:

- Railway luggage screening
- Parcel screening
- Surface screening
- Platform inspection
- Railway yard inspection
- Field security operations

«Note: RAKSHA-NETRA is a presumptive screening prototype. Results should be confirmed through appropriate authorized laboratory procedures.»

---

🏆 Project

RAKSHA-NETRA

Edge AI × Multimodal Sensing × Cybersecurity

Developed for Smart India Hackathon

KLN College of Engineering
