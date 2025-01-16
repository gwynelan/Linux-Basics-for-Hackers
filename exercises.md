# Exercises

## Overview

This chapter provides hands-on exercises to test and reinforce the concepts you have learned in the previous chapters. These tasks are designed to help you apply theoretical knowledge to practical scenarios, focusing on Linux basics, advanced scripting, and cybersecurity skills.

---

## 1. General Linux Commands

### Tasks:
1. Create a directory structure for a project:
   ```
   project/
   ├── src/
   ├── docs/
   ├── tests/
   ```
2. List all files in the `/etc` directory that contain the word "conf" in their name.
3. Find the largest 5 files in your home directory.
4. Create a tar archive of the `/var/log` directory and compress it using Gzip.

---

## 2. File Permissions

### Tasks:
1. Create a file `secure.txt` with `rw-r-----` permissions.
2. Add a sticky bit to a shared directory so that only file owners can delete their files.
3. Use ACL to grant a specific user write access to a file they don’t own.

---

## 3. Networking

### Tasks:
1. Use `ping` to check connectivity with an external server.
2. Capture network packets on a specific interface using `tcpdump` and analyze them in Wireshark.
3. Create a simple script that scans a range of IP addresses for open ports.

---

## 4. Bash Scripting

### Tasks:
1. Write a script to back up a directory to a specified location, appending the date to the archive’s name.
2. Automate cleaning up old log files (older than 7 days) in a specific directory.
3. Create a script to monitor CPU usage and alert if it exceeds 80%.

---

## 5. Python Scripting

### Tasks:
1. Create a Python script to encrypt and decrypt a file using the `cryptography` library.
2. Write a script to fetch and display the latest weather information from a public API.
3. Build a chat application using Python sockets for communication between two systems.

---

## 6. Security and Anonymity

### Tasks:
1. Configure a firewall using `ufw` to allow SSH traffic and block all other incoming connections.
2. Set up Tor for anonymous browsing and verify its functionality.
3. Monitor failed login attempts using `/var/log/auth.log` and write a summary report.

---

## 7. Kernel and Module Management

### Tasks:
1. List all loaded kernel modules and find their sizes.
2. Insert and remove a custom kernel module.
3. Enable IP forwarding using `sysctl` and verify its effect.

---

## 8. Automating Tasks

### Tasks:
1. Schedule a cron job to clean up temporary files every day at midnight.
2. Create a `systemd` timer to run a backup script weekly.
3. Use the `at` command to schedule a task to send an alert email in 1 hour.

---

## 9. Wireless Network Analysis

### Tasks:
1. Use `airodump-ng` to capture packets for a specific wireless network.
2. Test the signal strength of nearby networks using `nmcli`.
3. Secure your wireless router by disabling WPS and enabling WPA3.

---

## 10. Advanced Scenarios

### Tasks:
1. Rebuild the Linux kernel with a custom configuration and test it.
2. Develop a Python tool to log keystrokes (for educational purposes only).
3. Create a full penetration testing report for a virtual lab environment, including vulnerabilities found and mitigations applied.

---

## Summary

These exercises are designed to provide a mix of theoretical and practical challenges to strengthen your skills. By completing them, you will gain deeper insights into Linux system management, scripting, and cybersecurity practices.

Feel free to revisit previous chapters for reference while working on these tasks. 🚀
