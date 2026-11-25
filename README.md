# 🍄 SmartFungi – AI-Powered Smart Mushroom Cultivation Monitoring and Environmental Control System

## 📌 Project Overview

**SmartFungi** is an AI-powered, IoT-based oyster mushroom cultivation system designed as a **standalone smart cultivation box**. It integrates environmental monitoring, two AI-based detection models, and automatic environmental control to improve mushroom cultivation management.

The system continuously monitors temperature, humidity, CO₂, and light intensity using environmental sensors. A camera captures mushroom images, which are processed using two separately trained AI models:

1. **Growth Stage Detection Model (YOLOv8n):** Identifies three mushroom growth stages – Juvenile, Intermediate, and Harvest.
2. **Mushroom Health Detection Model:** Identifies whether the mushroom is Healthy or Infected.

The detected growth stage is used to select suitable environmental target values. An ESP32 controls devices such as fans, humidifiers, and lighting systems to help maintain the required conditions.

A web dashboard provides remote monitoring of environmental readings and AI detection results, while email alerts notify users when environmental conditions exceed configured limits.

Unlike room-based monitoring systems, SmartFungi is designed as an independent cultivation box with integrated sensing, image processing, monitoring, and environmental control.

## 🎯 Project Objectives

- Develop a standalone smart oyster mushroom cultivation box.
- Monitor temperature, humidity, CO₂, and light intensity.
- Identify mushroom growth stages using a trained YOLOv8n model.
- Detect Healthy and Infected mushroom conditions using a separate trained model.
- Select environmental target values according to the detected growth stage.
- Automate environmental control using ESP32.
- Provide remote monitoring through a web dashboard.
- Send email alerts when environmental conditions exceed configured limits.
- Reduce manual monitoring and support better cultivation management.

## ⚙️ Key Features

- **Standalone Cultivation Box:** An integrated enclosure for mushroom monitoring and environmental management.
- **Environmental Monitoring:** Measures temperature, humidity, CO₂, and light intensity.
- **AI-Based Growth Stage Detection:** Identifies Juvenile, Intermediate, and Harvest stages using YOLOv8n.
- **AI-Based Health Detection:** Uses a separately trained model to identify Healthy and Infected conditions.
- **Automatic Environmental Control:** Controls fans, humidifiers, and lighting based on sensor readings and selected targets.
- **Web Dashboard:** Displays environmental readings and AI detection results.
- **Email Notifications:** Sends alerts when environmental readings go beyond specified limits.
- **Stage-Based Management:** Selects environmental target values according to the detected growth stage.

## 🧠 AI Models

SmartFungi uses two separately trained AI models for mushroom analysis.

### 1. Growth Stage Detection – YOLOv8n

This model is trained to identify three oyster mushroom growth stages.

| Class | Description |
|---|---|
| Juvenile | Early mushroom development stage |
| Intermediate | Developing mushroom stage |
| Harvest | Mushroom ready for harvesting |

**Purpose:** The detected growth stage is used to select the corresponding environmental target settings for automatic control.

### 2. Mushroom Health Detection Model

A second, separately trained model is used for mushroom health detection.

| Class | Description |
|---|---|
| Healthy | Mushroom identified as healthy |
| Infected | Mushroom identified as infected |

**Purpose:** Provides a basic health-status result to help identify potentially unhealthy mushrooms.

The health detection model does not classify individual disease types.

## 🏗️ System Architecture

```text
       STANDALONE CULTIVATION BOX
    +--------------------------------+
    |                                |
    |  Environmental Sensors         |
    |  Temperature | Humidity        |
    |  CO2 | Light                   |
    |          |                     |
    |          v                     |
    |         ESP32                  |
    |          |                     |
    |  +-------+--------+            |
    |  |                |            |
    |  v                v            |
    | Local Display   Web Dashboard  |
    |                   |            |
    |               Email Alerts     |
    |                                |
    |  Camera Module                 |
    |       |                        |
    |       v                        |
    |  Raspberry Pi / Python Backend |
    |       |                        |
    |  +----+----------------+       |
    |  |                     |       |
    |  v                     v       |
    | Growth Stage       Health      |
    | Model (YOLOv8n)    Model       |
    |  |                     |       |
    |  v                     v       |
    | Juvenile /          Healthy /  |
    | Intermediate /      Infected   |
    | Harvest                         |
    |       |                        |
    |       v                        |
    | Environmental Target Selection |
    |       |                        |
    |       v                        |
    |       ESP32                    |
    |        |                       |
    |   +----+------+                |
    |   |           |                |
    |   v           v                |
    |  Fan      Humidifier           |
    |               |                |
    |            Lighting            |
    +--------------------------------+
```

