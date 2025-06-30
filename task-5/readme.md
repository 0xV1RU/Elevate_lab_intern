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




