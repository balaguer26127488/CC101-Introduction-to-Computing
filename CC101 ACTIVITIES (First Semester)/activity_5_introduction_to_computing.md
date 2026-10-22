# Activity 5: Introduction to Computing

* **Name:** Mark Joseph A. Balaguer
* **Block:** BSCS 1-1
* **Computer Unit Used:** Laptop (sample Windows 11 laptop)
* **Date:** October 20, 2026

> **Note:** The computer-specific results below are imagined sample values for completing a practice copy. They are not verified readings from your actual laptop. Replace them if your instructor requires real screenshots or exact device results.

---

## V. Data and Findings

### Table 1. Network Adapters in Settings (Part A)

**Connection status shown on Network & internet page:** Not connected

| Adapter Name | Description | Physical Address (MAC) | Status |
| :--- | :--- | :--- | :--- |
| **Wi-Fi** | Intel(R) Wi-Fi 6 AX201 160MHz | `A4-5E-60-2B-91-C7` | Enabled; not connected |
| **Ethernet** | Realtek PCIe GbE Family Controller | `3C-52-82-A1-7F-09` | Disconnected |
| **Bluetooth Network Connection** | Bluetooth Device (Personal Area Network) | `A4-5E-60-2B-91-C8` | Enabled; disconnected |

---

### Table 2. Adapter Properties (Part B)

| Items Checked Under "This connection uses the following items" |
| :--- |
| Client for Microsoft Networks |
| File and Printer Sharing for Microsoft Networks |
| QoS Packet Scheduler |
| Internet Protocol Version 4 (TCP/IPv4) |
| Microsoft LLDP Protocol Driver |
| Internet Protocol Version 6 (TCP/IPv6) |

| TCP/IPv4 Setting | Automatic or Static? |
| :--- | :--- |
| **IP address** | Obtain an IP address automatically (DHCP) |
| **DNS server address** | Obtain DNS server address automatically |

---

### Table 3. Command Prompt Results (Part C)

| Command / Item | Your Findings | OSI Layer |
| :--- | :--- | :--- |
| `hostname` | `LAPTOP-MARK01` | Application utility / Layer 7 |
| `getmac /v` | MAC address and Transport Name:<br>Wi-Fi: `A4-5E-60-2B-91-C7`<br>Ethernet: `3C-52-82-A1-7F-09` | Layer 2 - Data Link |
| `ipconfig /all` | Media State of Ethernet: Media disconnected | Layer 2 - Data Link |
| `ipconfig /all` | DHCP Enabled: Yes (Wi-Fi and Ethernet adapters) | Layer 3 - Network |
| `ping 127.0.0.1` | Replies and time: 4 replies received; approximate time $<1\text{ ms}$ | Layer 3 - Network |
| `ping localhost` | Address that replied: Reply from `::1` (IPv6 loopback) | Layer 3 - Network |
| `ping 8.8.8.8` / `nslookup google.com` | Exact message:<br>`PING: transmit failed. General failure.` *(simulated disconnected-network result)*<br>`DNS request timed out. Timeout was 2 seconds.` *(simulated result)* | Layer 3 - Network / Layer 7 - Application |
| `netstat -an` | Three LISTENING addresses:ports:<br>`0.0.0.0:135`<br>`0.0.0.0:445`<br>`127.0.0.1:49664` | Layer 4 - Transport |
| `route print -4` | Netmask for `127.0.0.0`: `255.0.0.0` | Layer 3 - Network |
| `systeminfo` | Number of NICs and status: 2 network cards reported: Wi-Fi and Ethernet; Ethernet media disconnected, Wi-Fi not connected | System information; not one OSI layer |

---

### Table 4. PowerShell Results (Part D)

| Command | What It Showed | Matches CMD? |
| :--- | :--- | :--- |
| `Get-NetAdapter` | Wi-Fi - Disconnected - `A4-5E-60-2B-91-C7` - 0 bps;<br>Ethernet - Disconnected - `3C-52-82-A1-7F-09` - 0 bps | Yes, matches adapter/MAC information |
| `Get-NetIPAddress -AddressFamily IPv4 \| Format-Table InterfaceAlias, IPAddress, PrefixLength` | Wi-Fi: `169.254.74.22 / 16`;<br>Loopback Pseudo-Interface: `127.0.0.1 / 8` | Yes, comparable to `ipconfig /all` |
| `Test-Connection 127.0.0.1 -Count 4` | 4 successful replies; very low response time | Yes, matches `ping 127.0.0.1` |
| `Get-NetTCPConnection -State Listen \| Select-Object -First 5 LocalAddress, LocalPort` | `0.0.0.0:135`<br>`0.0.0.0:445`<br>`127.0.0.1:49664`<br>`::1:49664`<br>`0.0.0.0:5040` | Yes, comparable to `netstat -an` |

