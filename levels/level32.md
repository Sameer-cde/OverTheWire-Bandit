# Bandit Level 32 → Level 33

## Objective
The goal of this level is to escape from the restricted uppercase shell and retrieve the password for the next level.

## Connection

```bash
ssh bandit32@bandit.labs.overthewire.org -p 2220
```
# Problem Encountered

- After logging in, the shell converts every command into uppercase letters.

- Example:
```
ls

becomes:

LS
```

- Since Linux commands are case-sensitive, normal commands do not work.

Solution

- The shell executes commands using the $0 environment variable. Running $0 starts a normal shell.
```
$0
```
- Now normal Linux commands work again.

- Check available files:
```
ls
```
- Read the password for the next level:
```
cat /etc/bandit_pass/bandit33
```
# Commands Used:
```
Command	Purpose
$0	    Starts a new normal shell
ls	    Lists files and directories
cat	    Displays the password file
```
# Concept Learned
- Shell restrictions
- Environment variables
- $0 variable in Linux shells
- Escaping a restricted shell

# Screenshot
![proof](</assets/level32.png>)