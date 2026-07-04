# OverTheWire: Bandit Level 18 → Level 19 Walkthrough

##  Objective
The password for Level 19 is stored in a file named `readme` in the home directory. However, the `bandit18` account has been modified to immediately log out any user who attempts to establish an interactive SSH login session.



##  Commands Used
* `ssh`: Secure Shell client used to execute a remote command without initiating an interactive terminal shell profile.



##  Execution & Troubleshooting Steps

### Step 1: Analyzing the Interactive Login Drop
Attempting a standard connection results in an immediate termination of the environment session:
```
ssh bandit18@bandit.labs.overthewire.org -p 2220
```
  Result: The connection drops immediately upon authenticating, displaying a logout banner (Byebye!). This indicates that configuration scripts like .bashrc, .profile, or the user's default login shell are set to trigger an exit condition instantly.
  
   # Step 2: Commanding via SSH Execution

    ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
    
 # Step 3:Extracting the Password 
 Input the password obtained from Level 17 when prompted. Because the command is passed inline, the server executes cat readme immediately upon successful authentication and pipes the output back to your local command line before closing the connection:

 [Password for Level 19 is displayed here]

 # What I Learned

SSH can execute remote commands directly.

Linux shell environments can restrict interactive access.

Non-interactive SSH execution is commonly used in automation and administration.

Shell configuration files can control login behavior.

# Screenshot:

![Proof](<level18remote-command.png>)
![Proof](<level18commandoutput.png>)