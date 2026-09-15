RAKSHA-NETRA

Intelligent Sensing • Edge AI • Cybersecure Detection

Smart India Hackathon 2026 | PS 26026 | Hardware | Team Track Pro

«Detect Locally. Decide Intelligently. Record Securely.»

🎯 Problem

Indian Railways requires a rapid, field-ready approach for screening suspicious narcotic and explosive traces across luggage, parcels, coaches, platforms and yards.

Conventional confirmation can be laboratory-dependent, while railway environments may also have limited connectivity.

💡 Our Solution

RAKSHA-NETRA is a rugged handheld presumptive field-screening system that combines:

- Swab-based trace sampling
- Controlled thermal desorption
- Multimodal chemical sensing
- Edge AI classification
- Offline operation
- Instant operator alerts
- GPS-tagged secure event logging

How It Works

SWAB
  ↓
DESORB
  ↓
SENSE
  ↓
EDGE AI
  ↓
THREAT CLASS + CONFIDENCE
  ↓
ALERT
  ↓
SECURE EVENT + GPS + TIMESTAMP
  ↓
SYNC WHEN CONNECTED

🔬 Technology Stack

Layer| Technology
Sensing| MOS + Colorimetric + Electrochemical + SAW
Control| STM32
Edge Computing| Raspberry Pi
AI| TensorFlow Lite / Lightweight Edge Model
Security| AES-256 + SHA-256 Hash Chain
Connectivity| Wi-Fi / 4G-LTE

⭐ What Makes RAKSHA-NETRA Different?

1. Offline-First Edge AI

The device can perform its core screening locally without depending on the internet.

2. Multimodal Sensing

Multiple sensing modalities are combined to obtain complementary chemical-response patterns.

3. Secure Event History

Each screening event can include classification, confidence, GPS, timestamp and device identity, with hash chaining providing tamper-evident integrity.

4. Field-Ready Architecture

The system is designed around a portable, modular and rugged handheld workflow for railway security personnel.

🔐 Cybersecurity

The device is designed to protect the integrity of screening records.

EVENT 1 → HASH 1
              ↓
EVENT 2 + HASH 1 → HASH 2
                         ↓
EVENT 3 + HASH 2 → HASH 3

If an earlier record is modified, the chain can reveal the integrity violation.

«Hash chain is used for tamper evidence; it is not itself a blockchain.»

🧠 Edge AI

Sensor responses are processed locally:

RAW SIGNALS
    ↓
SIGNAL PROCESSING
    ↓
SENSOR FUSION
    ↓
EDGE AI
    ↓
CLASS + CONFIDENCE

This enables local decision support even when network connectivity is unavailable.

🧪 Validation

We follow:

«CLAIM → TEST → MEASURE → EVIDENCE»

Key validation areas:

- Sensor response & repeatability
- Sensor drift & cross-sensitivity
- AI accuracy and F1-score
- Edge inference latency
- Offline operation & synchronization
- Hash-chain integrity
- Thermal safety
- Ruggedization

No performance numbers are claimed until experimentally validated.

🛡️ Scope

RAKSHA-NETRA is a presumptive screening system, not a replacement for confirmatory laboratory analysis.

A suspicious result is intended to support appropriate follow-up and confirmation.

🚀 Vision

«Close the gap between encountering a suspicious trace in the field and creating a rapid, traceable and security-aware screening event.»

Current Status: Core architecture and multiple subsystems are under development, integration and validation.

---

RAKSHA-NETRA

SIH 2026 • PS 26026 • Team Track Pro
