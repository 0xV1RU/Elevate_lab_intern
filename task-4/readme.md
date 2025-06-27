## 🔷Task 4: Firewall Configuration and Testing
### 🎯Objective
> To configure and test basic firewall rules on Windows (or Linux) using Windows Defender Firewall or UFW to allow/block specific traffic based on ports.
### 🔷Tools Used
- Windows Defender Firewall or UFW on Linux
- Terminal / GUI
- Telnet (for testing port 23)
- GitHub (for documentation)

### Open Firewall Configuration Tool
> #### *Open Firewall with Advanced Security*
Press `⊞ + R`
Type `wf.msc` → Press `⏎`
> Press (⊞) + R, then type `wf.msc` and press ⏎ to open Windows Defender Firewall with Advanced Security.
> Click on Inbound Rules shown in the top-left corner of the screen.
![image](https://github.com/user-attachments/assets/fd4b3192-b447-401d-a827-a35705ca05ca)
![image](https://github.com/user-attachments/assets/522f445d-5929-4b9a-96dd-7027f14419ee)

### Add a rule to block inbound traffic
> ##### *Choose Rule Type*
- In the left panel, click on `Inbound Rules` (for incoming connections) or `Outbound Rules` (for outgoing).
- In the right panel, click on "`New Rule...`"
![inbound_rules](https://github.com/user-attachments/assets/b9c20c98-aab1-49d0-9b49-1964d3c584af)
![new inbound rule](https://github.com/user-attachments/assets/aa1013cd-2b04-444f-ae1b-9be4e74ec861)

> ##### *Select Rule Type*
Choose what you want to apply the rule to:
- `Program` – to allow/block a specific app.
- `Port` – to allow/block a specific port (like 80, 443).
- `Predefined` – select a Windows service.
- `Custom` – full manual configuration.
>> Click `Next`
>![rule type](https://github.com/user-attachments/assets/3fb27b18-2c13-4a0c-815f-5fec726dea65)

> ##### *Define Details*
- For `Program`: Browse and select `.exe` file
- For `Port`: Select `TCP` or `UDP` → enter port number(like-23)
- ![protocol and ports](https://github.com/user-attachments/assets/bd7d557c-0d7c-4a2f-9e10-b40703177425)

> ##### *Action*
Choose what to do when the rule matches:
- Allow the connection.
- Block the connection.
- Allow only if it is secure (advanced).
- ![action ](https://github.com/user-attachments/assets/d5e3cca0-d295-48a2-a6fc-499a7d5982b8)

> ##### *Profile*
Select when the rule applies:
- Domain (corporate network)
- Private (home network)
- Public (public Wi-Fi, etc.)
- ![profile](https://github.com/user-attachments/assets/8e2fdfa3-5314-461c-86b0-45b8bcd336c9)

> ##### *Name the Rule*
- Give a meaningful Name and optionally Description
- Click `Finish`
- ✅ Your firewall rule is now created and active.
- ![name assign](https://github.com/user-attachments/assets/97b7fd5e-a816-484e-bb04-8e2f0073d56a)

  

### Tested the Rule
- Tried `telnet localhost 23` — Connection failed (blocked)
- Confirmed firewall rule is active and working

### Removed the Test Rule
Navigated back to Inbound Rules, Located “`Block Telnet`” → Right-click → Delete

### (Linux_only) Allowed SSH (Port-22)
```bash
`sudo ufw enable`
`sudo ufw allow 22/tcp


