## 🌐 STM32 W5500 Ethernet Web Server – LED Control
<img width="1280" height="581" alt="image" src="https://github.com/user-attachments/assets/672f6b8c-63e7-47e7-8b51-ec8e1cbe03e7" />

A lightweight embedded HTTP web server built using **STM32**, **W5500 Ethernet Controller**, and **FreeRTOS**. The project demonstrates how an STM32 can act as a standalone web server while running under the FreeRTOS scheduler, allowing users to control the onboard LED through any web browser on the local network.

---

## 🛠 Hardware & tools Used

* STM32F407 Discovery Board
* W5500 Ethernet Module
* Ethernet Cable
* ST-Link Debugger
* Wireshark
* Hercules
* STM32CubeIDE
* STM32CubeMX
* FreeRTOS
* WIZnet ioLibrary

---

## 📡 Network Configuration

| Parameter   | Value         |
| ----------- | ------------- |
| IP Address  | 192.168.5.50  |
| Gateway     | 192.168.5.1   |
| Subnet Mask | 255.255.255.0 |
| Port        | 80 (HTTP)     |

---

## 🌐 Web Interface

The browser displays a simple control panel containing:

* LED ON Button
* LED OFF Button

Clicking either button sends an HTTP GET request to the STM32 web server, where the corresponding FreeRTOS task processes the request and updates the onboard LED.

---

## 📂 Project Structure

```text
Core/
 ├── Src/
 │    ├── main.c
 │    ├── freertos.c
 │    └── stm32f4xx_hal_msp.c
 │
 ├── Inc/
 │    ├── main.h
 │
W5500/
 ├── wizchip_conf.c
 ├── socket.c
 ├── w5500.c
 ├── wizchip_conf.h
 ├── socket.h
 └── w5500.h
```

---

## 🔄 Program Flow

```text
STM32 Boot
      │
      ▼
Initialize HAL
      │
      ▼
Initialize GPIO & SPI
      │
      ▼
Initialize W5500
      │
      ▼
Configure Network
      │
      ▼
Create FreeRTOS Tasks
      │
      ▼
Start FreeRTOS Scheduler
      │
      ▼
HTTP Server Task
      │
      ▼
Open TCP Socket (Port 80)
      │
      ▼
Listen for Client
      │
      ▼
Receive HTTP Request
      │
      ▼
Parse URL
      │
      ├────────► /ledon
      │              │
      │              ▼
      │          LED ON
      │
      └────────► /ledoff
                     │
                     ▼
                  LED OFF
      │
      ▼
Send HTML Response
      │
      ▼
Wait for Next Client
```

---

## 📸 Expected Output

Open your browser and navigate to:

```text
http://192.168.5.50
```

A web page appears with:

* LED ON
* LED OFF

Clicking the buttons controls the STM32 onboard LED over Ethernet.

---

## 📚 Concepts Covered

* FreeRTOS Task Scheduling
* Embedded TCP Server
* HTTP Protocol
* ICMP Protocol
* DHCP Protocol
* Ethernet Communication
* W5500 Socket API
* SPI Communication
* Static IP Configuration
* Embedded Web Server Development
* HTTP GET Request Parsing
* GPIO Control
