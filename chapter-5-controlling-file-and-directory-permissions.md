# Chapter 5: Controlling File and Directory Permissions

## Overview

File and directory permissions are critical to securing a Linux system. This chapter explores how to view, modify, and manage permissions effectively, ensuring only authorized users can access sensitive data.

---

## 1. Understanding Linux Permissions

Linux permissions determine who can read, write, or execute files and directories. Permissions are represented as a string of 10 characters:

```bash
-rwxr-xr--
```

### Breakdown:
1. **First Character**:
   - `-` = Regular file
   - `d` = Directory
   - `l` = Symbolic link

2. **Next Nine Characters** (Grouped in threes):
   - `r` = Read (4)
   - `w` = Write (2)
   - `x` = Execute (1)

   **Example**:
   - `rwx` = Full permissions (4+2+1 = 7)
   - `r--` = Read-only (4)
   - `rw-` = Read and write (4+2 = 6)

### Types of Users:
- **Owner**: The user who created the file.
- **Group**: A collection of users who share access.
- **Others**: All other users on the system.

---

## 2. Viewing Permissions

### `ls -l`: List Files with Permissions

#### Example:
```bash
ls -l
```
Output:
```bash
-rw-r--r-- 1 user group 1024 Jan 1 12:34 file.txt
```

- `-rw-r--r--`: Permissions
- `1`: Number of hard links
- `user`: Owner
- `group`: Group
- `1024`: File size
- `Jan 1 12:34`: Last modified date
- `file.txt`: File name

---

## 3. Modifying Permissions

### `chmod`: Change File Mode
- Used to modify file or directory permissions.

#### Syntax:
```bash
chmod [options] mode file
```

#### Examples:
- Give full permissions to the owner:
  ```bash
  chmod u+rwx file.txt
  ```
- Remove write permission for the group:
  ```bash
  chmod g-w file.txt
  ```
- Set permissions using octal notation:
  ```bash
  chmod 755 file.txt
  ```

| Octal | Permission | Description      |
|-------|------------|------------------|
| 7     | `rwx`      | Full             |
| 6     | `rw-`      | Read and write   |
| 5     | `r-x`      | Read and execute |
| 4     | `r--`      | Read-only        |
| 0     | `---`      | No permissions   |

---

## 4. Changing Ownership

### `chown`: Change Ownership
- Modifies the owner and group of a file or directory.

#### Syntax:
```bash
chown [options] owner[:group] file
```

#### Examples:
- Change the owner:
  ```bash
  sudo chown user file.txt
  ```
- Change the owner and group:
  ```bash
  sudo chown user:group file.txt
  ```
- Recursively change ownership for a directory:
  ```bash
  sudo chown -R user:group /path/to/directory
  ```

### `chgrp`: Change Group Ownership
- Used specifically to change the group of a file.

#### Example:
```bash
sudo chgrp group file.txt
```

---

## 5. Special Permissions

### SUID (Set User ID):
- Executes a file with the permissions of the file owner.

#### Example:
```bash
chmod u+s file
```

### SGID (Set Group ID):
- Executes a file with the permissions of the file's group.

#### Example:
```bash
chmod g+s file
```

### Sticky Bit:
- Ensures only the file owner can delete files in a directory.

#### Example:
```bash
chmod +t /tmp
```

---

## 6. Advanced Permission Management

### `umask`: Default Permission Mask
- Defines default permissions for newly created files and directories.

#### Check Current `umask`:
```bash
umask
```

#### Set a New `umask`:
```bash
umask 022
```

### ACL (Access Control List):
- Provides fine-grained permissions for users and groups.

#### View ACL:
```bash
getfacl file
```

#### Set ACL:
```bash
setfacl -m u:user:rwx file
```

---

## Summary

By the end of this chapter, you should be able to:
- Understand Linux file and directory permissions.
- Modify permissions using `chmod`.
- Change ownership with `chown` and `chgrp`.
- Implement special permissions like SUID, SGID, and sticky bit.
- Utilize `umask` and ACLs for advanced permission management.

### Next Steps:
- Move to [Chapter 6: Process Management](chapter-6-process-management.md) to learn about managing and controlling processes in Linux.

---

### Exercises

1. List all files in `/var` with their permissions.
2. Create a file with `rw-r--r--` permissions and change its group ownership.
3. Add SUID to a script and verify its behavior.
4. Set ACL to grant a specific user write access to a file they don’t own.
5. Test sticky bit functionality in a shared directory.
