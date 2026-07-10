# Bandit Level 26 → 27

# Objective

Obtain the password for bandit27 by escaping the restricted shell as bandit26 and using the provided SUID executable to execute commands with bandit27's privileges.

# Concepts Learned
```
Set User ID (SUID)
Linux file permissions
Privilege escalation (educational)
Executing commands as another user
Linux security principles
Command execution through helper programs
```
# Commands Used:


# List files in the home directory
ls 

# View information about the executable
file bandit27-do

# Display usage information
./bandit27-do

# Read Bandit27 password
./bandit27-do cat /etc/bandit_pass/bandit27

# Solution Summary
```
Escaped the restricted login shell and obtained an interactive Bash shell as bandit26.
Listed the contents of the home directory.
Found the executable bandit27-do.
Investigated its purpose and identified it as a SUID helper program.
Used the executable to run commands with bandit27 privileges.
Read the password stored in /etc/bandit_pass/bandit27.
Successfully logged into Bandit27.
```
# Troubleshooting:
```
Issue 1: Permission denied when accessing the password directly

Cause

The password file belongs to bandit27, so bandit26 cannot read it directly.

Solution

Use the provided SUID executable instead of accessing the file directly.

./bandit27-do cat /etc/bandit_pass/bandit27
```

# Screenshots:
![Level26 Proof](</assets/level26.png>)