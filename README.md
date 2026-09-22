🛡️ RAKSHA-NETRA

Railway-Aware Multimodal Trace Intelligence for Rapid Field Screening

Smart India Hackathon 2026 | Problem Statement 26026 | Hardware

«Detect Locally. Decide Intelligently. Record Securely.»

RAKSHA-NETRA is a proposed rugged, handheld Edge-AI presumptive screening system designed for rapid field-level screening of suspicious narcotic and explosive traces across Indian Railway environments.

The system combines:

Controlled Sample Handling + Multimodal Trace Sensing + Edge AI + Secure Event Logging + Offline-First Connectivity

The architecture is designed to support rapid screening of:

- Luggage
- Parcels
- Packages
- Coach surfaces
- Platforms
- Railway yards
- Other vulnerable or difficult-to-screen locations

A complementary mobile quadruped architecture is also defined for autonomous patrol, remote inspection and operation in hazardous or inaccessible railway environments.

---

🚆 1. Problem Context

Indian Railway security environments demand screening systems that can operate across large, crowded and heterogeneous spaces while maintaining rapid response and reliable event records.

Conventional security screening may involve combinations of:

- X-ray inspection
- Canine-based detection
- Visual inspection
- Laboratory confirmation
- Standalone trace-detection systems

However, field deployment can involve practical constraints such as:

- Large railway premises
- High passenger and luggage throughput
- Difficult-to-access areas
- Variable environmental conditions
- Limited network connectivity
- Requirement for rapid preliminary screening
- Need for traceable security-event records

The design objective of RAKSHA-NETRA

«Reduce the gap between encountering a suspicious trace and generating a rapid, structured, traceable field-screening event.»

---

💡 2. Proposed Solution

RAKSHA-NETRA follows a multimodal evidence-fusion architecture.

Instead of relying on a single sensing modality, the proposed handheld system combines complementary chemical and optical responses.

Core pipeline

SAMPLE
   ↓
CONTROLLED SAMPLE HANDLING
   ↓
MULTIMODAL TRACE SENSING
   ↓
SIGNAL ACQUISITION & CONDITIONING
   ↓
EDGE AI + SENSOR FUSION
   ↓
THREAT?
   ├── NO  → NORMAL SCREENING EVENT
   └── YES → PRESUMPTIVE ALERT
                    ↓
             SECURE EVENT RECORD
                    ↓
               RPF DASHBOARD
                    ↓
       SYNC / STORE-AND-FORWARD

Both Normal and Alert screening outcomes are intended to generate an event record, enabling complete screening traceability.

---

🔬 3. Core Technology Stack

Layer| Proposed Technology
Sample collection| Swab-based trace collection
Sample handling| Controlled thermal desorption
MOX sensing| Bosch BME688 + Sensirion SGP40
Electrochemical sensing| SPCE + AD5940 AFE
Colorimetric / optical sensing| TCS34725 + Camera
Sensor control| STM32
Edge computing| Raspberry Pi 5
Edge AI| LiteRT / lightweight on-device model
Data processing| Signal preprocessing + multimodal sensor fusion
User interface| Touchscreen + audio + vibration alerts
Localization| GPS
Event integrity| AES-256 + SHA-256 + hash chaining
Connectivity| Wi-Fi + 4G/LTE
Messaging / integration| MQTT / REST
Offline resilience| Local storage + store-and-forward synchronization
Central monitoring| RPF-oriented dashboard

«Note: Final component selection, model architecture and hardware parameters remain subject to prototype validation and integration testing.»

---

🧪 4. Multimodal Trace Intelligence

RAKSHA-NETRA is based on the principle that chemically different materials can produce different response patterns across complementary sensing modalities.

4.1 MOX / VOC Response

BME688 + SGP40

Provides gas/VOC-related response patterns that can contribute to a chemical-response fingerprint.

4.2 Electrochemical Response

SPCE + AD5940

