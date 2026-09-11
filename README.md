# -Smart-Predictive-Solar-Street-Lighting-System
An ESP32-based solar street lighting prototype with adaptive brightness and a predictive multi-pole lighting concept.
# 🌞 Smart Predictive Solar Street Lighting System

> An ESP32-based solar street lighting prototype with adaptive brightness and a predictive multi-pole lighting concept.

---

## 📌 About the Project

Traditional street lights often remain at high brightness even when there is little or no traffic. This can result in unnecessary energy consumption.

The **Smart Predictive Solar Street Lighting System** is designed to provide an energy-efficient and sustainable alternative using **solar power, motion detection, ambient-light sensing, and intelligent control**.

The system uses an **ESP32 microcontroller** to control street-light brightness according to the surrounding lighting conditions and detected movement.

The main concept is to create a **moving wave of illumination** along a road, where the upcoming lighting zone can be activated as movement progresses.

---

## 🎯 Problem Statement

Conventional street lights may consume energy continuously even when roads are empty.

This project aims to:

* 💡 Reduce unnecessary lighting power consumption
* 🚶 Provide brighter illumination when movement is detected
* ☀️ Utilize solar energy for sustainable operation
* 🔋 Store and efficiently utilize solar energy
* 🛣️ Develop a predictive lighting concept for multiple street-light poles
* ⚡ Improve overall energy efficiency

---

## 💡 How It Works

The prototype consists of the following major components:

| Component      | Function                              |
| -------------- | ------------------------------------- |
| **PIR Sensor** | Detects human/vehicle movement        |
| **LDR Sensor** | Detects ambient light intensity       |
| **ESP32**      | Main controller of the system         |
| **LED**        | Represents the street light           |
| **MOSFET**     | Controls LED switching and brightness |

### Basic Operation

```text
             🌙 Night / Low Ambient Light
                         ↓
                  💡 Low Brightness
                         ↓
                  🚶 Motion Detected
                         ↓
                  💡 High Brightness
                         ↓
                   Motion Ends
                         ↓
                      Timeout
                         ↓
                  💡 Low Brightness
```

During nighttime, the lights operate at a lower brightness level to conserve energy.

When motion is detected, the corresponding light increases to a higher brightness level.

After the motion ends and the predefined timeout expires, the light returns to its lower brightness state.

The multi-pole concept further extends this operation by allowing the next lighting zone to be activated based on the direction of movement.

---

## ✨ Key Features

* ☀️ Solar-powered lighting concept
* 🔋 Battery-based energy storage
* 💡 Adaptive LED brightness control
* 🚶 PIR-based motion detection
* 🌙 LDR-based ambient-light detection
* 🧠 ESP32-based intelligent control
* 🛣️ Multi-pole predictive lighting concept
* ⚡ Energy-efficient operation
* 🔌 Embedded control system
* 🌱 Sustainable lighting approach

---

## 🔧 Hardware Components

| Component                   | Purpose                 |
| --------------------------- | ----------------------- |
| **ESP32-WROOM-32**          | Main controller         |
| **HC-SR501 PIR Sensor**     | Motion detection        |
| **LDR + LM393 Module**      | Ambient light detection |
| **LED**                     | Street-light simulation |
| **IRLZ44N MOSFET**          | LED switching/control   |
| **MT3608 Boost Converter**  | Voltage boosting        |
| **18650 Li-ion Battery**    | Energy storage          |
| **Solar Panel**             | Solar energy generation |
| **Solar Charge Controller** | Battery charging        |
| **220Ω Resistor**           | LED current limiting    |

---

## 📍 Prototype Pin Configuration

| Component                | ESP32 Pin |
| ------------------------ | --------- |
| **PIR Sensor**           | GPIO 27   |
| **LDR Sensor**           | GPIO 34   |
| **LED / MOSFET Control** | GPIO 25   |

> ⚠️ Pin assignments may change in future hardware versions.

---

## ⚙️ Prototype Working

The prototype was developed using a **three-pole lighting setup controlled by a centralized ESP32**.

The demonstrated brightness behavior is:

```text
              No Motion
                  ↓
            ~35% Brightness
                  ↓
          Motion Detected
                  ↓
            100% Brightness
                  ↓
            Motion Ends
                  ↓
               Timeout
                  ↓
            ~35% Brightness
```

### Working Principle

1. The **LDR** checks the surrounding ambient light.
2. During daylight, the street lights remain OFF.
3. During low-light/night conditions, the system enables the lighting system.
4. The lights operate at approximately **35% brightness** when there is no detected movement.
5. When the **PIR sensor detects motion**, the brightness increases to approximately **100%**.
6. After movement stops, the system waits for a predefined timeout.
7. The brightness then returns to the lower level.

The brightness levels and timeout duration can be modified in the Arduino code.

---

## 🔋 Solar Power Architecture

The solar power flow of the prototype can be represented as:

```text
              ☀️ Solar Panel
                    ↓
          🔋 Solar Charge Controller
                    ↓
             🔋 18650 Battery
                    ↓
             ⚡ Boost Converter
                    ↓
               🧠 ESP32
                    ↓
              💡 LED Lighting
```

The solar panel provides energy to the charging system, which stores energy in the battery.

The stored energy is then supplied to the electronics and lighting system through the required power-conversion stages.

---

## 🔌 System Circuit / Block Diagram

The following diagram represents the main hardware architecture and connections of the **Smart Predictive Solar Street Lighting System**.

### Circuit Diagram

Place your circuit diagram in the repository and name it:

