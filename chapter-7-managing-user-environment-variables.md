# Chapter 7: Managing User Environment Variables

## Overview

Environment variables are a critical aspect of Linux systems. They define the working environment for processes, applications, and users by storing information such as file paths, system configurations, and session data. This chapter covers the tools and techniques for viewing, modifying, and managing environment variables effectively.

---

## 1. Understanding Environment Variables

### Key Concepts:
- **Environment Variable**: A key-value pair that influences the behavior of the system and applications.
- **Types of Environment Variables**:
  - **System-wide**: Defined for all users, typically in `/etc/environment` or `/etc/profile`.
  - **User-specific**: Defined for a specific user, stored in shell configuration files like `~/.bashrc` or `~/.bash_profile`.

### Common Environment Variables:
- `$PATH`: Directories where the shell searches for executables.
- `$HOME`: The user’s home directory.
- `$SHELL`: The default shell for the user.
- `$USER`: The username of the current user.

---

## 2. Viewing Environment Variables

### `printenv`: Display Environment Variables
- Displays all environment variables or a specific one.

#### Examples:
```bash
printenv                 # Show all variables
printenv PATH            # Show the value of PATH
```

### `env`: List Environment Variables
- Similar to `printenv`, lists all environment variables.

#### Example:
```bash
env
```

### `echo`: Display a Specific Variable
- Prints the value of a specific environment variable.

#### Example:
```bash
echo $HOME
```

---

## 3. Setting Environment Variables

### Temporarily Set a Variable
- The variable exists only for the current session.

#### Syntax:
```bash
export VARIABLE_NAME=value
```

#### Examples:
- Set a new variable:
  ```bash
  export MY_VAR="Hello World"
  ```
- Verify the variable:
  ```bash
echo $MY_VAR
  ```

### Permanently Set a Variable
- Add the variable to a shell configuration file.

#### Example (for Bash):
1. Open `~/.bashrc` or `~/.bash_profile`:
   ```bash
   nano ~/.bashrc
   ```
2. Add the variable:
   ```bash
   export MY_VAR="Persistent Value"
   ```
3. Apply the changes:
   ```bash
   source ~/.bashrc
   ```

---

## 4. Modifying `PATH`

The `$PATH` variable determines where the shell looks for executables.

### Add a Directory to `$PATH`:
```bash
export PATH=$PATH:/new/directory
```

### Example:
- Add `/usr/local/bin` to `$PATH`:
  ```bash
  export PATH=$PATH:/usr/local/bin
  ```
- Make the change permanent:
  Add the above line to `~/.bashrc` or `~/.bash_profile`.

---

## 5. Unsetting Environment Variables

### `unset`: Remove an Environment Variable
- Deletes a variable from the environment.

#### Syntax:
```bash
unset VARIABLE_NAME
```

#### Example:
```bash
unset MY_VAR
```

---

## 6. Debugging Environment Variables

### `env -i`: Start with a Clean Environment
- Runs a command with a minimal environment.

#### Example:
```bash
env -i bash --noprofile --norc
```

### `set`: Display Shell Variables
- Lists all shell and environment variables.

#### Example:
```bash
set
```

---

## 7. Common Environment Variable Files

### System-wide Configuration:
- `/etc/environment`: Contains global environment variables.
- `/etc/profile`: Executes for all users at login.

### User-specific Configuration:
- `~/.bashrc`: Executes for non-login Bash shells.
- `~/.bash_profile`: Executes for login Bash shells.

---

## Summary

By the end of this chapter, you should be able to:
- View environment variables using `printenv`, `env`, and `echo`.
- Set and modify environment variables both temporarily and permanently.
- Customize and debug the `$PATH` variable.
- Use configuration files to manage environment variables effectively.

### Next Steps:
- Move to [Chapter 8: Bash Scripting](chapter-8-bash-scripting.md) to learn how to automate tasks using Bash scripts.

---

### Exercises

1. Display all environment variables on your system using `env`.
2. Set a temporary environment variable and verify its value.
3. Add a new directory to your `$PATH` and make it permanent.
4. Remove an environment variable using `unset`.
5. Identify the difference between `~/.bashrc` and `/etc/environment` in your system.