## 🔄 Working Principle

1. Environmental sensors measure temperature, humidity, CO₂, and light intensity inside the standalone cultivation box.
2. The ESP32 collects sensor readings and sends them to the monitoring interface.
3. The camera captures mushroom images inside the box.
4. The first trained AI model, YOLOv8n, identifies the mushroom growth stage.
5. The second trained AI model identifies the mushroom health condition as Healthy or Infected.
6. The detected growth stage is used to select the corresponding environmental target values.
7. The ESP32 controls the connected fan, humidifier, and lighting system based on sensor readings and selected targets.
8. The web dashboard displays environmental readings and AI detection results.
9. Email alerts notify users when environmental conditions exceed configured limits.

## 🔧 Hardware Components

- ESP32 Microcontroller
- Raspberry Pi (AI processing and backend)
- Temperature and Humidity Sensor
- CO₂ Sensor
- Light Sensor
- Camera Module
- Local Display Unit
- Cooling System
- Exhaust Fan
- Ultrasonic Humidifier
- Lighting System
- Standalone Cultivation Box

## 💻 Software and Technologies

| Technology | Purpose |
|---|---|
| Python | Backend development and image processing |
| YOLOv8n | Growth-stage detection model |
| Second trained AI model | Mushroom health detection |
| OpenCV | Image processing and colour analysis |
| ESP32 / Arduino IDE | Sensor monitoring and actuator control |
| Firebase | Data exchange and target-value communication |
| FastAPI | Python backend and API development |
| HTML, CSS, JavaScript | Web dashboard development |

## 🌱 Expected Impact

- Reduces the need for continuous manual monitoring.
- Supports stage-based mushroom cultivation management.
- Helps identify potentially unhealthy mushrooms.
- Enables remote environmental monitoring.
- Supports automatic adjustment of cultivation conditions.
- May improve resource utilization through controlled actuator operation.
- Provides an integrated smart cultivation solution for small-scale farmers and commercial growers.

## 🚀 Future Scope

- Complete edge deployment and real-time integration of both AI models.
- Improve growth-stage and health-detection accuracy.
- Validate environmental targets for each growth stage.
- Conduct complete oyster mushroom cultivation trials.
- Evaluate an automated treatment mechanism after safety and crop-compatibility testing.
- Extend the system to support additional mushroom varieties.

## 📊 Project Status

The project has progressed through environmental sensor interfacing, sensor monitoring, local display development, web dashboard development, email alerts, and training of both AI models.

Further work focuses on complete camera integration, deployment of both models on the intended edge hardware, communication between the AI backend and ESP32, and automatic stage-based environmental control.

## 👨‍💻 Project Information

- **Project Name:** SmartFungi
- **Domain:** Smart Agriculture | IoT | Artificial Intelligence | Edge Computing
- **Cultivation Type:** Standalone Mushroom Cultivation Box
- **Crop:** Oyster Mushroom
- **AI Model 1:** YOLOv8n – Growth Stage Detection
- **AI Model 2:** Trained Mushroom Health Detection Model
- **Growth Classes:** Juvenile, Intermediate, Harvest
- **Health Classes:** Healthy, Infected

## 📌 Conclusion

SmartFungi aims to make oyster mushroom cultivation smarter by integrating two AI models, IoT-based environmental monitoring, remote monitoring, and automatic environmental control in a single standalone cultivation box.

Its key innovation is connecting AI-based growth-stage detection with stage-based environmental management while also providing a separate mushroom health assessment.

**SmartFungi – Smart Monitoring, Intelligent Detection, Better Cultivation.**
