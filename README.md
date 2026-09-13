# Bluetooth_Controlled_Toy_Car_PCB
This repository showcases my first PCB design project  — a Bluetooth‑controlled toy car.   Designed entirely in EasyEDA as a 2‑layer board (45 mm × 60 mm, thickness 1.6 mm). The focus is on hardware design only: schematic creation, PCB routing, power management, motor driver integration, custom footprint creation and peripheral switching.

## 📌 Overview
This project is a **2‑layer PCB design** (45 mm × 60 mm, thickness 1.6 mm) created in EasyEDA.  
It implements a Bluetooth‑controlled toy car using **ATmega328P microcontroller** and **DRV8210 motor driver**.

---

## ⚡ Features
- Battery protection circuit with HY2120CB
- 5V regulated supply via LDO
- Dual DC motor control (forward/reverse, PWM speed)
- Bluetooth communication (smartphone app)
- Servo motor connector for steering
- Headlights, tail lights, blinkers, buzzer, vibration motor
- Peripheral MOSFET switching for external loads

- **Custom symbol and footprints created:**
  - Motor pad (SMD)
  - Peripheral connector pad (2‑pin SMD)
  - Battery through‑hole pad

---

## 📐 PCB Specs
- Layers: 2  
- Dimensions: 45 mm × 60 mm  
- Thickness: 1.6 mm  

---

## 🔎 Schematic Explanation

This schematic represents the complete hardware design of a **Bluetooth‑controlled toy car**. It is divided into several functional blocks:

### 1. Power Supply & Battery Protection
- **Battery Cells (CELL1+, CELL2‑)** provide the main power source.
- **HY2120CB protection IC** ensures safe operation by preventing over‑charge, over‑discharge, and short‑circuit conditions.
- **UMW78M05 LDO regulator** converts battery voltage to a stable 5V supply for the microcontroller and peripherals.
- Capacitors (100nF, 100µF, 10nF) are used for decoupling and noise filtering.

### 2. Microcontroller Unit (ATmega328P‑AU)
- Serves as the central controller for the car.
- Operates with a **16 MHz crystal oscillator** for stable timing.
- Interfaces include:
  - **PWM outputs** for motor speed control.
  - **GPIO pins** for headlights, tail lights, blinkers, buzzer, and vibration motor.
  - **UART TX/RX** for Bluetooth communication.
  - **Dedicated pin** for servo motor signal (steering).

### 3. Motor Driver Circuit (DRV8210PDSGR)
- Dual H‑bridge driver controls **Motor A** and **Motor B**.
- Inputs (IN1, IN2) from MCU determine motor direction.
- Outputs (OUT1, OUT2) drive the motors with PWM signals for speed control.

### 4. Bluetooth Module
- Connected via **TX/RX pins** of ATmega328P.
- Enables wireless control from a smartphone app.
- **BT_STATE pin** provides connection status feedback.

### 5. Peripheral MOSFET Switch Circuit
- MOSFETs (Q3–Q11) act as switches for headlights, tail lights, blinkers, buzzer, and vibration motor.
- Controlled by MCU pins (LH_CONTROL, RH_CONTROL, LT_CONTROL, RT_CONTROL, etc.).
- Allows efficient switching without overloading MCU pins.

### 6. Servo Connector
- Provides PWM signal to a servo motor for steering.
- Enables precise directional control of the toy car.

### 7. Auxiliary Pads & Slide Switch
- **Auxiliary pad** allows external modules or loads to be connected.
- **Slide switch pads** provide manual ON/OFF control for safety and convenience.

### 8. Custom Footprints
- **Motor pad (SMD)** designed for direct motor connection.
- **Peripheral connector pad (2‑pin SMD)** for external devices.
- **Battery pad (through‑hole)** for secure battery connection.

---

## 🚀 Working Principle
1. Smartphone sends commands via Bluetooth.
2. ATmega328P decodes signals and drives the motor driver + MOSFET switches.
3. Motors, lights, buzzer, and servo respond accordingly.
4. Battery protection ensures safe and reliable operation.

---

## 🛠 Skills Highlight
- ✅ Schematic capture in EasyEDA  
- ✅ PCB routing (2‑layer board)  
- ✅ Power supply & battery protection design  
- ✅ Motor driver integration (DRV8210)  
- ✅ Custom footprint creation (motor pad, connector, battery pad)  
- ✅ Gerber generation for manufacturing  
- ✅ 3D visualization of PCB

---

## 🖼️ Visuals
### Schematic
![Schematic](Schematic(Img_Pdf)\Schematic_bluetooth-controlled-toy-car.png)
