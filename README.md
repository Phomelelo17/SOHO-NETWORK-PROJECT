# Small Office / Home Office (SOHO) Network Design & Security
**Author:** Lesetja Chuene
**Tool Used:** Cisco Packet Tracer

## 📖 Project Overview
Designed and implemented a secure, multi-VLAN network topology simulating a small business environment. The project demonstrates core networking concepts including network segmentation, automated IP addressing, internet edge simulation, and security policy enforcement using Access Control Lists (ACLs).

## 🛠️ Technologies & Concepts Implemented
*   **VLANs & Trunking:** Segregated traffic into VLAN 10 (Office), VLAN 20 (Guest), and VLAN 30 (Servers) using 802.1Q trunk links.
*   **Inter-VLAN Routing:** Configured Router-on-a-Stick on the Cisco 2911 router to allow communication between VLANs.
*   **DHCP Server:** Configured centralized DHCP pools on the router to automatically assign IP addresses, subnet masks, and default gateways to Office and Guest endpoints.
*   **NAT (Network Address Translation):** Implemented PAT (Port Address Translation / Overload) to translate internal private IPs to a public WAN IP, simulating internet access via an ISP router.
*   **Access Control Lists (ACL):** Created and applied an Extended ACL to block Guest traffic from reaching the internal Server network, while still allowing outbound internet access.

## 🌐 IP Addressing Scheme
*   **VLAN 10 (Office):** `192.168.10.0/24` (Gateway: `192.168.10.1`)
*   **VLAN 20 (Guest):** `192.168.20.0/24` (Gateway: `192.168.20.1`)
*   **VLAN 30 (Servers):** `192.168.30.0/24` (Gateway: `192.168.30.1`)
*   **WAN (Simulated ISP):** `10.0.0.0/30`

## ✅ Verification & Testing
*[Screenshot 2026-11-01 132401.png](./Screenshot%2026-11-01%132401.png)*
*[Screenshot 2026-11-01 132840.png](Screenshot%2026-11-01%132840.png)*
*[Screenshot 2026-11-01 132821.png](Screenshot%2026-11-01%132821.png)*
*[Screenshot 2026-11-01 132606.png](Screenshot%2026-11-01%132606.png)*
*[Screenshot 2026-11-01 132502.png](Screenshot%2026-11-01%132502.png)*

*   **Inter-VLAN Routing:** Verified successful pings between Office VLAN (PC0) and Server VLAN.
*   **Security Policy:** Verified Extended ACL successfully denies Guest (PC1) traffic from accessing the Server.
*   **NAT/PAT:** Verified Guest endpoints can successfully reach the simulated external internet (8.8.8.8) while remaining blocked from internal servers.
*   **DHCP:** Verified automated IP assignment via `show ip dhcp binding` on the router.
