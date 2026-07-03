# Bandit Level 15 -> Level 16

* **Objective:** Submit the password of the current level to a specific port on localhost using SSL/TLS encryption to retrieve the password for Level 16.

* **Commands Used:**
  
  ```
  cat /etc/bandit_pass/bandit15
  openssl s_client -connect localhost:30001
  ```
  * **What I Learned:**

`openssl s_client`: A powerful tool used to establish secure, encrypted SSL/TLS connections to a remote or local host port.

`SSL/TLS vs Netcat`: While nc handles raw text network communication, encrypted ports will reject standard connections unless a proper cryptographic handshake is completed first via OpenSSL.

* **Screenshots**
**Execution & Verification**
![Proof](<level15a.png>)

![Proof](<level15b.png>)

* **Password** `kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V`