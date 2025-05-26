# Nmap-based port scanning to analyze open ports, detect services, and assess network security.  

---

## 🛠️ Commands Used  

### 1️⃣ **Run Nmap TCP SYN Scan** ⚡ 

Perform a stealth scan on a target:

```bash
nmap -sS <your-ip>
```

## Run Nmap as Administrator (Windows) 🔧

Some ports require privileged access. Open Command Prompt as Administrator and run:
nmap -sS <target_ip>


## 3️⃣ Expanding the Scan Range
Scan ports 1–1000 for a broader overview:
nmap -sS <your-ip> -p 1-1000


Scan the top commonly used ports instead:
nmap -sS --top-ports 100 <your-ip>


## 4️⃣ Firewall Detection & Bypass Attempts 🔒

Detect filtered ports blocked by firewalls:
nmap -sS -Pn <your-ip>


Aggressive scan with OS detection & more details:
nmap -A <your-ip>


## 5️⃣ Logging Results for Review 📝
Save scan output to a file:
nmap -sS <your-ip> -oN scan_results.txt

# 📡 Packet Capture & Analysis with Wireshark

## 6️⃣ Start Capturing Packets 🏁

- Open Wireshark and select the network interface you want to monitor (e.g., Ethernet or Wi-Fi).
- Click Start Capture and let it collect network packets.
  
## 7️⃣ Apply Filters for Analysis 🔍

Once packets are captured, apply filters to inspect specific traffic:
🔹 Filter by Protocol
- TCP traffic only:
```
tcp
```
- UDP packets:
```
udp
```
- ICMP (ping traffic):
```
icmp
```

🔹 Filter by Source/Destination IP
- Show packets from a specific source IP:
ip.src == 192.168.1.1
- Show packets sent to a destination IP:
ip.dst == 10.0.0.5


🔹 Filter by Port
- Capture traffic on port 80 (HTTP):
tcp.port == 80
- Capture DNS requests on port 53:
udp.port == 53


🔹 Track a Specific Connection
- Filter packets belonging to the same TCP conversation (replace <port> with actual port):
tcp.stream eq <port>





## 📊 Dataset Overview

This project works with port scan data, including:
- 🎯 Target IP address (e.g., 192.168.1.0/24)
- 🔓 Open ports detected
- 🔒 Filtered/closed ports
- 📡 Firewall interference messages
This data helps identify active services and assess network security.

### 🚀 Next Steps
🔹 Expand scanning to remote devices on the network.
🔹 Implement more aggressive scans for deeper insights.
🔹 Automate results logging & exporting for security audits.
🔎💻

---

