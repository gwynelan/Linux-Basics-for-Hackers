# Chapter 10: Filesystem and Storage Device Management

## Overview

Managing the filesystem and storage devices is a critical part of Linux administration. This chapter covers how to view, configure, and maintain storage devices, partitions, and filesystems effectively.

---

## 1. Understanding Filesystems

### Common Filesystem Types:
- **ext4**: Default filesystem for most Linux distributions.
- **xfs**: High-performance journaling filesystem.
- **btrfs**: Advanced filesystem with features like snapshots and compression.
- **ntfs**: Commonly used on Windows systems, supported in Linux for compatibility.
- **vfat**: Used for USB drives and older Windows systems.

---

## 2. Viewing Filesystem Information

### `lsblk`: List Block Devices
- Displays information about block devices such as disks and partitions.

#### Example:
```bash
lsblk
```

### `df`: Disk Usage
- Shows disk space usage for mounted filesystems.

#### Example:
```bash
df -h
```

### `du`: Disk Usage for Files and Directories
- Displays the space used by files and directories.

#### Example:
```bash
du -sh /path/to/directory
```

### `mount` and `umount`
- Mount and unmount filesystems.

#### Examples:
- Mount a device:
  ```bash
  sudo mount /dev/sdX1 /mnt
  ```
- Unmount a device:
  ```bash
  sudo umount /mnt
  ```

---

## 3. Managing Partitions

### `fdisk`: Partition Management Tool
- Interactive utility for creating and managing partitions.

#### Example:
1. Open the disk for partitioning:
   ```bash
   sudo fdisk /dev/sdX
   ```
2. Common commands inside `fdisk`:
   - `n`: Create a new partition.
   - `d`: Delete a partition.
   - `p`: Print the partition table.
   - `w`: Write changes and exit.

### `parted`: Advanced Partition Tool
- Used for creating and managing GPT and MBR partitions.

#### Example:
```bash
sudo parted /dev/sdX
```

### `lsblk` with Partition Information:
```bash
lsblk -f
```

---

## 4. Filesystem Creation and Management

### `mkfs`: Create a Filesystem
- Used to format partitions with a specific filesystem.

#### Examples:
- Create an ext4 filesystem:
  ```bash
  sudo mkfs.ext4 /dev/sdX1
  ```
- Create an xfs filesystem:
  ```bash
  sudo mkfs.xfs /dev/sdX1
  ```

### `fsck`: Check and Repair Filesystems
- Used to identify and fix filesystem errors.

#### Example:
```bash
sudo fsck /dev/sdX1
```

### `tune2fs`: Adjust Filesystem Parameters
- Modify parameters for ext-based filesystems.

#### Example:
```bash
sudo tune2fs -c 10 /dev/sdX1
```

---

## 5. Swap Management

### Create a Swap Partition:
1. Create the partition using `fdisk` or `parted`.
2. Format the partition as swap:
   ```bash
   sudo mkswap /dev/sdX2
   ```
3. Enable the swap partition:
   ```bash
   sudo swapon /dev/sdX2
   ```
4. Make the swap persistent by adding it to `/etc/fstab`:
   ```
   /dev/sdX2 none swap sw 0 0
   ```

### Check Swap Usage:
```bash
free -h
```

---

## 6. Mounting Filesystems Automatically

### `/etc/fstab`: Filesystem Table
- Defines how and where filesystems are mounted automatically.

#### Example Entry:
```
/dev/sdX1 /mnt ext4 defaults 0 2
```

### Testing `/etc/fstab` Changes:
- After modifying `/etc/fstab`, test the configuration:
  ```bash
  sudo mount -a
  ```

---

## 7. Disk Quotas

### Enable Disk Quotas:
1. Add quota options to `/etc/fstab`:
   ```
   /dev/sdX1 /mnt ext4 defaults,usrquota,grpquota 0 2
   ```
2. Remount the filesystem:
   ```bash
   sudo mount -o remount /mnt
   ```
3. Create the quota database:
   ```bash
   sudo quotacheck -cum /mnt
   sudo quotaon /mnt
   ```

### Set Quotas for a User:
```bash
sudo edquota -u username
```

---

## Summary

By the end of this chapter, you should be able to:
- View and analyze storage devices and filesystems.
- Manage partitions and format them with various filesystems.
- Mount, unmount, and configure filesystems using `/etc/fstab`.
- Create and manage swap partitions and disk quotas.

### Next Steps:
- Move to [Chapter 11: The Logging System](chapter-11-the-logging-system.md) to learn about managing logs and monitoring system activities in Linux.

---

### Exercises

1. Create a new ext4 partition, format it, and mount it to `/mnt/newdrive`.
2. View the disk space usage of `/home` using `du` and `df`.
3. Check and repair an ext4 filesystem using `fsck`.
4. Add a swap partition and verify it is active using `free`.
5. Configure a user quota on a mounted filesystem and test it.