Provides electrochemical measurements that can complement gas-phase sensing.

4.3 Colorimetric + Optical Response

TCS34725 + Camera

Captures optical/colorimetric changes associated with a controlled sensing process.

Sensor-fusion objective

MOX RESPONSE
      +
ELECTROCHEMICAL RESPONSE
      +
OPTICAL / COLOR RESPONSE
      ↓
FEATURE EXTRACTION
      ↓
MULTIMODAL SENSOR FUSION
      ↓
EDGE AI CLASSIFICATION
      ↓
THREAT CLASS + CONFIDENCE SCORE

The intended output is a presumptive threat classification, not legal identification or laboratory confirmation.

---

⚙️ 5. Controlled Sample Handling

The handheld architecture uses a controlled sample-handling workflow to improve consistency between sampling events.

SURFACE / ITEM
      ↓
SWAB COLLECTION
      ↓
CONTROLLED TRANSFER
      ↓
THERMAL DESORPTION
      ↓
SENSOR ARRAY
      ↓
SIGNAL ACQUISITION

Controlled handling is important because sensing performance can be influenced by:

- Sampling variability
- Temperature
- Humidity
- Background VOCs
- Sensor drift
- Cross-sensitivity
- Contamination
- Desorption conditions

The implementation therefore treats sample handling as part of the sensing system, rather than as a separate step.

---

🧠 6. Edge AI Architecture

A key design objective is to perform screening intelligence locally on the device.

RAW SENSOR SIGNALS
        ↓
NOISE FILTERING
        ↓
BASELINE CORRECTION
        ↓
FEATURE EXTRACTION
        ↓
SENSOR FUSION
        ↓
LIGHTWEIGHT EDGE MODEL
        ↓
THREAT CLASSIFICATION
        ↓
CONFIDENCE SCORE

Edge computing split

STM32
│
├── Sensor acquisition
├── Heater / thermal control
├── Safety monitoring
├── Timing
└── Diagnostics
        │
        ↓
Raspberry Pi 5
│
├── Signal preprocessing
├── Sensor fusion
├── Edge AI inference
├── Event generation
└── User interface / connectivity

The architecture is intended to remain functional for core screening operations without requiring continuous cloud connectivity.

---

📡 7. Offline-First Intelligence

Railway environments cannot always guarantee continuous network availability.

RAKSHA-NETRA therefore follows an offline-first architecture.

When connectivity is available

SCREENING
   ↓
LOCAL AI DECISION
   ↓
SECURE EVENT
   ↓
RPF DASHBOARD

When connectivity is unavailable

SCREENING
   ↓
LOCAL AI DECISION
   ↓
SECURE LOCAL EVENT STORE
   ↓
OFFLINE QUEUE
   ↓
NETWORK RESTORED
   ↓
AUTOMATIC SYNCHRONIZATION

This prevents loss of screening records solely because the device temporarily loses connectivity.

---

🔐 8. Secure Event Intelligence

Every screening interaction can generate a structured event containing fields such as:

Event ID
Device ID
Timestamp
GPS Location
Screening Result
Threat Class
Confidence Score
Sensor Metadata
System Status
Integrity Hash

Hash-chain concept

EVENT 01
   ↓
HASH 01
   ↓
EVENT 02 + HASH 01
   ↓
HASH 02
   ↓
EVENT 03 + HASH 02
   ↓
HASH 03

Each event can reference the integrity value of the previous event.

This makes unauthorized modification of historical event records detectable through integrity verification.

Security architecture

DATA
 ↓
AES-256 PROTECTION
 ↓
EVENT HASHING
 ↓
HASH-CHAIN LINKING
 ↓
SECURE LOCAL STORAGE
 ↓
RPF DASHBOARD

«Important: A hash chain provides tamper evidence; it is not itself a blockchain.»

A future railway-scale deployment could additionally use a permissioned integrity-anchoring mechanism where required.

---

