# Bandit Level 14 -> Level 15
* **Objective:** Submit the current password to localhost on port 30000 and retrieve the next password.
* **Commands Used:**
  cat /etc/bandit_pass/bandit14

  nc localhost 30000

* **What I Learned:**
nc (netcat) can connect to TCP ports.

localhost refers to the current machine.

Network services listen on specific ports.

Client/server communication can happen through terminal tools.

* **Important Commands Explained:**

`Command`    -->	`Purpose`

nc               -->	 Connect to network ports

localhost        -->	 Current machine

cat	             -->     Display password file


**Execution & Verification**


![level14 Proof](<level14.png>)