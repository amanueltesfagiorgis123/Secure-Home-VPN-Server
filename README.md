#  Secure Home VPN Server (Raspberry Pi & WireGuard)

A personal project implementing a lightweight, high-performance Virtual Private Network (VPN) server using a **Raspberry Pi** and **PiVPN / WireGuard**. This project establishes secure remote access to a home network, ensuring encrypted traffic routing and secure device management over public networks.

---

## 🚀 Key Features
* **Modern Cryptography:** Powered by WireGuard, offering state-of-the-art cryptographic protocols (ChaCha20, Curve25519) for fast speeds and minimal overhead.
* **Streamlined Deployment:** Configured using PiVPN for automated installation, key management, and client profile generation.
* **Remote Secure Access:** Allows remote client devices (laptops, smartphones) to securely tunnel into the home network from external networks (cellular, public Wi-Fi).
* **Headless Linux Administration:** Managed entirely via SSH on Raspberry Pi OS, emphasizing command-line proficiency and system maintenance.

---
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


***

<Elicitations message="What would you like to do next?">
  <Elicitation label="Add security best practices" query="How can I add a security section to this README covering firewall rules or fail2ban?"/>
  <Elicitation label="Document Dynamic DNS" query="How do I document Dynamic DNS integration in this README?"/>
</Elicitations>

## Network Topology & Architecture
```mermaid
flowchart TD
    subgraph External [External / Remote Network]
        RemoteClient[Remote Mobile / Laptop]
    end

    subgraph HomeNet [Home Network / LAN]
        Router[Home Network Router<br/>Port Forward: 51820 UDP]
        LocalClient[Local LAN Clients<br/>PC, Smart Devices]
        
        subgraph PiNode [Raspberry Pi Node]
            VPN[WireGuard VPN Server<br/>Interface: wg0]
            DNS[Pi-hole DNS Sinkhole<br/>Interface: eth0]
        end
    end

    Upstream[Upstream DNS<br/>Cloudflare / Quad9]

    %% External Traffic Flow
    RemoteClient -->|Encrypted WireGuard Tunnel| Router
    Router -->|Forward UDP 51820| VPN
    VPN -->|Internal DNS Queries| DNS

    %% Local Traffic Flow
    LocalClient -->|DNS Queries Port 53| DNS

    %% Outbound DNS Resolution
    DNS -->|Filtered Upstream Queries| Upstream

    %% Styling
    style RemoteClient fill:#e2e8f0,stroke:#64748b,stroke-width:2px
    style Router fill:#fef3c7,stroke:#d97706,stroke-width:2px
    style LocalClient fill:#e2e8f0,stroke:#64748b,stroke-width:2px
    style VPN fill:#dbeafe,stroke:#2563eb,stroke-width:2px
    style DNS fill:#dcfce7,stroke:#16a34a,stroke-width:2px
    style Upstream fill:#f3e8ff,stroke:#9333ea,stroke-width:2px
