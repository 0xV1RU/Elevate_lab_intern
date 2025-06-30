## Capture and Analyze Network Traffic Using Wireshark
### 🎯 Objective:
To capture live network packets using Wireshark and identify at least three different protocols used during normal traffic (like ping, DNS query, or curl-based HTTP requests).
### 🧰 Tools Used:
> `Wireshark`

> `tshark` (CLI version of Wireshark)

> `ping`, `dig`, `curl` commands (for traffic generation)
### ⚙️ Steps Followed:
> #### Started Packet Capture:
- Interface used: wlan0
- Capture started using:
  
        sudo tshark -i eth0 -w task5_capture.pcap

> #### Generated Traffic Using CLI:
- `ping google.com` → ICMP packets
- `dig openai.com` → DNS packets
- `curl -X POST "http://tryhackme.com/login" -H "Content-Type: application/x-www-form-urlencoded" -d "email=test@example.com&password=123456"` → HTTP/TCP packets
- `tshark -i eth0 -f "port 53"` → Capture Only DNS Packets Live

> #### Stopped Capture:
- After ~1 minute using `Ctrl + C`

> #### Analyzed Captured Packets:
- Shows all available interfaces (Wi-Fi, Ethernet, etc.)

      tshark -D
  
![image](https://github.com/user-attachments/assets/50990cd4-eff3-4ad6-9a35-a4d09abad634)

- Used following command to inspect protocol types:
  
      tshark -r task5_capture.pcap -T fields -e _ws.col.Protocol | sort | uniq -c
![image](https://github.com/user-attachments/assets/aad45b1f-b9fb-40d7-9eeb-941d161b0acd)

- Filter Only HTTP Traffic:
 
       tshark -r task5_capture.pcap -Y "http"
  
  ![image](https://github.com/user-attachments/assets/ffe9596c-6d9c-4a61-8998-f6981ab0e5e8)

- Show Source and Destination IPs with Protocol

      tshark -r task5_capture.pcap -T fields -e ip.src -e ip.dst -e _ws.col.Protocol
  ![image](https://github.com/user-attachments/assets/10eaaff2-69f7-42a6-a84b-8edf4173ed43)

> #### 🧾Summary of Findings and Packet Details
During the capture session, various packets were observed using the tshark tool while generating traffic through command-line utilities `ping`, `dig`, and `curl`. The [.pcap](https://github.com/0xV1RU/Elevate_lab_intern/blob/main/task-5/t5_capture.pcap) file contains clear evidence of different network protocols interacting over the internet.

> **✅ Identified Protocols:**

    8 ARP
    236 DNS
      2 HTTP
     22 ICMPv6
     10 IGMPv3
      1 IPv4
      4 LLMNR
      8 MDNS
      2 NTP
     42 OCSP
    168 QUIC
    2297 TCP
      1 TLSv1
    114 TLSv1.2
    1242 TLSv1.3