```text
circuit_diagram.png
```

Then use:

```markdown
![Smart Predictive Solar Street Lighting System - Circuit Diagram](circuit_diagram.png)
```

---

## 🧠 Predictive Multi-Pole Concept

The major concept of this project is to coordinate multiple street-light poles according to the direction of movement.

### Three-Pole Concept

```text
       POLE 1          POLE 2          POLE 3

        💡              💡              💡
        │               │               │
       PIR             PIR             PIR
        │               │               │
        └───────►───────┴───────►───────┘
                 Movement Direction →
```

When movement is detected at one lighting zone, the next lighting zone can be prepared to provide illumination ahead of the moving person or vehicle.

### Current Prototype

The current prototype demonstrates the lighting-control concept using a **centralized ESP32**.

### Future Version

A future implementation can use:

* Individual controllers for each pole
* Wireless communication between poles
* Movement-direction detection
* Predictive activation of upcoming lights
* Coordinated brightness control

This can create a **predictive wave of illumination** along the road.

---

## 📊 Expected Benefits

The proposed system can provide the following benefits:

* ⚡ Reduced unnecessary lighting energy consumption
* 🔋 Better utilization of stored solar energy
* 💡 Improved illumination around moving objects
* 🛣️ Suitable for low-traffic roads
* ☀️ Reduced dependence on grid electricity
* 🌱 Environment-friendly lighting approach
* 📈 Scalable multi-pole architecture
* 💰 Potential reduction in operating costs

---

## 🚀 Future Improvements

Future versions of the project could include:

* 📡 Wireless communication between lighting poles
* 🔋 Improved battery management system
* ☀️ MPPT-based solar charging
* 💡 High-power LED street-light modules
* ⚡ Dedicated constant-current LED driver
* 💤 ESP32 deep-sleep power management
* 📊 Real-time energy-consumption monitoring
* 🤖 Vehicle/person classification
* 🌐 IoT-based remote monitoring
* 🧠 Advanced predictive movement detection
* 📍 Direction and speed estimation
* 📱 Mobile application for system monitoring

---

## 🛣️ Potential Applications

The system can be adapted for:

* 🏘️ Rural roads
* 🏡 Village streets
* 🌾 Agricultural roads
* 🎓 College campuses
* 🏭 Industrial areas
* 🛣️ Low-traffic roads
* 🌄 Remote locations
* ☀️ Solar-powered infrastructure
* 🏕️ Public pathways and isolated areas

---

## 📷 Project Gallery

Add your actual project photographs to the repository and use the following structure.

### 🔧 Prototype Setup

```markdown
![Prototype Setup](i1.jpeg)
```

### 💡 LDR Sensor Testing

```markdown
![LDR Sensor Testing](i2.jpeg)
```

### 📊 Serial Monitor Output

```markdown
![Serial Monitor Output](i3.jpeg)
```

### 🌙 Night-Time Operation

```markdown
![Night-Time Operation](i4.jpeg)
```

### 🌃 Three-Pole Lighting

```markdown
![Three-Pole Lighting](i5.jpeg)
```

### 🚦 Complete Prototype

```markdown
![Complete Prototype](i6.jpeg)
```

> 📌 Upload `i1.jpeg` to `i6.jpeg` to the repository before using these image references.

---

## 💻 Software & Tools

* **Arduino IDE**
* **Embedded C/C++**
* **ESP32**
* **Wokwi**
* **GitHub**

---


### File Description

| File / Folder         | Description            |
| --------------------- | ---------------------- |
| `README.md`           | Project documentation  |
| `src/`                | ESP32 source code      |
| `street_light.ino`    | Main Arduino program   |
| `circuit_diagram.png` | System circuit diagram |
| `i1.jpeg`             | Prototype setup        |
| `i2.jpeg`             | LDR testing            |
| `i3.jpeg`             | Serial monitor output  |
| `i4.jpeg`             | Night-time operation   |
| `i5.jpeg`             | Three-pole setup       |
| `i6.jpeg`             | Complete prototype     |

---

## ⭐ Project Status

### **Current Status: Prototype Completed and Tested**

The current prototype demonstrates:

* ESP32-based control
* PIR-based motion detection
* LDR-based ambient-light detection
* Adaptive LED brightness
* Solar-powered operating concept
* Three-pole lighting arrangement
* Centralized controller architecture

The prototype successfully demonstrates the transition between **low and high brightness based on detected motion**.

The **predictive multi-pole communication concept** is planned for further development using wireless communication between individual lighting poles.

---

## 🔮 Project Development Roadmap

```text
Phase 1
Basic LED Control
      ↓
Phase 2
LDR + PIR Integration
      ↓
Phase 3
Adaptive Brightness
      ↓
Phase 4
Solar Power Integration
      ↓
Phase 5
Three-Pole Prototype
      ↓
Phase 6
Predictive Lighting Concept
      ↓
Phase 7
Wireless Pole-to-Pole Communication
      ↓
Phase 8
IoT + Advanced Prediction
```

---

## 📜 License

This project is intended for **educational, academic, research, and prototype development purposes**.

You may adapt and improve the concept for educational and research applications with appropriate attribution.

---

## 🙌 Acknowledgements

This project combines concepts from:

* Embedded systems
* Solar energy systems
* Motion sensing
* Intelligent lighting control
* Energy-efficient electronics
* IoT and smart infrastructure

---

## ⭐ Support the Project

If you find this project useful or interesting, consider giving the repository a ⭐ on GitHub.

Your feedback and suggestions for improving the predictive lighting concept are welcome.
