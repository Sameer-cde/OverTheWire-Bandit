# Bandit Level 13 -> Level 14
* **Objective:** Find the password for the next level stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level

# Method 1 — Manual Key Creation Method
```
In this method, the private key was manually copied from the Bandit server and saved locally on the Ubuntu/WSL machine.

Step 1 — Display The Private Key
* **Command Used:** cat sshkey.private

The output contains the RSA private key.

Step 2 — Create Local Key File

On the local Ubuntu/WSL terminal & Paste the copied private key contents into the file & save.
```
* **Command Used:** nano bandit14key
                    ctrl+O
                    Ctrl+X

Step 3 — Secure File Permissions

* **Command Used:** chmod 600 bandit14key
```
Permission     Meaning

`6`           `owner can read/write`

`0`           `group has no access`

`0`           `others have no access`

SSH requires secure permissions for private keys.

Step 4 — Login Using SSH Key
* **Command Used:** ssh -i bandit14key bandit14@bandit.labs.overthewire.org -p 2220

Step 5 — Retrieve Password

* **Command Used:** cat /etc/bandit_pass/bandit14
```
* **Screenshots**
* **Execution & Verification**
![Proof](</assets/level13a1.png>)
![alt text](</assets/level13a2.png>)



# Method 2 — Using SCP To Transfer The Key.
```
In this method, the private key was securely transferred directly from the Bandit server to the local Ubuntu/WSL machine using scp.

Step 1 — Transfer The Key

Run this on the LOCAL Ubuntu/WSL terminal:

scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .

Enter the Level 13 password when prompted.

Step 2 — Verify The File

`ls`

The transferred file:

`sshkey.private`      should appear in the current local directory.

Step 3 — Secure File Permissions

`chmod 600 sshkey.private`

Step 4 — Login Using The Key

`ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220`

Step 5 — Retrieve Password

`cat /etc/bandit_pass/bandit14`
```

* **What I Learned**:
```
SSH private keys allow authentication without passwords.
scp securely transfers files over SSH.
Linux file permissions are important for SSH security.
SSH keys are widely used in cloud and Linux administration.
Multiple valid methods can solve the same Linux task.

 
    * **Command	        Purpose:**


     ssh	            Secure remote login
     
     scp	            Secure file transfer
     
     chmod 600	        Restrict file permissions
     
     cat	             Display file contents
     
     nano	             Terminal text editor
```
      **Screenshots**
* **Execution & Verification**
![Proof](</assets/level13b1.png>)
![Proof](/assets/level13b2.png)    

     
 * **Important Note:**
```
The original localhost method:

ssh -i sshkey.private bandit14@localhost -p 2220

is currently blocked by the latest OverTheWire infrastructure.

Therefore, the SSH key was used externally from the local Ubuntu/WSL machine instead.
 
 ```
 