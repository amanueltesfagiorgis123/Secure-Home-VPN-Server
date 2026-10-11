#  Secure Home VPN Server (Raspberry Pi & WireGuard)

A personal project implementing a lightweight, high-performance Virtual Private Network (VPN) server using a **Raspberry Pi** and **PiVPN / WireGuard**. This project establishes secure remote access to a home network, ensuring encrypted traffic routing and secure device management over public networks.

---

## 🚀 Key Features
* **Modern Cryptography:** Powered by WireGuard, offering state-of-the-art cryptographic protocols (ChaCha20, Curve25519) for fast speeds and minimal overhead.
* **Streamlined Deployment:** Configured using PiVPN for automated installation, key management, and client profile generation.
* **Remote Secure Access:** Allows remote client devices (laptops, smartphones) to securely tunnel into the home network from external networks (cellular, public Wi-Fi).
* **Headless Linux Administration:** Managed entirely via SSH on Raspberry Pi OS, emphasizing command-line proficiency and system maintenance.

---

## 🛠️ Architecture & Network Topology
[ Remote Client (Phone / Laptop) ]
│ (Encrypted WireGuard Tunnel over Cellular/Public Wi-Fi)
▼
[ Home Internet Router (Port Forwarding UDP 51830) ]
│
▼
[ Raspberry Pi VPN Server (Static Local IP) ]
│ (Local Subnet Routing: 10.6.0.0/24)
▼
[ Home Network Resources ]

## 📋 Prerequisites & Hardware
* **Hardware:** Raspberry Pi (running Raspberry Pi OS)
* **Networking:** 
  * Static local IP address assigned via router DHCP reservation.
  * Port forwarding configured on the home router (UDP port forwarded to the Pi).
* **Software:** PiVPN, WireGuard, OpenSSH Server

---

## ⚙️ Installation & Configuration Steps

### 1. Update System & Set Static IP
### 2. Install PiVPN
### 3. Configure Router Port Forwarding 
### 4. Create a client profile 
### 5. Connect your device 


