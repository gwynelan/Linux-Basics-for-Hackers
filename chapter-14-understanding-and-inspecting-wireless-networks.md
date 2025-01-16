# Chapter 14: Understanding and Inspecting Wireless Networks

## Overview

Wireless networks are widely used but often vulnerable to attacks due to their inherent nature. Understanding wireless protocols, security mechanisms, and how to inspect wireless networks is crucial for maintaining network security. This chapter covers the tools and techniques to analyze and secure wireless networks.

---

## 1. Basics of Wireless Networking

### Key Concepts:
- **Wireless Standards**:
  - **802.11a/b/g/n/ac/ax**: Various IEEE wireless standards.
- **Frequencies**:
  - 2.4 GHz: Longer range, slower speeds.
  - 5 GHz: Shorter range, higher speeds.
- **SSID**: Network name broadcasted by the access point.
- **BSSID**: Unique MAC address of the access point.

### Wireless Security Protocols:
- **WEP (Wired Equivalent Privacy)**: Weak and outdated.
- **WPA (Wi-Fi Protected Access)**: Improved but deprecated.
- **WPA2**: Common and secure (when used with AES encryption).
- **WPA3**: Latest standard with enhanced security.

---

## 2. Scanning Wireless Networks

### `iwconfig`: Configure Wireless Interfaces
- Displays and configures wireless network interfaces.

#### Example:
```bash
iwconfig
```

### `nmcli`: Network Manager Command-Line Interface
- Manage network connections.

#### Examples:
- List available networks:
  ```bash
  nmcli dev wifi list
  ```
- Connect to a network:
  ```bash
  nmcli dev wifi connect "SSID" password "password"
  ```

### `airmon-ng`: Enable Monitor Mode
- Part of the Aircrack-ng suite, used for wireless monitoring and testing.

#### Example:
```bash
sudo airmon-ng start wlan0
```

---

## 3. Capturing Packets

### `airodump-ng`: Packet Capture Tool
- Captures wireless packets and identifies nearby networks.

#### Example:
```bash
sudo airodump-ng wlan0mon
```

### Options:
- Capture packets for a specific network:
  ```bash
  sudo airodump-ng --bssid <BSSID> --channel <channel> -w capture wlan0mon
  ```

---

## 4. Analyzing Wireless Traffic

### `wireshark`: Network Traffic Analyzer
- GUI tool for analyzing captured packets.

#### Installation:
```bash
sudo apt install wireshark
```

#### Usage:
- Open Wireshark and select the wireless interface in monitor mode.
- Apply filters (e.g., `wlan.fc.type_subtype == 0x08` to show beacon frames).

### `tcpdump`: Command-Line Packet Analyzer
- Analyze network traffic from the terminal.

#### Example:
```bash
sudo tcpdump -i wlan0mon -w capture.pcap
```

---

## 5. Cracking Wireless Networks

### Aircrack-ng Suite:
- A set of tools for wireless auditing and penetration testing.

#### Steps:
1. Capture the handshake:
   ```bash
   sudo airodump-ng --bssid <BSSID> --channel <channel> -w handshake wlan0mon
   ```
2. Crack the password:
   ```bash
   aircrack-ng -w wordlist.txt -b <BSSID> handshake-01.cap
   ```

> **Note**: Use these tools responsibly and only with explicit permission.

---

## 6. Securing Wireless Networks

### Best Practices:
- **Use Strong Encryption**: Enable WPA3 or WPA2 with AES.
- **Disable WPS**: Prevent brute force attacks on PIN-based setups.
- **Change Default SSID and Password**: Use unique and strong credentials.
- **Enable MAC Filtering**: Restrict access to specific devices.
- **Reduce Signal Strength**: Prevent access from outside your intended area.

### Monitor Network Activity:
- Use tools like `arp-scan` to detect unauthorized devices:
  ```bash
  sudo arp-scan --localnet
  ```

---

## Summary

By the end of this chapter, you should be able to:
- Understand wireless networking concepts and security protocols.
- Scan and capture wireless traffic using tools like `airodump-ng` and `wireshark`.
- Analyze and secure wireless networks using best practices.

### Next Steps:
- Move to [Chapter 15: Managing the Linux Kernel and Loadable Kernel Modules](chapter-15-managing-the-linux-kernel-and-loadable-kernel-modules.md) to learn about kernel management and customization.

---

### Exercises

1. Use `iwconfig` to display your wireless interface settings.
2. Capture packets for a specific network using `airodump-ng` and analyze them in Wireshark.
3. Test the signal strength of nearby networks using `nmcli`.
4. Create a secure wireless network configuration with WPA2 and MAC filtering.
5. Use `tcpdump` to capture wireless traffic and apply filters to isolate specific frames.
