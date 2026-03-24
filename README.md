# 🌾 IoT-Based Farm Motor Control & Monitoring System

## 📌 Overview

This project is an advanced IoT-based farm automation system using ESP32 and MQTT protocol to remotely control motors and monitor electrical parameters in real time. It supports dual motor control with secure cloud communication and feedback mechanisms.

## 🚀 Features

* Remote motor ON/OFF control using MQTT
* Dual motor control system (Motor 1 & Motor 2)
* Relay-based pulse control (automatic OFF after fixed time)
* Real-time voltage monitoring (R, Y, B phases)
* Current monitoring via Arduino Nano (UART communication)
* Cloud-based status feedback and logging
* Retained message protection (ignores old commands after boot)
* Heartbeat system for device online status

## ⚙️ Hardware Used

* ESP32
* Relay Module (4-channel)
* Arduino Nano (for current sensing)
* Voltage Sensors (R, Y, B phases)
* WiFi Network
* LED Indicator

## 💻 Software & Technologies

* Embedded C (Arduino IDE)
* MQTT Protocol (HiveMQ Broker)
* WiFi Communication
* UART Communication (ESP32 ↔ Arduino Nano)

## 🔌 Working Principle

1. ESP32 connects to WiFi and MQTT broker
2. Receives motor control commands via MQTT topics:

   * `farm/m1/cmd` → Motor 1
   * `farm/m2/cmd` → Motor 2
3. Activates relays using pulse logic (auto OFF after 5 seconds)
4. Sends feedback to:

   * `farm/m1/state`
   * `farm/m2/state`
5. Reads voltage from R, Y, B phases and publishes:

   * `farm/voltage/ryb`
6. Receives current data from Arduino Nano via UART and publishes:

   * `farm/current/all`
7. Sends heartbeat status:

   * `farm/mcu/status`

## 📡 MQTT Topics Used

* Control:

  * farm/m1/cmd
  * farm/m2/cmd
* Feedback:

  * farm/m1/state
  * farm/m2/state
* Monitoring:

  * farm/voltage/ryb
  * farm/current/all
* Status:

  * farm/mcu/status

## 🌐 Applications

* Smart agriculture automation
* Industrial motor control systems
* Remote pump management
* Energy monitoring systems

## 🔮 Future Improvements

* Mobile app dashboard
* AI-based fault detection
* Over-voltage and overload protection
* Integration with AWS IoT

## 👨‍💻 Author

Sowgandh S
Embedded Systems & AI–IoT Developer
GitHub: https://github.com/kingstonsow45
