# Bandit Level 25 → 26

# Objective

Authenticate as bandit26 using the provided SSH private key. Since the login shell is configured to execute a custom program (showtext) instead of a standard shell, understand its behavior and escape the restricted environment to obtain the password for bandit26.

# Concepts Learned
SSH private key authentication
Linux login shells
Reading system account information (/etc/passwd)
Understanding shell scripts
File permissions (chmod 600)
Temporary working directories (/tmp)
more pager behavior
Escaping from vim to a shell
vim shell escape (:set shell and :shell)
Escaping from restricted environments
Pager (more) interaction

# Commands Used:
```
# Login to Bandit25
ssh bandit25@bandit.labs.overthewire.org -p 2220

# View files
ls

# Check Bandit26's login shell
grep bandit26 /etc/passwd

# Read the custom login shell script
cat /usr/bin/showtext

# Display the SSH private key
cat bandit26.sshkey

# Open a second terminal
mkdir /tmp/bandit26
cd /tmp/bandit26

# Create a key file
nano bandit26.key

# Secure the private key
chmod 600 bandit26.key

# Login using the SSH private key
ssh -i bandit26.key bandit26@bandit.labs.overthewire.org -p 2220

# Inside the "more" pager
v

Once vim opens, type:

:set shell=/bin/bash

Press Enter, then type:

:shell

Press Enter again.


Finally, read the password:

 cat /etc/bandit_pass/bandit26
```
# Solution Summary
```
Logged into Bandit25.
Listed the files and found the bandit26.sshkey private key.
Checked Bandit26's login shell using /etc/passwd and discovered it used the custom showtext program.
Read the showtext script to understand its behavior.
Opened the private key and copied it.
Opened a second terminal and created a temporary working directory under /tmp.
Created a new key file (bandit26.key) and pasted the private key.
Restricted the key permissions with chmod 600.
Connected to Bandit26 using the private key.
Reduced the terminal height so the more pager paused instead of exiting immediately.
Pressed v to open the file in vim.
Escaped from vim to a Bash shell.
Read the Bandit26 password.
```
# What I Learned

How SSH private key authentication works.
Why private keys should have restrictive permissions (chmod 600).
How to inspect a user's login shell using /etc/passwd.
How custom login shells can restrict user access.
How the more pager behaves when the terminal size changes.
How vim can be used to escape into a shell in a controlled environment.
Why understanding Linux tools is more important than memorizing commands.

# Troubleshooting
```
Issue 1: SSH to localhost was blocked

Cause: The current OverTheWire server blocks SSH connections to localhost to conserve resources.

Solution: Created a local key file in a second terminal and connected directly to:

ssh -i bandit26.key bandit26@bandit.labs.overthewire.org -p 2220
Issue 2: Immediate disconnection after login

Cause: The showtext login shell executed more, which exited immediately because the terminal was large enough to display the entire file.

Solution: Reduced the terminal height so more paused, allowing interaction.

Issue 3: SSH private key permissions

Cause: SSH requires private keys to be accessible only by the owner.

Solution:
chmod 600 bandit26.key
```

# Screenshots
![Proof](</assets/level25-execution-1.png>)
![Proof1](</assets/level25-execution-2.png>)
![Proof2](</assets/level25-execution-3.png>)
![Proof3](/assets/level25-output.png)