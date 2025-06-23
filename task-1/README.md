# 🛡️ Task-1: Network Reconnaissance using Nmap

## 🎯 Objective
Perform basic network scanning using Nmap to discover active devices, open ports, and identify potential risks.

## 1.finding local IP range

```ifconfig , ip a```

	eth0: flags= 4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        		inet 192.168.228.129  netmask 255.255.255.0  broadcast 192.168.228.255
		        inet6 fe80::20c:29ff:fe12:e534  prefixlen 64  scopeid 0x20<link>
		        ether 00:0c:29:12:e5:34  txqueuelen 1000  (Ethernet)
	        	RX packets 76  bytes 5483 (5.3 KiB)
		        RX errors 0  dropped 0  overruns 0  frame 0
		        TX packets 46  bytes 5718 (5.5 KiB)
	        	TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
		        device interrupt 19  base 0x2000  

	lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
		        inet 127.0.0.1  netmask 255.0.0.0
		        inet6 ::1  prefixlen 128  scopeid 0x10<host>
		        loop  txqueuelen 1000  (Local Loopback)
		        RX packets 8  bytes 480 (480.0 B)
		        RX errors 0  dropped 0  overruns 0  frame 0
		        TX packets 8  bytes 480 (480.0 B)
		        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

## 2.finding active machines

	sudo nmap -sn 192.168.228.0/24 -oN local_scan.txt 
		Starting Nmap 7.95 ( https://nmap.org ) at 2025-06-23 15:41 IST
		Nmap scan report for 192.168.228.73
		Host is up (0.0022s latency).
		MAC Address: 1A:F1:CC:80:01:F3 (Unknown)
		Nmap scan report for 192.168.228.210
		Host is up (0.0077s latency).
		MAC Address: 4E:B0:1A:6D:57:8E (Unknown)
		Nmap scan report for 192.168.228.129
		Host is up.
		Nmap done: 256 IP addresses (3 hosts up) scanned in 3.01 seconds


## 3.finding open ports

	Command : sudo nmap -p- 192.168.228.73  -oN port_scan.txt        
		Starting Nmap 7.95 ( https://nmap.org ) at 2025-06-23 15:46 IST
		Stats: 0:00:03 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan
		SYN Stealth Scan Timing: About 0.72% done
		Nmap scan report for 192.168.228.73
		Host is up (0.00090s latency).
		Not shown: 65530 filtered tcp ports (no-response)
		PORT      STATE SERVICE
		135/tcp   open  msrpc
		139/tcp   open  netbios-ssn
		445/tcp   open  microsoft-ds
		2179/tcp  open  vmrdp
		49669/tcp open  unknown
		MAC Address: 1A:F1:CC:80:01:F3 (Unknown)

		Nmap done: 1 IP address (1 host up) scanned in 124.10 seconds

## 4.Identify potential security risks from open ports.
	
	🔴 135/tcp (msrpc - Microsoft Remote Procedure Call)
		Use: Handles inter-process communication.
		Risks: Often targeted for privilege escalation.
		       Vulnerable to DCE-RPC based attacks.
		Famous Exploits: MS03-026 (Blaster worm), CVE-2003-0352.
		Mitigation: Block from external access via firewall.

	🔴 139/tcp (NetBIOS Session Service)
		Use: Used for Windows file/printer sharing in older systems.
		Risks:  Information Disclosure via null session.
			Attacker can enumerate usernames, shares, policies.
		Mitigation: Disable NetBIOS if not needed; use SMB v2+.

	🔴 445/tcp (Microsoft-DS / SMB)
		Use: Windows file sharing and domain services.
		Risks:  Critical vulnerabilities (e.g. EternalBlue - CVE-2017-0144).
			Ransomware often exploits SMB (e.g. WannaCry).
		Mitigation: Disable SMBv1.
			    Use strong passwords.
			    Keep OS patched.

	🟠 2179/tcp (VMRDP - Remote Desktop for Hyper-V VMs)
		Use: Remote Desktop Protocol for VMs.
		Risks:  If exposed, attacker can brute-force login or exploit RDP vulns.
		Mitigation: Use RDP over VPN only. Enable 2FA, lockout policies.

	🟡 49669/tcp (Unknown High Port - Likely Dynamic RPC)
		Use: Random high port used for Dynamic RPC connections.
		Risks:  Used in combo with port 135/445 by RPC services.
			Could be misused by malware.
		Mitigation: Allow only trusted internal access.



