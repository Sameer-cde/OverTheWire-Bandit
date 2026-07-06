# Bandit Level 21 → Level 22

## Objective

The goal of this level was to investigate scheduled cron jobs and identify where the password for `bandit22` was being stored.

---

# Skills Practiced

* Cron job analysis
* Linux task scheduling
* Bash script inspection
* File discovery
* Linux system directories
* Reading automated scripts

---

# Commands Used

## 1. Login to bandit21

```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```

---

# 2. Explore Cron Job Directory

```bash
ls /etc/cron.d/
```

A cron configuration file related to:

```text
cronjob_bandit22
```

was discovered.

---

# 3. Read the Cron Job File

```bash
cat /etc/cron.d/cronjob_bandit22
```

The file showed:

* which script executes
* which user runs the script
* how often the task runs

---

# Example Output

```text
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh
```

This means:

```text
the script executes every minute
```

---

# 4. Inspect the Script

```bash
cat /usr/bin/cronjob_bandit22.sh
```

The script revealed:

* where the password was copied
* which temporary file stored the output

---

# Bash Concepts Observed

The script used Linux commands such as:

```bash
cat
chmod
echo
```

This demonstrated how Bash scripts automate Linux tasks.

---

# 5. Read the Password File

After identifying the generated file path:

```bash
cat /tmp/<generated-file>
```

The password for:

```text
bandit22
```

was successfully retrieved.

---

# What I Learned

* Cron jobs automate scheduled Linux tasks.
* `/etc/cron.d/` stores cron configuration files.
* Bash scripts can automate repetitive operations.
* Linux systems frequently use `/tmp/` for temporary output.
* Reading scripts is important for understanding system behavior.


---

# Screenshot Recommendation

One screenshot showing:
![Proof](</assets/level21 script analysis & output.png>)
![Proof](</assets/level21 cronfile inspection.png>)
* cron file inspection
* script analysis
* successful password retrieval


---

# Key Takeaway

This level introduced automated Linux task scheduling using cron jobs and demonstrated how Bash scripts are used in real Linux environments.

---
