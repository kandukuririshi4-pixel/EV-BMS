# 🔋 ESP32 Modular Battery Management System (BMS)

An ESP32-based Modular Battery Management System designed to demonstrate real-time battery cell monitoring, intelligent fault management, safety-state transitions, and IoT-based battery analytics.

The project combines embedded systems, IoT telemetry, fault detection, and a live Blynk dashboard to provide battery status monitoring and operator decision support.

## 🚀 Key Features

- **Cell Voltage Monitoring:** Monitor four simulated battery cells and identify the weakest and strongest cells.
- **Fault Detection:** Detect simulated ADC faults, frozen sensor readings, relay mismatches, and cell imbalance.
- **Four-State Safety Machine:** Implements `NORMAL`, `DEGRADED`, `FAILSAFE`, and `SHUTDOWN` states.
- **Structured Event Logging:** Record fault events and state transitions with timestamps, fault IDs, and fault sources.
- **Verified Recovery:** Require recovery checks before returning from a fault condition.
- **Flicker-Free LCD:** Use differential character rendering and rotating display pages.
- **Event-Driven Telemetry:** Transmit significant data changes and system events to Blynk IoT.
- **Offline Event Queue:** Buffer telemetry events in a fixed-size FIFO queue when connectivity is unavailable.
- **Wi-Fi Reconnection:** Attempt reconnection without blocking the main application loop with long connection waits.
- **Live IoT Dashboard:** Display cell voltages, relay status, system state, Wi-Fi RSSI, fault information, and queue depth.
- **Battery Risk Analytics:** Calculate a demonstration risk score using cell imbalance, fault frequency, and estimated state of charge.
- **Maintenance Recommendations:** Generate human-readable recommendations based on simulated battery health and fault conditions.
- **Historical Analytics:** Publish periodic samples for Blynk time-series charts.
- **Fault Injection:** Simulate faults and network outages to demonstrate monitoring and recovery behavior.

## 🛠️ Technologies Used

- **Hardware platform:** ESP32
- **Programming language:** C++ / Arduino
- **Simulation:** Wokwi
- **IoT platform:** Blynk IoT
- **Display:** 16×2 I2C LCD
- **Inputs:** Potentiometers and push buttons
- **Communication:** Wi-Fi
- **Analytics:** Risk scoring, voltage imbalance analysis, and event history

## 🏗️ System Architecture

1. **Sensing Layer:** Read simulated cell voltages using ESP32 ADC inputs.
2. **BMS Processing Layer:** Calculate cell statistics, voltage imbalance, and estimated battery health.
3. **Safety Layer:** Classify operating conditions and manage fault states and recovery.
4. **Display Layer:** Present battery information and critical fault status on the LCD.
5. **Telemetry Layer:** Detect meaningful changes and buffer events during network outages.
6. **Analytics Layer:** Calculate risk indicators and maintenance recommendations.
7. **Dashboard Layer:** Display live telemetry and historical trends through Blynk IoT.

## 📊 Dashboard Metrics

- Individual cell voltages
- Weakest and strongest cell voltages
- Cell imbalance
- Estimated state of charge (SoC)
- Battery health and risk score
- Relay status and current safety state
- Fault count and system uptime
- Wi-Fi connection status and signal strength
- Offline queue depth
- Maintenance recommendations

## 🧪 Testing Scenarios

- Normal simulated battery operation
- Cell voltage imbalance
- Frozen ADC readings
- ADC out-of-range conditions
- Relay feedback mismatch
- Simulated communication failure
- Wi-Fi disconnection and reconnection
- Offline telemetry queue replay
- Fault acknowledgement and recovery verification
- Latched shutdown behavior

## ▶️ Getting Started

1. Open the project in Wokwi.
2. Install the Blynk and LiquidCrystal I2C libraries.
3. Configure the Blynk template and device authentication credentials.
4. Connect the simulated ESP32, LCD, potentiometers, and buttons according to the project pin configuration.
5. Start the simulation and open the Serial Monitor.
6. Configure the Blynk dashboard datastreams to display telemetry and analytics.
7. Test normal operation, fault injection, and network reconnection.

## ⚠️ Limitations

This project is a simulation-oriented prototype. Cell voltages are simulated using potentiometers, and the SoC and battery risk calculations are demonstration estimates rather than validated battery models. The offline queue is stored in RAM and does not survive a restart.

This prototype is not certified for real battery protection or safety-critical applications.

## 🎯 Project Objective

To demonstrate how embedded systems, IoT connectivity, event-driven communication, structured fault management, and battery analytics can be integrated into a modular battery monitoring prototype.

## 👨‍💻 Author

**Sai Prasad Karnam**

Electronics and Communication Engineering (ECE)

Teegala Krishna Reddy Engineering College, Hyderabad

## 📄 License

Choose an appropriate open-source license before distributing or reusing this project.

