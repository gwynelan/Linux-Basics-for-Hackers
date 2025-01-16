# Chapter 8: Bash Scripting

## Overview

Bash scripting is a powerful tool for automating tasks, managing systems, and creating efficient workflows in Linux. This chapter introduces the fundamentals of Bash scripting, common use cases, and advanced techniques to write robust scripts.

---

## 1. Introduction to Bash Scripting

### What is a Bash Script?
- A Bash script is a file containing a series of commands that are executed sequentially by the Bash shell.
- Scripts are used to automate repetitive tasks and manage system operations.

### Creating a Bash Script
1. Open a text editor (e.g., `nano`, `vim`).
2. Write your script.
3. Save the file with a `.sh` extension (e.g., `script.sh`).
4. Make the script executable using `chmod`:
   ```bash
   chmod +x script.sh
   ```
5. Run the script:
   ```bash
   ./script.sh
   ```

### Example:
```bash
#!/bin/bash
# Simple Bash Script

echo "Hello, World!"
```

---

## 2. Script Components

### Shebang (`#!`)
- The shebang specifies the interpreter for the script.
- Common example:
  ```bash
  #!/bin/bash
  ```

### Comments
- Use `#` for single-line comments.
- Use comments to document the purpose of your script and its sections.

### Variables
- Store and reuse data within the script.

#### Syntax:
```bash
VARIABLE_NAME=value
```

#### Example:
```bash
name="Linux User"
echo "Hello, $name!"
```

---

## 3. Control Structures

### Conditional Statements

#### `if-else`
```bash
if [ condition ]; then
  # Commands
else
  # Commands
fi
```

#### Example:
```bash
#!/bin/bash
number=10
if [ $number -gt 5 ]; then
  echo "Number is greater than 5"
else
  echo "Number is 5 or less"
fi
```

### Loops

#### `for` Loop
```bash
for var in list; do
  # Commands
done
```

#### Example:
```bash
for i in 1 2 3 4 5; do
  echo "Number: $i"
done
```

#### `while` Loop
```bash
while [ condition ]; do
  # Commands
done
```

#### Example:
```bash
count=1
while [ $count -le 5 ]; do
  echo "Count: $count"
  ((count++))
done
```

---

## 4. Functions

### Defining and Calling Functions
- Functions allow you to organize reusable blocks of code.

#### Syntax:
```bash
function_name() {
  # Commands
}
```

#### Example:
```bash
#!/bin/bash
hello() {
  echo "Hello, $1!"
}
hello "World"
```

---

## 5. Input and Output

### Reading Input
- Use `read` to get input from the user.

#### Example:
```bash
#!/bin/bash
echo "Enter your name:"
read name
echo "Hello, $name!"
```

### Redirecting Output
- Redirect standard output to a file:
  ```bash
  command > file
  ```
- Append output to a file:
  ```bash
  command >> file
  ```
- Redirect standard error:
  ```bash
  command 2> error.log
  ```

---

## 6. Debugging Scripts

### Enable Debug Mode
- Use `-x` to debug a script:
  ```bash
  bash -x script.sh
  ```

### Add Debug Statements
- Use `set -x` to enable debug mode within a script and `set +x` to disable it.

#### Example:
```bash
#!/bin/bash
set -x
echo "Debugging this script"
set +x
echo "Debugging disabled"
```

---

## 7. Advanced Techniques

### Arrays
- Store multiple values in a single variable.

#### Example:
```bash
fruits=("apple" "banana" "cherry")
echo ${fruits[1]}
```

### Case Statements
- Handle multiple conditions elegantly.

#### Example:
```bash
#!/bin/bash
echo "Enter a number:"
read number
case $number in
  1)
    echo "You entered one" ;;
  2)
    echo "You entered two" ;;
  *)
    echo "Invalid choice" ;;
esac
```

---

## Summary

By the end of this chapter, you should be able to:
- Write and execute basic Bash scripts.
- Use variables, control structures, and functions in scripts.
- Handle user input and output effectively.
- Debug scripts and implement advanced scripting techniques.

### Next Steps:
- Move to [Chapter 9: Compressing and Archiving](chapter-9-compressing-and-archiving.md) to learn about managing file compression and archives in Linux.

---

### Exercises

1. Write a script that calculates the factorial of a number using a `while` loop.
2. Create a script that backs up a directory to a specified location.
3. Write a script to check if a file exists and display an appropriate message.
4. Use a `for` loop to iterate through all `.txt` files in a directory and display their content.
5. Debug a script using `bash -x` and identify potential issues.
