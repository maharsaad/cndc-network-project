# Multi-Departmental Floor Network Design

A Cisco Packet Tracer simulation project designing a scalable, secure, and logically segmented network for a multi-floor commercial building. Developed as part of the CNDC (Computer Networks & Data Communication) coursework.

## 1. Introduction

In modern organizational environments, efficient and secure communication infrastructure is essential for supporting daily operations, collaboration, and data exchange. As businesses expand across multiple floors or departments, the need for a scalable and logically segmented network becomes increasingly critical.

This project presents the conceptual design and technical configuration of a multi-floor departmental network, built and simulated using **Cisco Packet Tracer** — a widely used tool for network modeling and validation.

The network architecture accommodates multiple departments distributed across **three floors** of a commercial building. Each floor operates semi-independently with its own routers, switches, computers, and printers, while maintaining seamless connectivity with other floors through inter-router links. The design emphasizes modularity, reliability, and security, ensuring departmental traffic is logically separated and efficiently routed.

### Design Goals
- Reliable connectivity between all departments
- Dynamic IP address assignment using **DHCP**
- Logical separation of departments through **VLANs**
- Secure inter-floor communication via **router-based inter-VLAN routing**


### Full Network Topology
<img width="982" height="606" alt="Screenshot 2026-06-28 at 3 50 30 PM" src="https://github.com/user-attachments/assets/9055b396-0885-496d-b1f6-62a3bdf70d38" />

### Floor 1 Configuration
<img width="501" height="226" alt="Screenshot 2026-06-28 at 3 51 43 PM" src="https://github.com/user-attachments/assets/17df1c2b-2b5e-430c-bb2f-81682527c751" />


### Floor 2 Configuration
<img width="311" height="355" alt="Screenshot 2026-06-28 at 3 53 31 PM" src="https://github.com/user-attachments/assets/f318742c-fa8e-4716-b3a2-3553993118b0" />



### Floor 3 Configuration
<img width="308" height="339" alt="Screenshot 2026-06-28 at 3 52 28 PM" src="https://github.com/user-attachments/assets/08fa43bc-c296-4f43-806a-84e32826b39e" />


## 2. Network Topology Overview

The network spans three floors, each containing specific departments. Each floor includes:

- **One router** — manages routing and DHCP for that floor
- **One switch** — handles VLAN segmentation
- **End devices** (PCs, printers) — assigned to department-specific VLANs
- **DHCP pools** — automate IP assignment per department

### IP Addressing & DHCP

Each department is assigned a unique subnet. DHCP pools are configured on each floor's router to automatically assign IP addresses to connected devices.

### VLAN Configuration

VLANs logically divide departments within each floor. Each VLAN has a unique ID and is mapped to specific switch ports, isolating traffic between departments while still allowing controlled inter-VLAN routing through the router.

## 3. Floor-Wise Configuration

### Floor 1 — Reception, Store, Logistics

| Department | Subnet | VLAN |
|------------|--------|------|
| Reception  | 192.168.8.0/24 | 10 |
| Store      | 192.168.7.0/24 | 20 |
| Logistics  | 192.168.6.0/24 | 30 |

# Router Configuration:
<img width="331" height="276" alt="Screenshot 2026-06-28 at 3 45 44 PM" src="https://github.com/user-attachments/assets/ffa69404-f13b-45e3-9f8b-da059aee9a06" />


# Switch Configuration:
<img width="243" height="227" alt="Screenshot 2026-06-28 at 3 46 07 PM" src="https://github.com/user-attachments/assets/33892f21-4c53-4fa6-9308-29c6c3d2430a" />

### Floor 2 — Finance, HR, Sales

| Department | Subnet |
|------------|--------|
| Finance    | 192.168.5.0/24 |
| HR         | 192.168.4.0/24 |
| Sales      | 192.168.3.0/24 (VLAN 50) |

# Router Configuration:
<img width="289" height="293" alt="Screenshot 2026-06-28 at 3 47 02 PM" src="https://github.com/user-attachments/assets/c6bb1fbf-8374-4fed-ae8f-e5d9948efdc0" />

# Switch Configuration:
<img width="194" height="106" alt="Screenshot 2026-06-28 at 3 47 21 PM" src="https://github.com/user-attachments/assets/63820de1-4572-43cd-88de-ace94eda3b73" />
### Floor 3 — IT and Admin

| Department | Subnet | VLAN |
|------------|--------|------|
| Admin      | 192.168.2.0/24 | — |
| IT         | 192.168.1.0/24 | 10 |

# Router Configuration:
<img width="244" height="182" alt="Screenshot 2026-06-28 at 3 47 43 PM" src="https://github.com/user-attachments/assets/62261708-d987-4cc7-8450-fa9e3dfdd481" />

# Switch Configuration:
<img width="218" height="123" alt="Screenshot 2026-06-28 at 3 48 11 PM" src="https://github.com/user-attachments/assets/a0d2f60b-16ff-4214-9977-fa08338ef133" />

## 4. Project Files

- `Cndc project.pkt` — Full Cisco Packet Tracer simulation file containing all routers, switches, end devices, and configurations across the three floors

## 5. How to Open & Test

1. Download and install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (free, requires a Cisco NetAcad account)
2. Open `Cndc project.pkt`
3. Use **Simulation Mode** to test connectivity:
   - Ping between devices on the same VLAN (should succeed)
   - Ping between devices on different VLANs within the same floor (should route through the router)
   - Ping between devices on different floors (should route through inter-router links)
4. Use `ipconfig` on PCs to verify DHCP-assigned IP addresses

## 6. Conclusion

This multi-floor departmental network ensures efficient connectivity, security, and scalability. By segmenting each department using VLANs and managing IP distribution through DHCP, network administration becomes simpler and more structured. Routers provide inter-VLAN routing for seamless communication, while switches ensure departmental separation. This design effectively meets the requirements of a multi-department, multi-floor enterprise network setup.

## Tools Used

- **Cisco Packet Tracer** — network simulation and configuration
- **DHCP** — dynamic IP allocation
- **VLANs** — logical network segmentation
- **Inter-VLAN Routing** — cross-department/floor communication
