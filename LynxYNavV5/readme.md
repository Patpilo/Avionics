# Avionics System

## Overview

This repository contains the avionics hardware schematics, and documentation for the **LynxRocket** project. The avionics module is responsible for:

- IMU-based flight monitoring  
- GNSS-based positioning  
- Barometric altitude logging  
- Pyro channel control (e.g., main/deploy parachutes)  
- Real-time telemetry transmission  
- Post-flight data logging  
---

## 🧠 Architecture

### Microcontroller
- **ESP32-C3** (RISC-V core, Wi-Fi, BLE)
- IO Expander PCA9555DBR

### Sensors
- **IMU1**: Bosch BNO055 
- **IMU2**: STM LSM6DSO32TR 
- **Barometer**: MS5611 or BMP390 

### GNSS
- **GNSS**: u-blox MAX M10S 

### Telemetry
- LoRa module RAK3172 
- UART interface  
- Compatible with custom ground station

### Power System
- 3S LiPo battery (11.1V nominal) or 4.5V to 23V XT60
- Buck converter to 3.3V  
- USB 5V LDO 3.3V
- Gauge Texas intruments INA260AIPWR

### Data Logging
- SPI Flash ESP32 4Mb

### Pyro Control
- 3x MOSFET-switched pyro channels  
- Redundant continuity checks via ADC/GPIO  

---

## 🔧 Firmware

Written in **C++** using the **Arduino framework**.

### Features
- Sensor fusion (Kalman or complementary filter)  
- Launch detection  
- Apogee detection and main deploy logic  
- USB debug + wireless telemetry  
- Configurable mission settings via JSON or `config.h`

---

