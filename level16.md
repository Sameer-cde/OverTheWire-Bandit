# Bandit Level 16 -> Level 17
* **Objective:** Find the correct SSL-enabled port between 31000-32000, submit the current password, and retrieve the SSH private key for bandit17.
* **Commands Used:**
cat /etc/bandit_pass/bandit16
nmap -sV localhost -p 31000-32000
openssl s_client -connect localhost:31790 
echo "P@ssword" | openssl s_client -connect localhost:31790 -ign_eof
nano /tmp/bandit17.key
cat << 'EOF' > /tmp/bandit17.key
chmod 600 /tmp/bandit17.key
ssh -i /tmp/bandit17.key bandit17@bandit.labs.overthewire.org -p 2220

* **What I Learned**
nmap can scan a range of ports and identify services.
Multiple SSL ports may exist, but only one provides the correct service.
openssl s_client can connect to SSL/TLS services manually.
TLS output may include messages like KEYUPDATE.
SSL certificates are different from SSH private keys.
Temporary files in /tmp may already exist and contain old data.
Using echo and the -ign_eof flag
This method keeps the interactive SSL connection open even after your password text is sent, which ensures the server has enough time to return the full private key before the stream cuts off.
Using the cat << 'EOF' trick
This method is used when you want to write or overwrite a file directly from the terminal line by line without opening a text editor like Nano.

* **Troubleshooting Notes**

At first I:

connected to the wrong ports
saw KEYUPDATE messages
entered the password incorrectly
confused SSL certificate output with the RSA private key
found an existing temporary file in /tmp/bandit17.key

I learned to:

identify the correct SSL service
send the password only once
save only the RSA private key block
Correct Key Format

The correct SSH key begins with:

-----BEGIN RSA PRIVATE KEY-----

and ends with:

-----END RSA PRIVATE KEY-----

This is different from SSL certificate output such as:

-----BEGIN CERTIFICATE-----

* **Verification:**
`Port Scan`

nmap -sV localhost -p 31000-32000

Example output:

31790/tcp open  ssl/unknown

31518/tcp open  ssl/echo

`SSL Connection`
openssl s_client -connect localhost:31790 -ign_eof

Example output:


Correct!

[next password hidden]

-----BEGIN RSA PRIVATE KEY-----
[hidden]
-----END RSA PRIVATE KEY-----

`Successful Login`

ssh -i /tmp/bandit17.key bandit17@bandit.labs.overthewire.org -p 2220

Example:

bandit17@bandit:~$

Key Concept

This level introduced:

port scanning

SSL/TLS service discovery

network troubleshooting

SSH private key authentication

service enumeration





 
