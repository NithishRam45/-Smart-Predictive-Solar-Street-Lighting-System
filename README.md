# -Smart-Predictive-Solar-Street-Lighting-System
An ESP32-based solar street lighting prototype with adaptive brightness and a predictive multi-pole lighting concept.
📌 About the Project
A smart solar-powered street lighting system using ESP32 that automatically controls LED brightness based on ambient light and motion detection.

During low-traffic conditions, the lights operate at reduced brightness to save energy. When a vehicle or person is detected, the nearby lights increase their brightness. Multiple lighting poles can communicate with each other to create a dynamic wave of illumination that follows the movement along the road.

Features
ESP32-based control
Solar-powered operation
Automatic brightness adjustment
Motion-based lighting
Energy-efficient design
Multi-pole wireless coordination
🎯 Problem Statement
Traditional street lights often operate at full brightness even when there is little or no movement on the road, leading to avoidable energy usage.

This project focuses on:

💡 Reducing unnecessary power consumption
🚶 Increasing brightness when motion is detected
☀️ Utilizing solar enerThe system uses:

PIR Sensor → Detects movement
LDR Sensor → Measures surrounding light
ESP32 → Processes sensor inputs and controls the light
LED → Acts as the street light
MOSFET → Adjusts LED brightness
Basic Operation
🌙 Low Light
     ↓
Low Brightness
     ↓
Motion Detected
     ↓
High Brightness
     ↓
No Motion
     ↓
Delay / Timeout
     ↓
Low Brightness

For multiple poles, the detected movement can be communicated to the next lighting unit, producing a sequential wave of illumination along the road.gy for sustainable lighting
✨ Key Features
☀️ Solar-powered street lighting
🔋 Rechargeable battery support
💡 Automatic LED intensity control
🚶 Motion detection using PIR
🌙 Ambient light sensing using LDR
🎛️ ESP32-based automation
🛣️ Coordinated multi-pole lighting
⚡ Reduced energy consumption
🔌 Smart embedded control
🌐 Enabling coordinated lighting across multiple poles
⚡ Creating an energy-efficient smart street lighting system
💡 How It Works
