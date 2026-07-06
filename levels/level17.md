# Bandit Level 17 → Level 18
* **Objective:**

The goal of this level was to compare two files and identify the changed line containing the password for bandit18.

* **skills Practiced:**

      File comparison,
      Linux text processing,
      Command-line analysis,
      Reading command output,
      Basic troubleshooting

* **Commands Used:**

1. Login to bandit17

`ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220`

2. List Files
    `ls`

 Files Found
 passwords.old
 passwords.new

3. Compare the Files
`diff passwords.old passwords.new`

What diff Does

The diff command compares:

differences between two files



Example structure:
```
42c42
< new-password
 ---
> old-password-hidden
```


    < =	new content
    > =	old content
    c =	Changed line

The line beginning with > contains the updated password for the next level.

**What I Learned:**

diff compares file contents line by line.

Linux tools can quickly identify changes between files.

File comparison is important in version control systems like Git.

The output symbols (<, >) help identify old and new data.

Verification

* **Command Used:**

`diff passwords.new passwords.old`

* **Output:**
```
< [new password-hidden]
 ---
> [old-password-hidden]
  ```
Key Concept:

This level introduced:

file comparison,
version differences,
command-line text analysis,
Linux troubleshooting workflow

![Proof](</assets/level17.png>)
