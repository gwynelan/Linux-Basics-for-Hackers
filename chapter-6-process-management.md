# Chapter 6: Process Management

## Overview

In Linux, processes are instances of running programs. Process management is essential for monitoring system performance, debugging, and ensuring the stability of the operating system. This chapter covers the tools and commands for viewing, managing, and controlling processes.

---

## 1. Understanding Linux Processes

### Key Concepts:
- **Process ID (PID)**: A unique identifier assigned to each process.
- **Parent Process ID (PPID)**: The ID of the process that created the current process.
- **Foreground Processes**: Processes that run interactively in the terminal.
- **Background Processes**: Processes that run without user interaction.
- **Daemon**: A background service typically started at boot time.

### Process States:
- **Running**: The process is currently executing.
- **Sleeping**: The process is waiting for a resource.
- **Stopped**: The process has been stopped by a signal.
- **Zombie**: The process has completed but is not yet removed by its parent.

---

## 2. Viewing Processes

### `ps`: Process Snapshot
- Displays information about running processes.

#### Examples:
```bash
ps aux                # Show all processes with detailed information
ps -ef                # Show all processes in full format
```

### `top`: Real-Time Process Monitoring
- Interactive tool for viewing and managing processes in real-time.

#### Usage:
```bash
top
```
- **Common Keys in `top`:**
  - `q`: Quit
  - `k`: Kill a process
  - `r`: Renice a process

### `htop`: Enhanced Process Viewer
- Provides a user-friendly interface for process management.

#### Installation:
```bash
sudo apt install htop
```

#### Usage:
```bash
htop
```

---

## 3. Managing Processes

### `kill`: Terminate a Process
- Sends a signal to a process to terminate it.

#### Syntax:
```bash
kill [signal] PID
```

#### Examples:
- Terminate a process:
  ```bash
  kill 1234
  ```
- Forcefully kill a process:
  ```bash
  kill -9 1234
  ```

### `pkill`: Kill Processes by Name
- Terminates processes matching a pattern.

#### Example:
```bash
pkill firefox
```

### `jobs`: List Background Jobs
- Displays jobs started in the current session.

#### Example:
```bash
jobs
```

### `fg` and `bg`: Foreground and Background Processes
- **`fg`**: Bring a background process to the foreground.
- **`bg`**: Resume a stopped process in the background.

#### Example:
```bash
fg %1
bg %2
```

---

## 4. Prioritizing Processes

### `nice`: Set Process Priority
- Assigns a priority to a process when starting it.
- Priority ranges from `-20` (highest) to `19` (lowest).

#### Example:
```bash
nice -n 10 ./script.sh
```

### `renice`: Change Process Priority
- Adjusts the priority of a running process.

#### Example:
```bash
sudo renice -5 1234
```

---

## 5. Monitoring Resource Usage

### `vmstat`: Virtual Memory Statistics
- Provides an overview of system performance.

#### Example:
```bash
vmstat 2 5
```

### `iostat`: CPU and Disk I/O Statistics
- Displays CPU and I/O usage.

#### Example:
```bash
iostat
```

### `free`: Memory Usage
- Shows free and used memory.

#### Example:
```bash
free -h
```

---

## 6. Advanced Process Management

### `strace`: Trace System Calls
- Debugs a process by tracing its system calls and signals.

#### Example:
```bash
strace -p 1234
```

### `lsof`: List Open Files
- Shows files opened by processes.

#### Example:
```bash
lsof -p 1234
```

### `systemctl`: Manage System Services
- Controls services and daemons.

#### Examples:
- Start a service:
  ```bash
  sudo systemctl start apache2
  ```
- Stop a service:
  ```bash
  sudo systemctl stop apache2
  ```
- Check service status:
  ```bash
  sudo systemctl status apache2
  ```

---

## Summary

By the end of this chapter, you should be able to:
- View and monitor processes using `ps`, `top`, and `htop`.
- Manage processes with `kill`, `pkill`, `fg`, and `bg`.
- Adjust process priorities using `nice` and `renice`.
- Debug and analyze processes with `strace` and `lsof`.

### Next Steps:
- Move to [Chapter 7: Managing User Environment Variables](chapter-7-managing-user-environment-variables.md) to learn about customizing the user environment in Linux.

---

### Exercises

1. List all processes running on your system and identify their PIDs.
2. Start a process in the background and bring it to the foreground using `fg`.
3. Change the priority of a running process using `renice`.
4. Use `strace` to debug a simple script and analyze its system calls.
5. Monitor memory and CPU usage on your system using `vmstat` and `iostat`.
