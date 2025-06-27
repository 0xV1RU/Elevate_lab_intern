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
> ##### *Select Rule Type*
Choose what you want to apply the rule to:
- `Program` – to allow/block a specific app.
- `Port` – to allow/block a specific port (like 80, 443).
- `Predefined` – select a Windows service.
- `Custom` – full manual configuration.
>> Click `Next`
> ##### *Define Details*
- For `Program`: Browse and select `.exe` file
- For `Port`: Select `TCP` or `UDP` → enter port number(like-23)
> ##### *Action*
Choose what to do when the rule matches:
- Allow the connection.
- Block the connection.
- Allow only if it is secure (advanced).
> ##### *Profile*
Select when the rule applies:
- Domain (corporate network)
- Private (home network)
- Public (public Wi-Fi, etc.)
> ##### *Name the Rule*
- Give a meaningful Name and optionally Description
- Click `Finish`
  
✅ Your firewall rule is now created and active.

### Tested the Rule
- Tried `telnet localhost 23` — Connection failed (blocked)
- Confirmed firewall rule is active and working
