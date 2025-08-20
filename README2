# 🌐 Inter-VLAN Routing with HSRP & DHCP

## 📖 Overview
This project demonstrates the design and configuration of a **redundant Layer 3 network** using:

- **HSRP (Hot Standby Router Protocol)** for gateway redundancy.  
- **Inter-VLAN Routing** on multilayer switches.  
- **DHCP** for dynamic IP allocation to end devices.  

The setup ensures **high availability**, **load balancing**, and **automated addressing** across multiple VLANs.

---

## 🖥️ Network Topology

### Devices Used
- **2 Multilayer Switches (Cisco 3650-24PS)** – DSW1 (Standby) & DSW2 (Active).  
- **2 Access Switches (Cisco 2960-24TT)** – For end devices.  
- **1 Router (Cisco 4331)** – For external connectivity.  
- **1 DHCP Server** – Provides dynamic IP addressing.  
- **4 PCs** – Connected to VLANs for testing.  

### Subnet Allocation
| VLAN | Subnet | Virtual Gateway (HSRP) | Purpose |
|------|---------|--------------------------|---------|
| VLAN 10 | 192.168.10.0/24 | 192.168.10.200 | End Devices |
| VLAN 20 | 192.168.20.0/24 | 192.168.20.200 | End Devices |
| Router Link 1 | 192.168.30.0/24 | 192.168.30.1 | R1 ↔ Switches |
| Router Link 2 | 192.168.40.0/24 | 192.168.40.1 | R1 ↔ Switches |
| Server Network | 192.168.50.0/24 | 192.168.50.1 | DHCP & Services |

---

## 🔑 Key Features
- **Redundancy with HSRP**
  - Virtual IPs: `192.168.10.200` (VLAN 10) & `192.168.20.200` (VLAN 20).  
  - DSW2 is the **active gateway**, DSW1 is **standby**.  
  - Automatic failover ensures business continuity.  

- **Layer 3 Inter-VLAN Routing**
  - SVIs (Switch Virtual Interfaces) configured on DSW1 & DSW2.  
  - `ip routing` enabled for routing between VLANs.  

- **DHCP Integration**
  - Central DHCP server dynamically assigns IPs to PCs.  

- **Efficient Trunking & VLAN Segmentation**
  - Uplinks configured as trunks.  
  - End-device ports assigned to access VLANs.  

- **External Connectivity**
  - Router R1 connected to multilayer switches.  
  - Static route ensures reachability to VLANs via HSRP gateways.  

---

## ⚙️ Configuration Highlights

### 🟦 On DSW1 (Standby) & DSW2 (Active)
- VLAN creation & trunking.  
- SVI IP assignment.  
- HSRP configuration with **priority & preempt**.  
- EtherChannel setup for redundancy.  

### 🟩 On Access Switches (S1 & S2)
- Ports assigned to VLAN 10 or VLAN 20.  
- Trunk links configured for uplinks.  

### 🟨 On Router R1
- Interfaces configured for `192.168.30.0/24` and `192.168.40.0/24`.  
- Static route to internal VLAN networks via HSRP gateway.  

---

## 🧪 Testing & Verification
1. **DHCP Assignment**  
   - PCs should obtain IPs automatically in their VLAN range.  

2. **Inter-VLAN Communication**  
   - PCs in VLAN10 can ping PCs in VLAN20.  

3. **HSRP Failover**  
   - Shutdown DSW2 (Active).  
   - Verify DSW1 takes over as gateway using virtual IPs.  

4. **External Connectivity**  
   - Ping external networks via Router R1.  

---

## ✅ Outcomes
- **Reliable Inter-VLAN routing**.  
- **Automatic DHCP IP allocation**.  
- **Gateway redundancy with HSRP**.  
- **Seamless failover** between DSW1 & DSW2.  

---

## 🚀 Future Improvements
- Replace static routing with **OSPF/EIGRP** for scalability.  
- Add **DHCP Snooping & Dynamic ARP Inspection (DAI)** for security.  
- Implement **Port Security** on access switches.  
- Extend with additional VLANs and service networks.  

---