🛰️ 9. RPF Dashboard Integration

The system is intended to convert individual screening actions into structured field intelligence.

Dashboard event flow

HANDHELD / QUADRUPED
          ↓
     SCREENING EVENT
          ↓
  TIMESTAMP + GPS + DEVICE ID
          ↓
      SECURE EVENT
          ↓
       RPF DASHBOARD
          ↓
   INCIDENT MONITORING
          ↓
   RESPONSE / FOLLOW-UP

The dashboard concept can provide:

- Device status
- Screening events
- Threat-class distribution
- GPS-tagged incidents
- Confidence information
- Timestamped records
- Device identification
- Connectivity status
- Offline synchronization status
- Event-integrity verification

---

🤖 10. Quadruped Extension

The overall solution architecture also defines a mobile quadruped variant for environments where a handheld operator may have limited access.

Four-layer architecture

INTELLIGENT PERCEPTION
        ↓
AUTONOMOUS NAVIGATION
        ↓
SMART INSPECTION & RESPONSE
        ↓
SECURE & RESILIENT OPERATIONS

Intelligent Perception

Potential sensor suite:

- LiDAR
- RGB camera
- Thermal imaging
- Chemical sensing

Autonomous Navigation

Potential capabilities:

- LiDAR-SLAM
- Sensor fusion
- Obstacle avoidance
- GPS-denied navigation

Smart Inspection & Response

Potential inspection targets:

- Coaches
- Underframes
- Concealed spaces
- Luggage areas
- Restricted / hazardous locations

Secure & Resilient Operations

The quadruped follows the same security-event philosophy as the handheld architecture:

DETECT
 ↓
CLASSIFY
 ↓
ALERT
 ↓
GPS / TIMESTAMP
 ↓
SECURE EVENT
 ↓
RPF DASHBOARD

«Quadruped functions are currently treated as an architectural/prototyping extension unless explicitly demonstrated in hardware.»

---

🖥️ 11. Prototype Development

RAKSHA-NETRA is being represented through multiple prototype layers.

Prototype A — Wokwi

Used for:

- Embedded-system logic
- Microcontroller workflow
- Sensor interfacing concepts
- Alert logic
- Data-flow demonstration

Demo:
"<PASTE WOKWI LINK HERE>"

---

Prototype B — Figma

Used for:

- Handheld UI
- Threat-alert interface
- Confidence-score presentation
- GPS/event display
- Offline status
- RPF dashboard concept

Demo:
"<PASTE FIGMA LINK HERE>"

---

Prototype C — EasyEDA

Used for:

- Electronic architecture
- Sensor integration concept
- Circuit design
- PCB planning
- Hardware interconnection

Demo / Project:
"<PASTE EASYEDA LINK HERE>"

---

🎥 12. Demonstration

Video Demonstration

"<PASTE YOUTUBE DEMO LINK HERE>"

Important demonstration note

The current demonstration represents a prototype / proof-of-concept architecture and does not claim to be a production-certified railway security device.

---

📊 13. Validation Philosophy

RAKSHA-NETRA follows an evidence-driven development process:

CLAIM
  ↓
TEST
  ↓
MEASURE
  ↓
REPEAT
  ↓
DOCUMENT
  ↓
EVIDENCE

Planned validation areas

Area| What will be evaluated
Sensor response| Response consistency
Repeatability| Repeated measurements under controlled conditions
Drift| Long-term sensor baseline variation
Cross-sensitivity| Response to interfering compounds / environmental backgrounds
AI performance| Accuracy, precision, recall, F1-score
Confidence calibration| Relationship between confidence and observed classification
Latency| Sampling-to-inference time
Offline mode| Local operation without network
Synchronization| Store-and-forward reliability
Security| Hash-chain integrity verification
Thermal safety| Controlled heating and protection
Environmental robustness| Temperature / humidity variation
Ruggedness| Mechanical and field-use validation

