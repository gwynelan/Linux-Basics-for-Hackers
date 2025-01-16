# Chapter 1: Getting Started with the Basics

## Overview

In this chapter, we focus on the essentials of Linux that every beginner needs to understand. You will learn how to:

1. Install Kali Linux on VirtualBox.
2. Use fundamental Linux commands.
3. Navigate the Linux filesystem.
4. Access manual pages and built-in help commands.

---

## 1. Installing Kali Linux

### Steps:
1. **Download VirtualBox**:
   - Visit [VirtualBox's official website](https://www.virtualbox.org/).
   - Download and install VirtualBox for your operating system.

2. **Download Kali Linux**:
   - Visit [Kali Linux Downloads](https://www.kali.org/get-kali/).
   - Choose the appropriate ISO image for VirtualBox.

3. **Create a New Virtual Machine**:
   - Open VirtualBox and click `New`.
   - Provide a name (e.g., "Kali Linux") and select `Linux` as the type.
   - Allocate at least 2GB of RAM and 20GB of storage.

4. **Attach ISO Image**:
   - Go to `Settings > Storage` and attach the downloaded Kali ISO file as a virtual optical disk.

5. **Start Installation**:
   - Boot the virtual machine and follow the on-screen instructions to complete the installation.

---

## 2. Basic Linux Commands

### Common Commands:

| Command       | Description                                |
|---------------|--------------------------------------------|
| `pwd`         | Prints the current working directory       |
| `ls`          | Lists files and directories                |
| `cd <path>`   | Changes the current directory              |
| `whoami`      | Displays the current logged-in user        |
| `man <cmd>`   | Displays the manual for a command          |
| `mkdir <name>`| Creates a new directory                    |
| `rm <file>`   | Deletes a file                            |
| `touch <file>`| Creates an empty file                      |

### Examples:

- **View current directory:**
  ```bash
  pwd
  ```

- **List all files (including hidden ones):**
  ```bash
  ls -a
  ```

- **Navigate to a directory:**
  ```bash
  cd /home
  ```

- **Create and delete files:**
  ```bash
  touch example.txt
  rm example.txt
  ```

---

## 3. Navigating the Linux Filesystem

The Linux filesystem is hierarchical, starting at the root directory `/`.

### Common Directories:
- `/home`: User home directories.
- `/etc`: Configuration files.
- `/var`: Logs and variable data.
- `/bin`: Essential binaries.
- `/usr`: User-installed applications.

### Useful Commands:
- **View directory contents:**
  ```bash
  ls -l /etc
  ```

- **Check disk usage:**
  ```bash
  df -h
  ```

---

## 4. Using Manual Pages and Help

Linux includes comprehensive documentation for commands. Use the following to access it:

### Commands:
- **Manual pages:**
  ```bash
  man <command>
  ```
- **Help option:**
  ```bash
  <command> --help
  ```

### Example:
- View the manual for `ls`:
  ```bash
  man ls
  ```
- Get a summary of `ls` options:
  ```bash
  ls --help
  ```

---

## Summary

By the end of this chapter, you should be able to:
- Set up a Linux environment using VirtualBox.
- Execute basic Linux commands for everyday tasks.
- Navigate and understand the Linux filesystem.
- Use manual pages to explore advanced options for commands.

### Next Steps:
- Move to [Chapter 2: Text Manipulation](chapter-2-text-manipulation) to learn about processing and analyzing text files in Linux.

---

### Exercises

1. Create a directory named `practice` in your home directory.
2. Create an empty file named `notes.txt` in the `practice` directory.
3. Navigate to `/etc` and list all files starting with `a`.
4. Find the manual for the `grep` command and identify its `-i` option.
