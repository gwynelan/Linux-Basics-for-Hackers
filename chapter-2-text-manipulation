# Chapter 2: Text Manipulation

## Overview

Text manipulation is a fundamental skill in Linux, especially for cybersecurity professionals. This chapter covers the essential tools and techniques to view, search, modify, and analyze text files.

---

## 1. Viewing Text Files

Linux provides several commands to display the contents of text files in various formats.

### Commands:
- **`cat`**: Concatenates and displays file content.
- **`less`**: Opens a file for viewing one screen at a time.
- **`more`**: Similar to `less` but less advanced.
- **`head`**: Displays the first few lines of a file.
- **`tail`**: Displays the last few lines of a file.

### Examples:
```bash
cat file.txt          # Display entire file
less file.txt         # View file with scrolling
head -n 5 file.txt    # View first 5 lines
tail -n 5 file.txt    # View last 5 lines
```

---

## 2. Searching Text Files

### `grep`: Global Regular Expression Print
- Searches for patterns in text files.

### Syntax:
```bash
grep [options] 'pattern' file
```

### Examples:
- Search for "error" in a log file:
  ```bash
  grep 'error' /var/log/syslog
  ```
- Perform a case-insensitive search:
  ```bash
  grep -i 'error' file.txt
  ```
- Search recursively in directories:
  ```bash
  grep -r 'error' /path/to/directory
  ```

---

## 3. Modifying Text Files

### `sed`: Stream Editor
- Used for finding, replacing, and transforming text in a file.

### Syntax:
```bash
sed 's/find/replace/g' file
```

### Examples:
- Replace "foo" with "bar" in a file:
  ```bash
  sed 's/foo/bar/g' file.txt
  ```
- Delete lines containing a pattern:
  ```bash
  sed '/pattern/d' file.txt
  ```

### `awk`: Pattern Scanning and Processing
- Processes text files and extracts data based on patterns.

### Syntax:
```bash
awk '/pattern/ {action}' file
```

### Examples:
- Print the second column of a file:
  ```bash
  awk '{print $2}' file.txt
  ```
- Filter lines containing "error":
  ```bash
  awk '/error/' file.txt
  ```

---

## 4. Combining Commands

Linux allows you to combine commands for complex operations.

### `|`: Pipe Operator
- Sends the output of one command as input to another.

### Examples:
- Count lines containing "error":
  ```bash
  grep 'error' file.txt | wc -l
  ```
- Display the top 5 most frequent words in a file:
  ```bash
  cat file.txt | tr ' ' '\n' | sort | uniq -c | sort -nr | head -5
  ```

---

## Summary

By the end of this chapter, you should be able to:
- View text files using various tools.
- Search files for patterns with `grep`.
- Modify text with `sed` and `awk`.
- Combine commands for advanced text processing.

### Next Steps:
- Move to [Chapter 3: Analyzing and Managing Networks](#) to learn about network configuration and monitoring in Linux.

---

### Exercises

1. View the first 10 lines of `/etc/passwd`.
2. Search for all lines containing "root" in `/etc/passwd`.
3. Replace "bash" with "sh" in a copy of `/etc/passwd`.
4. Count the number of lines in `/var/log/syslog` containing "error".
5. Extract and display the third column of a CSV file using `awk`. 

