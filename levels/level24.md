# Bandit Level 24 -> Level 25

## Objective
The password for level 25 is given by a daemon listening on port 30002. To get the password, we need to send the bandit24 password followed by a secret 4-digit PIN (from 0000 to 9999) on a single line, separated by a space.

## Commands Used
* `mkdir` - To create a directory in /tmp for our script.
* `cd` - To change directory.
* `nano` - To write the Bash brute force script.
* `chmod +x` - To grant execution permissions to the script.
* `./brute.sh > response.txt` - Execute the script and save the ourput to a file.
* `nc` - To connect to the local daemon on port 30002.
* `grep -v` - To filter out all lines containing "Wrong" and only see the success message.

## Code Used (brute.sh)
```bash
#!/bin/bash

for pin in {0000..9999}
do
    echo "VAXpO3...[your_bandit24_pass]... $pin"
done | nc localhost 30002
```



![level24 Proof](/assets/level24-execution.png)