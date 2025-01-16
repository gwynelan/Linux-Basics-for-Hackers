# Linux Basics for Hackers - Comprehensive Guide

Welcome to the **Linux Basics for Hackers** repository! This guide is based on the book "Linux Basics for Hackers" by OccupyTheWeb, which focuses on networking, scripting, and security using Kali Linux. It provides a structured approach for both beginners and advanced users.

---

## 📌 Repository Name: **Linux-Basics-for-Hackers**

---

## 📚 Table of Contents

1. [Introduction](#introduction)
2. [Chapter 1: Getting Started with the Basics](#chapter-1-getting-started-with-the-basics)
3. [Chapter 2: Text Manipulation](#chapter-2-text-manipulation)
4. [Chapter 3: Analyzing and Managing Networks](#chapter-3-analyzing-and-managing-networks)
5. [Chapter 4: Adding and Removing Software](#chapter-4-adding-and-removing-software)
6. [Chapter 5: Controlling File and Directory Permissions](#chapter-5-controlling-file-and-directory-permissions)
7. [Chapter 6: Process Management](#chapter-6-process-management)
8. [Chapter 7: Managing User Environment Variables](#chapter-7-managing-user-environment-variables)
9. [Chapter 8: Bash Scripting](#chapter-8-bash-scripting)
10. [Chapter 9: Compressing and Archiving](#chapter-9-compressing-and-archiving)
11. [Chapter 10: Filesystem and Storage Device Management](#chapter-10-filesystem-and-storage-device-management)
12. [Chapter 11: The Logging System](#chapter-11-the-logging-system)
13. [Chapter 12: Using and Abusing Services](#chapter-12-using-and-abusing-services)
14. [Chapter 13: Becoming Secure and Anonymous](#chapter-13-becoming-secure-and-anonymous)
15. [Chapter 14: Understanding and Inspecting Wireless Networks](#chapter-14-understanding-and-inspecting-wireless-networks)
16. [Chapter 15: Managing the Linux Kernel and Loadable Kernel Modules](#chapter-15-managing-the-linux-kernel-and-loadable-kernel-modules)
17. [Chapter 16: Automating Tasks with Job Scheduling](#chapter-16-automating-tasks-with-job-scheduling)
18. [Chapter 17: Python Scripting Basics for Hackers](#chapter-17-python-scripting-basics-for-hackers)
19. [Exercises](#exercises)

---

## 🐧 Introduction

This book introduces Linux concepts for aspiring hackers and cybersecurity professionals using Kali Linux. The key focus areas include:

- Installing and configuring Linux systems.
- Networking basics and advanced topics.
- Scripting with Bash and Python.
- Security and anonymity techniques.
- Practical hacking tools and techniques.

---

## Chapter 1: Getting Started with the Basics

### Key Topics:
- Installing Kali Linux on VirtualBox.
- Basic Linux commands (`pwd`, `ls`, `cd`, `whoami`).
- Navigating the Linux filesystem.
- Using manual pages (`man`) and help commands.

#### Important Commands:
```bash
pwd        # Print current directory
ls         # List files and directories
cd <path>  # Change directory
man <cmd>  # Show manual for a command
```

---

## Chapter 2: Text Manipulation

### Key Topics:
- Viewing and modifying text files.
- Using `grep` for pattern matching.
- Combining commands like `head`, `tail`, `nl`, and `sed` for text processing.

#### Example:
```bash
cat file.txt | grep "error" > error_log.txt
```

---

## Chapter 3: Analyzing and Managing Networks

### Key Topics:
- Using `ifconfig` and `iwconfig` for network configuration.
- Changing network parameters like IP and MAC addresses.
- Inspecting DNS settings with `dig`.

#### Example:
```bash
ifconfig eth0 192.168.1.10 netmask 255.255.255.0
```

---

## Chapter 4: Adding and Removing Software

### Key Topics:
- Using package managers (`apt`, `yum`) to install, update, and remove software.
- Adding repositories to the system.

#### Example:
```bash
sudo apt update && sudo apt install nmap
```

---

## Chapter 5: Controlling File and Directory Permissions

### Key Topics:
- File and directory permissions (`chmod`, `chown`).
- Special permissions like SUID, SGID, and sticky bit.

#### Example:
```bash
chmod 755 script.sh
chown user:group file.txt
```

---

## Chapter 6: Process Management

### Key Topics:
- Viewing and managing processes (`ps`, `top`, `htop`).
- Adjusting process priorities with `nice` and `renice`.

#### Example:
```bash
ps aux | grep apache
kill -9 <PID>
```

---

## Chapter 7: Managing User Environment Variables

### Key Topics:
- Setting and modifying environment variables (`PATH`, `HOME`).
- Making changes permanent in shell configuration files.

#### Example:
```bash
export PATH=$PATH:/custom/path
```

---

## Chapter 8: Bash Scripting

### Key Topics:
- Writing basic Bash scripts.
- Automating tasks with loops and conditionals.
- Creating tools like a simple port scanner.

#### Example:
```bash
#!/bin/bash
for ip in {1..255}; do
  ping -c 1 192.168.1.$ip
done
```

---

## Chapter 9: Compressing and Archiving

### Key Topics:
- Using `tar`, `gzip`, and `bzip2` for archiving and compressing files.

#### Example:
```bash
tar -czvf archive.tar.gz directory_name
```

---

## Chapter 10: Filesystem and Storage Device Management

### Key Topics:
- Managing storage devices and partitions (`lsblk`, `mount`, `umount`).
- Checking filesystem errors with `fsck`.

#### Example:
```bash
mount /dev/sda1 /mnt
```

---

## Chapter 11: The Logging System

### Key Topics:
- Understanding system logs (`/var/log/`).
- Configuring `rsyslog` for centralized logging.

---

## Chapter 12: Using and Abusing Services

### Key Topics:
- Configuring services like Apache and MySQL.
- Exploiting misconfigurations for testing.

---

## Chapter 13: Becoming Secure and Anonymous

### Key Topics:
- Using Tor, VPNs, and proxy chains.
- Configuring encrypted email and secure communications.

---

## Chapter 14: Understanding and Inspecting Wireless Networks

### Key Topics:
- Monitoring wireless networks with tools like `airmon-ng` and `airodump-ng`.
- Capturing packets for analysis.

---

## Chapter 15: Managing the Linux Kernel and Loadable Kernel Modules

### Key Topics:
- Understanding the Linux kernel architecture.
- Loading and unloading kernel modules (`modprobe`, `lsmod`).

---

## Chapter 16: Automating Tasks with Job Scheduling

### Key Topics:
- Using `cron` and `at` for task scheduling.

#### Example:
```bash
crontab -e
```

---

## Chapter 17: Python Scripting Basics for Hackers

### Key Topics:
- Writing Python scripts for automation.
- Using libraries like `socket` and `os` for hacking tools.

#### Example:
```python
import socket
s = socket.socket()
s.connect(("192.168.1.10", 80))
```

---

## Exercises

Each chapter includes practical exercises to reinforce learning. Complete these to gain hands-on experience with Linux and cybersecurity tools.

---

## 🤝 Contributing

Contributions are welcome! Fork this repository and submit your improvements via pull requests.

---

## 📜 License

This project is licensed under the MIT License.
