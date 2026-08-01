# 🚘 STM32-to-STM32 CAN Communication Using MCP2551

Implemented CAN 2.0 communication between two **STM32F407 Discovery** boards using **MCP2551 CAN transceivers**. This project demonstrates real CAN bus communication, including CAN peripheral configuration, frame transmission and reception, acceptance filter configuration, and physical-layer communication over the CAN bus.

---
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/8f5e0784-5b7c-4524-8a44-8db4991aa255" />

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
<img width="1917" height="887" alt="image" src="https://github.com/user-attachments/assets/f8e9ac3d-0e84-4bb7-aaf8-f411dbbadf51" />
<img width="1600" height="999" alt="image" src="https://github.com/user-attachments/assets/740e7b72-13aa-4abb-864b-f1aee8995bed" />
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/17af056d-7940-44ad-8b9f-a5915cca425f" />

---

