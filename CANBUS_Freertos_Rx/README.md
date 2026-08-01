# 🚘 STM32-to-STM32 CAN Communication Using MCP2551
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/2a61da59-518c-48df-9102-0031a45e6081" />

Implemented CAN 2.0 communication between two **STM32F407 Discovery** boards using **MCP2551 CAN transceivers**. This project demonstrates real CAN bus communication, including CAN peripheral configuration, frame transmission and reception, acceptance filter configuration, and physical-layer communication over the CAN bus.

---

## ✨ Key Highlights

* Two STM32F407 Discovery Boards
* Two MCP2551 CAN Transceivers
* CAN 2.0 Communication
* Physical CAN Bus
* Polling-Based Communication
* Acceptance Filter Configuration

---

## 🏗️ Architecture

```text
STM32F407
   │
CAN1 TX/RX
   │
   ▼
MCP2551
   │
CANH ───────────── CANH (120Ω Resistor)
CANL ───────────── CANL (120Ω Resistor)
   │
MCP2551
   │
CAN1 TX/RX
   ▼
STM32F407
```

---

## 🔧 Hardware

* STM32F407 Discovery ×2
* MCP2551 CAN Transceiver ×2
* 120 Ω Termination Resistors ×2
* Twisted Pair (CANH/CANL)
* ST-LINK Debugger
---

## ⚙️ STM32 Peripherals

* CAN1 =  PD0 , PD1
* GPIO
* RCC
* SysTick
<img width="1280" height="720" alt="WhatsApp Image 2026-07-23 at 7 23 03 PM" src="https://github.com/user-attachments/assets/59081934-65c0-464f-973f-57121bb52f13" />

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/17af056d-7940-44ad-8b9f-a5915cca425f" />

---

