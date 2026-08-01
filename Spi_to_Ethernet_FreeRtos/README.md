## 🌐 STM32 W5500 Ping Test
<img width="1280" height="581" alt="image" src="https://github.com/user-attachments/assets/a462a21e-5897-48c5-950d-188ab359a9d1" />

A lightweight **Embedded HTTP Web Server** built using the **STM32F407 Discovery Board**, **W5500 Ethernet Controller**, and **FreeRTOS**. The project demonstrates a multitasking embedded application where an STM32 hosts a web server that allows users to control the onboard LED from any web browser over a local Ethernet network.

---

# 🛠 Hardware & Tools

## Hardware

* STM32F407 Discovery Board
* W5500 Ethernet Module
* Ethernet Cable
* Router / Switch
* ST-Link Debugger

## Software

* STM32CubeIDE
* STM32CubeMX
* FreeRTOS
* WIZnet ioLibrary
* Wireshark
* Hercules

---

# 📡 Network Configuration

| Parameter   | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.5.50  |
| Gateway     | 192.168.5.1   |
| Subnet Mask | 255.255.255.0 |
| HTTP Port   | 80            |

---

# 🧵 FreeRTOS Task Architecture

| Task             | Responsibility                                       |
| ---------------- | ---------------------------------------------------- |
| Network Task     | Initializes W5500 and Ethernet stack                 |
| HTTP Server Task | Accepts client connections and handles HTTP requests |
| LED Control Task | Controls onboard LED based on received commands      |

---

# 🌐 Web Interface

The browser provides a simple dashboard containing:

* 🟢 LED ON Button
* 🔴 LED OFF Button

When a button is pressed, the browser sends an HTTP GET request to the STM32 web server.

```
GET /ledon
GET /ledoff
```

The HTTP Server Task parses the request and updates the LED state.

---

# 📂 Project Structure

```text
Core/
├── Inc/
│   └── main.h
│
├── Src/
│   ├── main.c
│   ├── freertos.c
│   └── stm32f4xx_hal_msp.c
│
Middlewares/
└── FreeRTOS/
    ├── Source/
    └── CMSIS_RTOS/
│
Drivers/
├── STM32 HAL Drivers
└── CMSIS
│
W5500/
├── socket.c
├── socket.h
├── wizchip_conf.c
├── wizchip_conf.h
├── w5500.c
└── w5500.h
```

---

# 🔄 Application Flow

```text
System Reset
      │
      ▼
HAL Initialization
      │
      ▼
SPI Initialization
      │
      ▼
GPIO Initialization
      │
      ▼
FreeRTOS Kernel Initialization
      │
      ▼
Create Tasks
      │
      ▼
Start Scheduler
      │
      ▼
──────────────────────────────────────
Network Task
      │
      ▼
Initialize W5500
      │
      ▼
Configure Static IP
      │
      ▼
Open TCP Socket (Port 80)
      │
      ▼
Listen for Client
──────────────────────────────────────
      │
      ▼
HTTP Server Task
      │
      ▼
Receive HTTP Request
      │
      ▼
Parse GET Request
      │
      ├────────► /ledon
      │             │
      │             ▼
      │      Notify LED Task
      │
      └────────► /ledoff
                    │
                    ▼
             Notify LED Task
      │
      ▼
Send HTML Response
      │
      ▼
Close Connection
──────────────────────────────────────
      │
      ▼
LED Task
      │
      ▼
GPIO ON / GPIO OFF
```

---
<img width="1600" height="610" alt="image" src="https://github.com/user-attachments/assets/6066d9a4-993b-4ea1-86cb-ef958f5da581" />
<img width="1600" height="526" alt="image" src="https://github.com/user-attachments/assets/21cee1ee-d3ad-4339-bfcf-e674a20f6add" />

<p align="center">
<img width="900" src="https://github.com/user-attachments/assets/ccf89de5-fbd2-4bf3-9d3c-c9643bd13115">
</p>