Evidence principle

«No performance number is treated as a final claim until experimentally validated.»

---

💰 14. Cost Strategy

The design objective is to create a cost-conscious architecture using commercially available embedded hardware and modular sensing components.

Current prototype-level cost planning should be treated as a target estimate, not a finalized production BOM.

Target prototype architecture

SENSORS
+
AFE
+
STM32
+
RASPBERRY PI
+
DISPLAY
+
POWER
+
COMMUNICATION
+
ENCLOSURE
=
COST-OPTIMIZED FIELD PLATFORM

Final production cost will depend on:

- Sensor selection
- Mechanical enclosure
- Battery system
- Display
- Communication module
- PCB manufacturing
- Calibration requirements
- Ruggedization
- Certification
- Production volume

---

🏗️ 15. Product Architecture

┌───────────────────────────────────────────────┐
│              FIELD ENVIRONMENT                │
│      Luggage • Parcel • Coach • Platform      │
└──────────────────────┬────────────────────────┘
                       ↓
             CONTROLLED SAMPLE HANDLING
                       ↓
              MULTIMODAL TRACE SENSING
       ┌───────────────┼────────────────┐
       ↓               ↓                ↓
      MOX       ELECTROCHEMICAL     OPTICAL
       │               │                │
       └───────────────┼────────────────┘
                       ↓
              STM32 DATA ACQUISITION
                       ↓
              RASPBERRY PI 5
                       ↓
             SIGNAL PREPROCESSING
                       ↓
            MULTIMODAL SENSOR FUSION
                       ↓
                  EDGE AI
                       ↓
          THREAT CLASS + CONFIDENCE
                 ┌─────┴─────┐
                 ↓           ↓
              NORMAL       ALERT
                 └─────┬─────┘
                       ↓
               SECURE EVENT LOG
                       ↓
              GPS + TIMESTAMP +
                  DEVICE ID
                       ↓
                RPF DASHBOARD
                       ↓
           STORE / SYNC / MONITOR

---

⭐ 16. What Makes RAKSHA-NETRA Different?

Railway-Specific Deployment

Designed around railway screening locations rather than generic laboratory environments.

Handheld Edge Architecture

Moves preliminary screening capability closer to the point of encounter.

Multimodal Sensing

Combines complementary sensing modalities instead of depending on a single measurement channel.

On-Device AI

Local inference reduces dependence on continuous cloud connectivity.

Presumptive Threat + Confidence

Provides a structured preliminary screening result rather than presenting the output as laboratory identification.

Offline-First Operation

Screening and event generation can continue during connectivity loss.

GPS-Tagged Security Events

Connects physical screening activity to time and location.

Tamper-Evident Records

Hash-chain integrity can help detect modification of stored screening history.

Centralized RPF-Oriented Monitoring

Designed to convert device-level events into centralized operational intelligence.

---

🔬 17. Development Status

Component| Status
Problem analysis| ✅ Completed
System architecture| ✅ Defined
Handheld concept| ✅ Defined
Multimodal sensing architecture| ✅ Defined
STM32 control architecture| ✅ Defined
Raspberry Pi Edge-AI architecture| ✅ Defined
Figma UI prototype| 🔄 Prototype / Development
Wokwi embedded prototype| 🔄 Prototype / Development
EasyEDA hardware design| 🔄 Prototype / Development
RPF dashboard concept| 🔄 Prototype / Development
AI model training| 🔄 Development / Validation
Sensor calibration| 🔄 Validation
Integrated physical prototype| 🔄 Development
Railway field validation| ⏳ Future
Production certification| ⏳ Future

Legend:

✅ Defined / completed
🔄 Under development / prototype
⏳ Future phase

---

🛣️ 18. Development Roadmap

PHASE 1
System Architecture
        ↓
PHASE 2
Sensor & Electronics Prototype
        ↓
PHASE 3
Controlled Sample Handling
        ↓
