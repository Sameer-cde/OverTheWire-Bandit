# Bandit Level 27 → 28
# Objective

Clone a Git repository over SSH and retrieve the password for Bandit Level 28 from the repository.

# Commands Used
```
# Create a temporary working directory
`mkdir /tmp/bandit27`

`cd /tmp/bandit27`

# Clone the Git repository
`git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo`

# Enter the cloned repository
`cd repo`

# List repository contents
`ls -la`

# Read the README file
`cat README`
```
# What I Learned
```
How to clone a Git repository using SSH.
How to connect to a Git server running on a custom SSH port (2220).
How Git repositories can be explored using standard Linux commands.
How to authenticate to a Git repository using SSH credentials.
The importance of carefully reading challenge instructions when connecting to remote repositories.
```
# Troubleshooting
```
The repository could not be cloned using the default SSH port (22).
The localhost method did not work correctly in my WSL environment.
Successfully cloned the repository by specifying the OverTheWire hostname and SSH port 2220.
Confirmed the repository contents using ls -la before reading the required file.
Screenshots
Login to Bandit27
Successful git clone
Repository contents (ls -la)
Reading the README file
Password for Bandit28
```
* **Notes:**

Environment: Windows 11 + WSL Ubuntu
Authentication: Password-based SSH using the Bandit27 password
Repository Access: Git over SSH (Port 2220)

# Screenshot:
![Proof](</assets/level27-execution1.png>)
![Proof](</assets/level27-execution2.png>)