# AR-IoT: Augmented Reality Meets the Internet of Things

Welcome to **AR-IoT**, an innovative project that bridges the world of Augmented Reality (AR) and the Internet of Things (IoT) using **Unity**, **Vuforia**, and the **ESP32** microcontroller. This project aims to provide a seamless and interactive experience for controlling and visualizing sensor data in real-time, utilizing the power of virtual buttons and cloud-based connectivity.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Setup Instructions](#setup-instructions)
- [Project Structure](#project-structure)
- [Future Work](#future-work)
- [Demo](#demo)

## Overview
**AR-IoT** demonstrates the integration of AR and IoT in a single cohesive system. With **Vuforia** and **Unity**, the project overlays virtual buttons onto a target plane, allowing users to interact with sensor data or control actuators visually. The **ESP32**, in conjunction with **Blynk 2.0**, provides a robust framework for real-time data acquisition and device control over the cloud.

### How It Works
- **Virtual Buttons**: Using Vuforia, the Unity-based AR app displays buttons that can toggle actuators or fetch sensor readings when pressed.
- **Sensor Data**: The ESP32 board, programmed using Arduino, collects temperature and humidity data using a DHT11 sensor and updates these readings to the Blynk cloud.
- **Cloud Connectivity**: The project leverages the Blynk 2.0 API for seamless communication between the AR app and the ESP32, making data visualization and control a breeze.

## Features
- **Interactive AR Interface**: Engage with virtual buttons mapped to physical actions or sensor data readings.
- **Real-Time Data**: View up-to-date sensor readings in Unity using Blynk API integration.
- **Seamless IoT Control**: Control actuators on the ESP32 from the AR app using cloud-based API requests.
- **User-Friendly Design**: Simple and intuitive interface for non-technical users to interact with IoT devices.

## Technology Stack
- **Hardware**: ESP32, DHT11 sensor
- **Software**:
  - **Unity**: For building the AR interface
  - **Vuforia**: For target tracking and virtual button integration
  - **Blynk 2.0**: For cloud connectivity and data management
  - **Arduino**: For programming the ESP32
  - **C#**: For scripting in Unity

## Setup Instructions
### Prerequisites
- Install **Unity** with Vuforia support.
- Install the **Arduino IDE** and set up your ESP32 board.
- Create a Blynk account and set up a template for your ESP32 device.

### Step 1: Arduino Sketch Setup
1. Open the `blynk2_Esp32_test.ino` file in the Arduino IDE.
2. Update the `BLYNK_TEMPLATE_ID`, `BLYNK_DEVICE_NAME`, and `BLYNK_AUTH_TOKEN` with your Blynk project details.
3. Configure your WiFi credentials:
   ```cpp
   char ssid[] = "your-SSID";
   char pass[] = "your-PASSWORD";
   ```
4. Upload the sketch to your ESP32.

### Step 2: Unity and Vuforia Setup
1. Open the **Sensor App** or **Virtual Buttons App** in Unity.
2. Ensure Vuforia is set up with the appropriate license key and target database.
3. Assign the `click.cs` or `First.cs` script to the relevant GameObjects.
4. Modify the Blynk API URLs in the scripts as necessary to match your setup.

### Step 3: Running the System
- Launch the Unity app on your AR-capable device.
- Point the device at the target plane to view and interact with virtual buttons.
- Use the Blynk web dashboard or mobile app to monitor and control the ESP32.

## Project Structure
```
AR-IoT/
│
├── Arduino Sketch/
│   ├── blynk2_Esp32_test.ino       # Main ESP32 code for Blynk integration
│   ├── debug.cfg                   # Debug configuration
│   ├── debug_custom.json           # Custom debug settings
│   └── esp32.svd                   # ESP32 peripheral description
│
├── Sensor App/
│   ├── Assets/                     # Unity assets for the sensor app
│   ├── Packages/
│   ├── ProjectSettings/
│   └── QCAR/                       # Vuforia target assets
│
├── Virtual Buttons App/
│   ├── Assets/                     # Unity assets for the virtual buttons app
│   ├── Packages/
│   ├── ProjectSettings/
│   └── QCAR/                       # Vuforia target assets
│
├── .gitattributes                  # Git configuration
├── demo_video.mp4                  # Demonstration video of the project
└── .gitignore                      # Git ignore file
```

## Future Work
- **Enhanced AR Visualizations**: Improve the user interface with more intuitive 3D models and animations.
- **Additional Sensors**: Integrate more sensors to expand the IoT capabilities.
- **Mobile App Integration**: Develop a companion app for more convenient control and monitoring.

## Demo
Check out the project in action:

![AR-IoT Demo](demo_video.mp4)

---