PHASE 4
Dataset Generation
        ↓
PHASE 5
Sensor Fusion + Edge AI
        ↓
PHASE 6
Integrated Handheld Prototype
        ↓
PHASE 7
Offline + Secure Event Infrastructure
        ↓
PHASE 8
RPF Dashboard Integration
        ↓
PHASE 9
Environmental / Field Validation
        ↓
PHASE 10
Ruggedized Deployment Prototype

---

🔭 19. Future Expansion

Potential future development areas include:

- Expanded chemical-response libraries
- More robust drift compensation
- Automated sensor self-diagnostics
- Replaceable sensing cartridge architecture
- Multilingual operator interface
- Improved environmental compensation
- Advanced confidence calibration
- Fleet-level device management
- Permissioned integrity anchoring
- Railway-scale dashboard deployment
- Quadruped + handheld cooperative operation
- Digital twin / fleet analytics

---

🧪 20. Responsible Use & Scope

RAKSHA-NETRA is intended as a research and engineering prototype for presumptive field screening.

It is not presented as a substitute for confirmatory laboratory analysis, certified forensic identification, or legally mandated procedures.

A suspicious screening result should support appropriate follow-up, secondary screening and confirmation by authorized personnel using approved procedures.

The system should not be deployed operationally without appropriate:

- Calibration
- Controlled validation
- Environmental testing
- Safety verification
- Cybersecurity testing
- Forensic/operational validation
- Regulatory and institutional approvals

---

📁 21. Repository Structure

RAKSHA-NETRA/
│
├── README.md
│
├── docs/
│   ├── SYSTEM_ARCHITECTURE.md
│   ├── HARDWARE_ARCHITECTURE.md
│   ├── SOFTWARE_ARCHITECTURE.md
│   ├── AI_SENSOR_FUSION.md
│   ├── CYBERSECURITY.md
│   ├── VALIDATION_PLAN.md
│   └── DEPLOYMENT_MODEL.md
│
├── prototypes/
│   ├── figma/
│   ├── wokwi/
│   └── easyeda/
│
├── hardware/
│   ├── schematics/
│   ├── pcb/
│   ├── bom/
│   └── enclosure/
│
├── firmware/
│   └── stm32/
│
├── edge-ai/
│   ├── preprocessing/
│   ├── models/
│   └── inference/
│
├── dashboard/
│
├── media/
│
└── references/

---

📚 22. References

The project documentation should maintain a dedicated reference list covering:

- Electrochemical sensing for illicit-substance detection
- Portable electronic-nose / VOC sensing
- Sensor drift and cross-sensitivity
- Edge AI / TinyML deployment
- Thermal desorption and trace sampling
- Forensic digital evidence integrity
- NIST guidance relevant to trace detection and digital evidence
- Relevant railway-security and screening technologies
- Datasheets and application notes for selected components

Component-level documentation should cite the original manufacturer datasheets and application notes.

---

👥 23. Project

RAKSHA-NETRA

Smart India Hackathon 2026
Problem Statement: 26026
Domain: Hardware / Railway Security

Project Objective

«Build an intelligent, portable and resilient screening architecture that brings rapid presumptive trace intelligence closer to the railway field while preserving secure, traceable event records.»

---

⚠️ Prototype Disclaimer

«RAKSHA-NETRA is a research and hackathon prototype / proof-of-concept architecture. The current implementation is not a certified final railway security or forensic device. Performance figures, detection limits, classification accuracy and deployment readiness must be established through controlled experimental validation before operational use.»

---

🔗 Project Links

GitHub:
"https://github.com/thiyagusanthosh2007-boop/RAKSHA-NETRA"

Figma Prototype:
"<PASTE LINK>"

Wokwi Prototype:
"<PASTE LINK>"

EasyEDA Design:
"<PASTE LINK>"

Demo Video:
"<PASTE LINK>"

Presentation:
"<PASTE LINK>"
