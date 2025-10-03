# Secure Multi-Section Network Design

## 📋 Project Overview
A comprehensive enterprise network design implementing secure three-section architecture with VLAN segmentation, OSPF dynamic routing, and multi-layered security controls using Cisco Packet Tracer.

## 🌐 Network Architecture

### Devices
- **3x Cisco 2911 Routers** (R1, R2, R3)
- **3x Cisco 2960 Switches** (SW1, SW2, SW3)
- **9x PCs** (3 per section, one for each VLAN)

### VLAN Configuration
- **VLAN 10**: Management
- **VLAN 20**: Users  
- **VLAN 30**: Guests
- **VLAN 99**: Native VLAN

### IP Addressing
| Section | Management VLAN | User VLAN | Guest VLAN |
|---------|-----------------|-----------|------------|
| 1 (R1) | 192.168.10.1/24 | 192.168.110.1/24 | 192.168.210.1/24 |
| 2 (R2) | 192.168.20.1/24 | 192.168.120.1/24 | 192.168.220.1/24 |
| 3 (R3) | 192.168.30.1/24 | 192.168.130.1/24 | 192.168.230.1/24 |

## 🛡️ Security Features Implemented

### Layer 2 Security
- **Port Security** (1 MAC per port, violation shutdown)
- **BPDU Guard + PortFast** on access ports
- **DHCP Snooping** with trusted trunk ports
- **All unused ports disabled**

### Layer 3 Security  
- **ACL Traffic Policies**:
  - Guest VLAN: Deny internal, permit external
  - User VLAN: Deny Management VLANs, permit other
  - Management VLAN: Full access
- **SSH-only access** (no Telnet)
- **Restricted management** to Management VLAN only

## 🔄 Routing Configuration
- **OSPF Process 1** on all routers
- **Area 0** for all networks
- **Full mesh connectivity** between sections

## 🚀 Getting Started

### Prerequisites
- Cisco Packet Tracer 8.x or later

### Installation
1. Download `Secure-Multi-Section-Network.pkt`
2. Open in Cisco Packet Tracer
3. The network is fully configured and ready for testing

## 🧪 Testing Features

The network includes comprehensive testing capabilities:

### Connectivity Tests
- VLAN segmentation verification
- Inter-VLAN routing tests
- Cross-section OSPF routing
- ACL policy enforcement

### Security Tests  
- Port security violation testing
- SSH access control verification
- DHCP snooping protection

## 📊 Verification Commands

### Switch Verification
```cisco
show vlan brief
show interfaces trunk
show port-security
```

### Router Verification
```cisco
show ip ospf neighbor
show ip route
show access-lists
```

## 👤 Author
Edward Sanga

## 📄 License
This project is for educational purposes.

---
**File**: `Secure-Multi-Section-Network.pkt`
**Format**: Cisco Packet Tracer
**Version**: 8.x
