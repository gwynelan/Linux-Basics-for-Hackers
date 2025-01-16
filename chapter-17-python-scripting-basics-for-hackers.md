# Chapter 17: Python Scripting Basics for Hackers

## Overview

Python is a versatile programming language that is widely used in cybersecurity for automation, penetration testing, and creating custom tools. This chapter introduces Python basics and demonstrates how to use it for hacking-related tasks.

---

## 1. Introduction to Python

### Key Features:
- Easy to learn and use.
- Extensive libraries for networking, cryptography, and data manipulation.
- Cross-platform compatibility.

### Installing Python:
- Most Linux distributions come with Python pre-installed. To check:
  ```bash
  python3 --version
  ```
- Install Python if not present:
  ```bash
  sudo apt install python3
  sudo apt install python3-pip
  ```

---

## 2. Writing and Running Python Scripts

### Writing a Script:
1. Create a file with the `.py` extension (e.g., `script.py`).
2. Write your Python code.

### Running a Script:
```bash
python3 script.py
```

### Example Script:
```python
#!/usr/bin/env python3

print("Hello, World!")
```

Make the script executable:
```bash
chmod +x script.py
./script.py
```

---

## 3. Python Basics

### Variables:
```python
name = "Hacker"
age = 25
print(f"Name: {name}, Age: {age}")
```

### Conditional Statements:
```python
if age > 18:
    print("Adult")
else:
    print("Minor")
```

### Loops:
```python
for i in range(5):
    print(i)

count = 0
while count < 5:
    print(count)
    count += 1
```

### Functions:
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Hacker"))
```

---

## 4. Networking with Python

### Using `socket`:
- Create a simple TCP client:
```python
import socket

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client.connect(("127.0.0.1", 8080))
client.send(b"Hello, Server!")
data = client.recv(1024)
print(f"Received: {data.decode()}")
client.close()
```

- Create a simple TCP server:
```python
import socket

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(("0.0.0.0", 8080))
server.listen(5)

print("Server listening...")
while True:
    client, addr = server.accept()
    print(f"Connection from {addr}")
    client.send(b"Hello, Client!")
    client.close()
```

---

## 5. File Handling

### Reading and Writing Files:
```python
# Write to a file
with open("output.txt", "w") as file:
    file.write("Hello, File!")

# Read from a file
with open("output.txt", "r") as file:
    print(file.read())
```

---

## 6. Automating Tasks

### Web Scraping with `requests` and `BeautifulSoup`:
- Install the libraries:
  ```bash
  pip3 install requests beautifulsoup4
  ```

- Example:
```python
import requests
from bs4 import BeautifulSoup

response = requests.get("http://example.com")
soup = BeautifulSoup(response.text, "html.parser")
print(soup.title.string)
```

---

## 7. Working with APIs

### Example: Fetching Data from a Public API:
```python
import requests

url = "https://api.github.com"
response = requests.get(url)
print(response.json())
```

---

## 8. Cryptography with Python

### Using the `cryptography` Library:
- Install the library:
  ```bash
  pip3 install cryptography
  ```

- Example:
```python
from cryptography.fernet import Fernet

# Generate a key
key = Fernet.generate_key()
cipher = Fernet(key)

# Encrypt data
data = b"Secret Message"
encrypted = cipher.encrypt(data)
print(f"Encrypted: {encrypted}")

# Decrypt data
decrypted = cipher.decrypt(encrypted)
print(f"Decrypted: {decrypted.decode()}")
```

---

## 9. Error Handling

### Try-Except Blocks:
```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
```

---

## Summary

By the end of this chapter, you should be able to:
- Write and execute basic Python scripts.
- Use Python for networking, file handling, and automation.
- Perform web scraping and interact with APIs.
- Implement cryptography for secure data handling.

### Next Steps:
- Explore advanced scripting concepts and integrate Python with tools like Metasploit.
- Move to [Excercise Time](exercises.md) to explore scripting in Python for automation and hacking.

---

### Exercises

1. Write a Python script that scans a range of IP addresses for open ports.
2. Automate downloading a file from a URL and save it locally.
3. Create a script that encrypts and decrypts text using `cryptography`.
4. Use `requests` to fetch and display the latest news headlines from an API.
5. Build a simple chat application using Python sockets.
