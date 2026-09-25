# MineGuard-AI
⛏️ AI-powered underground mine safety system for SIH26039. Monitors worker health, predicts gas leaks &amp; roof collapses, deploys autonomous rescue rover. Built with ESP32, LoRa, React, TensorFlow.

## 🎯 What Problem Are We Solving?

Every year, **hundreds of miners die** in underground accidents due to:

- ❌ **Gas leaks** (methane, carbon monoxide) detected too late
- ❌ **Roof collapses** without warning
- ❌ **No real-time health monitoring** of workers underground
- ❌ **Rescue teams entering blindly** into hazardous areas
- ❌ **Poor communication** underground (GPS/WiFi don't work)
- ❌ **Delayed emergency response** costing critical minutes

**Current safety systems are reactive** — they alert AFTER danger has already occurred. We need a **proactive system** that predicts hazards before they happen and enables faster, safer rescue operations.

---

## 💡 Our Solution: MineGuard AI

MineGuard AI is a **complete 5-layer safety ecosystem** for underground mines:

### **Layer 1: Worker Wearable Safety Bands** ⌚
Every miner wears a smart wristband that monitors:
- **Health:** SpO2 (blood oxygen), heart rate, body temperature
- **Safety:** Fall detection, panic button for emergencies
- **Location:** Real-time tracking underground (UWB/BLE, since GPS doesn't work)
- **Alerts:** Vibration warns worker of detected hazards

**Cost:** ₹1,200 per unit | **Battery:** 12-24 hours

---

### **Layer 2: Environmental Sensor Nodes** 📡
IoT devices mounted on tunnel walls every 50-100 meters:
- **Gas Detection:** Methane (CH4), Carbon Monoxide (CO), Oxygen levels
- **Environment:** Temperature, humidity, air velocity, dust
- **Structural Health:** Vibration sensors detect roof instability
- **Communication:** LoRa mesh network (works 1-2 km underground)
- **Local Alerts:** LED indicators (green/yellow/red) + buzzer

**Cost:** ₹4,000 per node | **Battery:** 6-12 months

---

### **Layer 3: Edge Gateway & Communication Hub** 🖥️
Raspberry Pi-based stations deployed underground:
- **Data Aggregation:** Collects from 50-100 sensors via LoRa
- **Local AI:** Runs anomaly detection offline (no internet needed)
- **Multi-Path Communication:** Wi-Fi + Ethernet + 4G backup to surface
- **Data Logging:** Stores all readings for compliance and analysis

**Cost:** ₹15,000 per gateway | **Coverage:** 300-500m radius

---

### **Layer 4: Autonomous Rescue Rover** 🤖
Remote-controlled tank robot for emergency response:
- **Live Video:** ESP32-CAM streams to control room (2-5 fps via LoRa)
- **Gas Sensing:** Onboard sensors measure conditions before humans enter
- **Obstacle Avoidance:** 4x ultrasonic sensors for autonomous navigation
- **Supply Delivery:** Carries oxygen masks, first aid, radio to trapped workers
- **Two-Way Audio:** Microphone + speaker for communication with trapped miners
- **Night Vision:** IR LEDs + camera for complete darkness
- **Mobility:** 6-wheel tank treads climb 45° slopes, rough terrain

**Cost:** ₹10,000 per rover | **Battery:** 1-2 hours operation

---

### **Layer 5: Control Room Dashboard** 📊
Centralized monitoring platform:
- **3D Digital Twin:** Interactive mine map with live sensor data overlay
- **Worker Tracking:** Real-time location and health for every miner
- **AI Predictions:**
  - Gas accumulation forecasting (30-60 minutes in advance)
  - Roof collapse risk using Physics-Informed Neural Networks
  - Anomaly detection across all sensors
  - Worker health risk scoring
- **Alert Management:** Automated severity classification and escalation
- **Rescue Operations:** Incident command, rover deployment, resource allocation

**Tech Stack:** React.js, Node.js, MongoDB, InfluxDB, TensorFlow

---

## 🔄 How It Works (Real Scenario)

### **Normal Operations:**
1. Miners wear safety bands, enter mine
2. 48 sensor nodes continuously monitor environment
3. Data flows: Sensors → LoRa mesh → Gateways → Dashboard
4. AI analyzes patterns, predicts hazards in real-time
5. Control room monitors all workers and conditions
6. **Green status** → Mining continues safely

### **Emergency Scenario:**

**8:15 AM - Hazard Detection**
Sensor S23 (Section B, 450m depth):

CH4: 1.2% → 1.5% → 1.8% (rising rapidly)

Vibration: Abnormal pattern detected

AI Prediction:

"Gas will reach 2.5% in 20 minutes"

"Roof collapse risk: 78%"

text

**8:16 AM - Automatic Alerts**
- Local buzzers + red LEDs activate in Section B
- Wearable bands vibrate on all workers' wrists
- Dashboard shows: "⚠️ CRITICAL - Section B - CH4 rising"
- SMS sent to supervisor: "Evacuate Section B immediately"

**8:17 AM - Worker Evacuation**
- Workers feel vibration, see red LEDs
- Follow exit route (shown on dashboard)
- All 12 workers accounted for on tracking system

**8:20 AM - Situation Worsens**
CH4 = 2.3% (dangerous level)

Roof collapse detected!

Worker #7: SpO2 drops to 87% (trapped, respiratory distress)

Location: 500m depth, behind debris

text

**8:21 AM - Rescue Deployment**
- Control room deploys Rescue Rover
- Command: "Navigate to Worker #7 location"

**8:25 AM - Rover Assessment**
- Live video shows debris pile, unstable roof
- Gas sensors: CH4 = 2.4% (toxic for humans)
- Two-way audio: "Can you hear me?" → "Yes! 3 workers trapped!"

**8:27 AM - Supply Delivery**
- Rover delivers oxygen masks, first aid, radio
- Workers put on masks immediately

**8:30 AM - Rescue Planning**
- Control room uses rover data to plan safe path
- Decision: "Clear debris from left side, send team with oxygen"

**9:15 AM - Successful Rescue**
- Rescue team follows rover's mapped path
- Extracts all 3 trapped workers safely
- **Result: Zero fatalities**

---

## 🚀 Key Innovations

### **1. Physics-Informed AI (PINNs)**
Unlike generic ML models, our AI incorporates:
- Ventilation physics (airflow dynamics)
- Methane transport equations
- Geomechanical principles (rock stress/strain)

**Result:** Better predictions with limited data (85-90% accuracy)

---

### **2. Hybrid Underground Communication**
- **LoRa mesh:** 1-2 km range, low-power, works underground
- **UWB positioning:** Accurate tracking without GPS
- **Multi-path backup:** Wi-Fi + Ethernet + 4G (always connected)

**Result:** Never loses connectivity in deep tunnels

---

### **3. Integrated Health + Environment Monitoring**
Correlates worker vitals with environmental data:
Worker #5: SpO2 drops to 89%
Nearby sensor: CH4 = 2.1%

System infers: "Low SpO2 caused by methane exposure"
→ Immediate medical alert + evacuation

text

---

### **4. Autonomous Rescue Rover**
- Enters hazardous areas BEFORE humans
- Live video + gas sensing for informed decisions
- Delivers oxygen/first aid to buy time
- Two-way audio provides psychological support

**Result:** Rescuers don't enter blindly, workers stay alive longer

---

### **5. 10x Cost Reduction**
| Component | Commercial Systems | MineGuard AI |
|-----------|-------------------|--------------|
| Per installation | ₹5-10 lakhs | ₹50,000-1 lakh |
| Wearable per worker | ₹10,000+ | ₹1,200 |
| Sensor node | ₹25,000+ | ₹4,000 |
| Rescue rover | ₹2-5 lakhs | ₹10,000 |

**Result:** Accessible for small/medium mines, not just large corporations

---

## 📊 Expected Impact

| Metric | Improvement |
|--------|-------------|
| Mine accidents | **50% reduction** through early hazard detection |
| Emergency response | **30% faster** with real-time alerts + rover |
| Worker tracking | **100% coverage** (no miner left unmonitored) |
| System cost | **10x cheaper** than commercial alternatives |
| Rescue team risk | **Significantly reduced** (rover assesses first) |

---

## 🛠️ Technology Stack

**Hardware:**
- ESP32-S3, ESP32, ESP32-CAM, Raspberry Pi 4
- MAX30102 (SpO2), MQ-4/MQ-7 (gas), BME280 (temp/humidity)
- RFM95W LoRa (868 MHz), UWB modules
- L298N motor driver, BO motors, 6-wheel tank chassis

**Software:**
- React.js, Node.js, MongoDB, InfluxDB
- TensorFlow (LSTM, autoencoders), PyTorch (PINNs)
- KiCad (electronics), Fusion 360 (CAD), ANSYS (FEA)

**Communication:**
- LoRa mesh (1-2 km underground)
- Wi-Fi/Ethernet/4G (surface backup)
- MQTT, WebSocket, REST APIs

---

## 📁 Repository Contents

This repository contains complete documentation and source files for MineGuard AI:

### **Hardware**
- `hardware/cad/` - 3D models (rover chassis, sensor enclosures, wearable cases)
- `hardware/electronics/` - KiCad schematics and PCB layouts
- `hardware/fea/` - ANSYS FEA analysis reports

### **Software**
- `software/firmware/` - ESP32 Arduino code (wearables, sensors, rover)
- `software/backend/` - Node.js API server
- `software/frontend/` - React.js dashboard

### **AI Models**
- `ai_models/` - LSTM gas prediction, PINNs roof stability, anomaly detection

### **Documentation**
- `documentation/` - BOM, circuit diagrams, FEA reports, presentations

### **Authenticity Evidence**
- `authenticity_photos/` - Lab work photos with team IDs
- `work_in_progress/` - CAD trees, EDA screenshots, FEA convergence plots

---

## 👥 Team

**Team Name:** [Your Team Name]  
**College:** [Your College Name]  
**Faculty Mentor:** Prof. [Mentor Name]

**Team Members:**
- [Member 1] - Hardware Lead
- [Member 2] - Software Lead
- [Member 3] - AI/ML Lead
- [Member 4] - Electronics Lead
- [Member 5] - Design Lead

---

## 📞 Contact

**Email:** [team-email@college.edu]

---

## 🙏 Acknowledgments

- **[Your College Name]** - For lab facilities and support
- **Prof. [Mentor Name]** - For guidance and mentorship
- **Department of [Department]** - For technical resources

---

**Last Updated:** September 25, 2026  
**Version:** v1.0

---

<p align="center">
  <strong>Made with ❤️ for safer underground mining in India</strong>
</p>
