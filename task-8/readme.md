# Task 8: VPN Setup and Privacy Analysis Report
## Objective:
To gain hands-on experience using a VPN and understand its role in privacy and secure communication.

## Tools Used:
- VPN Client: ProtonVPN (Free Tier)
- Website to Verify IP: https://whatismyipaddress.com
- Test Site: https://example.com 
- OS Used: Linux

## Steps Followed:
> **Signed Up on ProtonVPN:**

- Created a free account from https://protonvpn.com

> **Installed ProtonVPN Client:**

- Downloaded the official client for Linux.

      wget https://repo.protonvpn.com/debian/dists/stable/main/binary-all/protonvpn-stable-release_1.0.8_all.deb
      sudo dpkg -i ./protonvpn-stable-release_1.0.8_all.deb
      echo "0b14e71586b22e498eb20926c48c7b434b751149b1f2af9902ef1cfe6b03e180 protonvpn-stable-release_1.0.8_all.deb" | sha256sum --check -
      sudo apt install proton-vpn-gnome-desktop
      sudo apt install libayatana-appindicator3-1 gir1.2-ayatanaappindicator3-0.1 gnome-shell-extension-appindicator
> **Installed successfully.**

- Connected to VPN Server:
- Chose nearest free server.
- Connection status: ✅ Connected Successfully.

> **Verified IP Address Change:**

- Visited https://whatismyipaddress.com
- Original IP: (screenshot before connection)
- VPN IP: (screenshot after connection)

> **Tested Encrypted Browsing:**

- Visited example.com (or any HTTPS site).
- Browsing worked fine under VPN.

> **Disconnected VPN and Re-Checked:**

- Browsing speed without VPN: (Mention if faster/slower)
- IP address returned to normal.

## VPN Encryption & Privacy Research:
- VPN Encryption: VPNs encrypt your internet traffic using protocols like OpenVPN or WireGuard to prevent eavesdropping.
- Tunneling Protocols: Used for creating secure “tunnels” between user and VPN server.
- Common Protocols: OpenVPN, IKEv2, WireGuard.
