# Bandit Level 19 → Level 20
* **Objective**

The goal of this level was to use a SUID-enabled executable to access the password for bandit20.

* **Commands Used:**
1. Login to bandit19

`ssh bandit19@bandit.labs.overthewire.org -p 2220`

2. List Files and Permissions

`ls -l`

Example output:

-rwsr-x--- 1 bandit20 bandit19 ... bandit20-do

Understanding the Permissions

The permission string contained:

s

Example:

-rwsr-x---

This indicates:

SUID (Set User ID)

What SUID Means

Normally, programs execute with:

the current user's permissions

However, SUID allows a program to run with:

the file owner's permissions

In this level:

the executable belonged to bandit20

the program was executed by bandit19

This allowed temporary execution with elevated permissions.

3. Check Program Usage

  ./bandit20-do


What ./ Means

    ./tells Linux to execute a file from the current directory

Linux does not automatically run programs from the current directory for security reasons.

4. Use the SUID Program

./bandit20-do cat /etc/bandit_pass/bandit20

**Understanding the Command**

./bandit20-do =	Execute SUID program

cat	= Command to run

/etc/bandit_pass/bandit20 =	Protected password file


Why This Works

Normally:

cat /etc/bandit_pass/bandit20

fails because:

bandit19 does not have permission

However:

./bandit20-do

executes the command with:

bandit20 privileges

allowing access to the protected file.

**What I Learned**

Linux permissions control file and program access.

SUID programs execute with the owner's privileges.

./ executes programs from the current directory.

Misconfigured SUID binaries can become security vulnerabilities.

Linux privilege management is important in system security.


**Example output:*8

[next-password-hidden]


**Screenshot**


![Proof](</assets/level19ls-l&SUIDcommand.png>)
![Proof](</assets/level19execution.png>)



Key Takeaway

This level demonstrated how Linux programs can temporarily execute with another user's permissions using the SUID mechanism.

