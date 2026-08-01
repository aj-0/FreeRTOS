# 🚗 **CAN Bus FreeRTOS RX**
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/2a61da59-518c-48df-9102-0031a45e6081" />

## 📖 Short Description

This project demonstrates **CAN Bus message transmission** using **FreeRTOS** on the **STM32F407 Discovery** board. A dedicated FreeRTOS task periodically transmits CAN frames through the CAN peripheral and **MCP2551 CAN Transceiver**, providing a basic real-time communication system commonly used in automotive embedded applications.

---

# 🛠️ Hardware & Software Tools

## 🔧 Hardware

* 🖥️ STM32F407 Discovery Board
* 🔌 MCP2551 CAN Transceiver
* 📡 CAN Bus with 120 Ω Termination Resistors
* 🐞 ST-LINK Debugger
* 🔗 USB Cable

## 💻 Software

* STM32CubeIDE
* STM32CubeMX
* STM32 HAL Drivers
* FreeRTOS
* Git & GitHub

---

# ⚙️ STM32CubeMX Configuration

## 🕒 Clock Configuration

* ✅ HSE Enabled
* ✅ PLL Enabled
* ✅ System Clock: **168 MHz**
* ✅ APB1 Clock Configured for CAN

## 🔩 Peripheral Configuration

### 🚘 CAN1

* Mode: Normal
* Auto Retransmission: Enabled
* CAN Filter Configured
* Transmit FIFO Enabled

### 📍 GPIO

| Pin | Function |
| --- | -------- |
| PD0 | CAN_RX   |
| PD1 | CAN_TX   |

---

# 🐞 Debugging & Problems Solved

## ❌ Problem

CAN peripheral failed to start.

## 🔍 Root Cause

Incorrect CAN initialization sequence and filter configuration.

## 🛠️ Debugging Steps

* ✔️ Verified `HAL_CAN_Init()` return value.
* ✔️ Verified `HAL_CAN_Start()` status.
* ✔️ Checked CAN filter configuration.
* ✔️ Verified CAN bit timing.
* ✔️ Monitored CAN error registers.
* ✔️ Used Breakpoints.
* ✔️ Used Live Expressions.
* ✔️ Verified FreeRTOS task execution.

## ✅ Solution

Configured CAN filters correctly and completed the required CAN initialization sequence before transmitting messages.

## 🎯 Skills Demonstrated

* CAN Peripheral Debugging
* FreeRTOS Task Debugging
* STM32 HAL Debugging
* Register Verification
* Real-Time Embedded Troubleshooting

---

# 📂 Project Structure

```text
CAN_Bus_FreeRTOS_TX/
│
├── Core/
│   ├── Inc/
│   └── Src/
│
├── Drivers/
│
├── Middlewares/
│   └── FreeRTOS/
│
├── Debug/
│
├── CAN_Bus_FreeRTOS_TX.ioc
│
└── README.md
```
<img width="1280" height="720" alt="WhatsApp Image 2026-07-23 at 7 23 03 PM" src="https://github.com/user-attachments/assets/6c976d71-35bf-4eb3-9bae-3d69eff1a1d8" />
<img width="1600" height="986" alt="image" src="https://github.com/user-attachments/assets/a49091ee-0854-4c44-bb57-4f6d6803bedc" />

