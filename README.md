# 🌿 SmartDrop: IoT Irrigation System

**SmartDrop** is an ESP32-based smart irrigation solution designed to automate plant watering through precise sensor data. The system monitors environmental conditions and soil health, sending all data to a centralized cloud for remote management via the SmartDrop mobile application.

---

## 🚀 How It Works
The system monitors two key environmental metrics:
1. **Atmospheric Data:** The **DHT11** sensor tracks ambient temperature and humidity.
2. **Soil Health:** A **Soil Moisture Sensor** measures the volumetric water content in the soil.

### 💧 Smart Watering Logic
To prevent overwatering and conserve resources, the water pump is strictly controlled by a logic threshold:
* **The Pump activates ONLY if Soil Moisture < 25%.**
* Once the moisture level rises above this threshold, the pump automatically deactivates.

---

## 📱 The SmartDrop App & Connectivity
The system utilizes **ThingSpeak** as its primary IoT database. 
* **Cloud Sync:** The ESP32 pushes sensor readings to ThingSpeak via Wi-Fi.
* **Mobile Interface:** The **SmartDrop App** fetches this data from ThingSpeak, providing users with real-time visualizations, historical graphs, and system status updates.

---

## 🛠️ Hardware Components
* **Controller:** ESP32 (Wi-Fi & Bluetooth enabled)
* **Sensors:** * DHT11 (Temperature & Humidity)
    * Soil Moisture Sensor (Analog/Digital)
* **Actuator:** 5V/12V Water Pump (via Relay Module)
* **Power:** 5V DC Supply

## ⚙️ Features
* **Automated Irrigation:** No manual intervention needed; the 25% threshold ensures plants are watered only when necessary.
* **Remote Monitoring:** Track your garden's health from anywhere using the SmartDrop app.
* **Data Logging:** ThingSpeak integration allows for long-term data analysis of soil and weather patterns.

---

## 🔧 Setup & Installation
1. **Hardware:** Connect sensors to the ESP32 GPIO pins as defined in the source code.
2. **ThingSpeak:** Create a channel and update the `API_KEY` in the ESP32 firmware.
3. **App:** Install the SmartDrop app and enter your Channel ID to begin monitoring.
