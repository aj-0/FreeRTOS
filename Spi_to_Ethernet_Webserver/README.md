<img width="1280" height="582" alt="image" src="https://github.com/user-attachments/assets/b9c057e7-c279-4032-8d0c-02628bced439" />
# 🌐 STM32 W5500 Ethernet Web Server – LED Control

A lightweight embedded HTTP web server built using **STM32** and the **W5500 Ethernet Controller**. The project demonstrates how an STM32 can act as a standalone web server that allows users to control an onboard LED through any web browser on the local network.

---

## 🛠 Hardware & tools Used

* STM32F407 Discovery Board
* W5500 Ethernet Module
* Ethernet Cable
* ST-Link Debugger
* Wireshark
* Hercules

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

Clicking either button sends an HTTP GET request to the STM32 web server.

---

## 📂 Project Structure

```
Core/
 ├── Src/
 │    ├── main.c
 │    ├── stm32f4xx_hal_msp.c
 │
 ├── Inc/
 │    ├── main.h

W5500/
 ├── wizchip_conf.c
 ├── socket.c
 ├── w5500.c
 ├── wizchip_conf.h
 ├── socket.h
 └── w5500.h
```


## 🔄 Program Flow

```
STM32 Boot
      │
      ▼
Initialize SPI
      │
      ▼
Initialize W5500
      │
      ▼
Configure Network
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
Disconnect Client
      │
      ▼
Wait for Next Connection
```

---

## 📸 Expected Output

Open your browser and navigate to:

```
```

A web page appears with:

* LED ON
* LED OFF

Clicking the buttons controls the STM32 onboard LED over Ethernet.

---

## 📚 Concepts Covered

* Embedded TCP Server
* HTTP ,ICMP, HTTP,DHCP Protocol
* Ethernet Communication
* W5500 Socket API
* SPI Communication
* Static IP Configuration
* Embedded Web Server Development

--
<img width="1280" height="582" alt="image" src="https://github.com/user-attachments/assets/ccf89de5-fbd2-4bf3-9d3c-c9643bd13115" />