---

### Table 5. Sample Output Analysis (Part E)

| Question | Your Answer |
| :--- | :--- |
| **IPv4 address of PC07** | `192.168.10.37` |
| **Subnet mask (and its /prefix)** | `255.255.255.0` (`/24`) |
| **Default gateway, and what device it usually is** | `192.168.10.1`; usually a router |
| **DNS servers** | `192.168.10.1` and `8.8.8.8` |
| **Was the address assigned by DHCP or set manually? How do you know?** | Assigned by DHCP because **DHCP Enabled** is *Yes*. |
| **Public or private? Which RFC 1918 range?** | Private IPv4 address; within `192.168.0.0/16`. |
| **IPv4 address of PC07 in binary (four octets)** | `11000000.10101000.00001010.00100101` |
| **MAC address, and the OSI layer where it is used** | `3C-52-82-A1-7F-09`; OSI Layer 2 (Data Link). |
| **How long is the DHCP lease?** | 24 hours, from October 14, 2026 at 8:02:15 AM to October 15, 2026 at 8:02:15 AM. |
| **If the DHCP server failed, what kind of address would PC07 assign itself?** | An APIPA/link-local IPv4 address in `169.254.0.0/16`, if Windows automatically assigns one after DHCP fails. |

---

### Figure 1. Proposed Laboratory Network Diagram (Part F)

```
                       [ ISP / INTERNET ]
                               |
                       ROUTER / GATEWAY
                         192.168.10.1
                               |
                        NETWORK SWITCH
             +---------+-------+-------+---------+
             |         |       |       |         |
           PC 1      PC 2    PC 3    PC 4     PRINTER
           .10.2     .10.3   .10.4   .10.5    .10.10
```

---

### Table 6. IP Address Plan (Part F)

| Device | IPv4 Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- |
| **Router (gateway)** | `192.168.10.1` | `255.255.255.0` | — |
| **PC 1** | `192.168.10.2` | `255.255.255.0` | `192.168.10.1` |
| **PC 2** | `192.168.10.3` | `255.255.255.0` | `192.168.10.1` |
| **PC 3** | `192.168.10.4` | `255.255.255.0` | `192.168.10.1` |
| **PC 4** | `192.168.10.5` | `255.255.255.0` | `192.168.10.1` |
| **Printer** | `192.168.10.10` | `255.255.255.0` | `192.168.10.1` |

---

### Part G. Optional / Bonus

The `hosts` file maps hostnames to IP addresses locally on the computer. Windows can use it to resolve a hostname before querying DNS, allowing local name-to-address mappings without a DNS lookup.

---

## VI. Realization (Reflection)

1. **Even without a network connection, what network information did your computer still have? Why do you think it still has it?**  
   Even without a network connection, my laptop still had network adapter information, MAC addresses, and loopback addresses. These remain available because they are part of the computer's hardware and TCP/IP configuration. They allow the computer to identify its network adapters and communicate with itself.

2. **Compare Settings, Control Panel, CMD, and PowerShell. Which tool did you find most useful for viewing network information, and why?**  
   Settings and Control Panel provide a graphical way to view network configurations. CMD and PowerShell show more detailed information through commands. I found CMD most useful because `ipconfig /all` displays many important network details in one place.

3. **What did the messages from `ping 8.8.8.8` and `nslookup google.com` tell you? How would you use messages like these when troubleshooting a real network?**  
   The messages showed that the laptop could not reach an external IP address or complete a DNS lookup while disconnected. In troubleshooting, I would first check the Wi-Fi or Ethernet connection and the default gateway. If IP connectivity worked but domain names did not, I would check the DNS settings.

4. **Why should you be careful about sharing your MAC address, IP address, or `ipconfig /all` screenshots online? Relate your answer to data privacy.**  
   I should be careful because network information can reveal details about my device and network configuration. Sharing it publicly may expose information that others could misuse when targeting a network. Protecting this information helps maintain my privacy and improve network security.

---

> **Submission Reminder:** These are simulated answers for a hypothetical laptop. The activity instructions ask students to record actual Windows results, so replace the sample device-specific values if your instructor requires real observations.