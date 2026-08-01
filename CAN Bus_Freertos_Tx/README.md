# 🚗 **CAN Bus FreeRTOS TX**

## 📖 Short Description

This project demonstrates **CAN Bus message transmission** using **FreeRTOS** on the **STM32F407 Discovery** board. A dedicated FreeRTOS task periodically transmits CAN frames through the CAN peripheral and **MCP2551 CAN Transceiver**, providing a basic real-time communication system commonly used in automotive embedded applications.

---

# 🏗️ Architecture

```text
                  +----------------------+
                  |  FreeRTOS Scheduler  |
                  +----------+-----------+
                             |
                      CAN_TX_Task
                             |
                 HAL_CAN_AddTxMessage()
                             |
                      CAN1 Peripheral
                             |
                 MCP2551 CAN Transceiver
                             |
                        CAN Bus Network
```

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
| PB8 | CAN_RX   |
| PB9 | CAN_TX   |

## 🚨 NVIC Configuration

* CAN Interrupt (If Enabled)

## 📦 Middleware

* FreeRTOS

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

# 📚 Concepts Covered

* ✅ Embedded C
* ✅ ARM Cortex-M4
* ✅ STM32 HAL
* ✅ FreeRTOS
* ✅ Task Creation
* ✅ Task Scheduling
* ✅ CAN Protocol
* ✅ CAN Frame Transmission
* ✅ MCP2551 CAN Transceiver
* ✅ Embedded Debugging
* ✅ Peripheral Initialization
* ✅ Real-Time Systems

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
