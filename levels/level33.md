# Bandit Level 33 → End

## Objective

The goal of this level is to read the final message and complete the OverTheWire Bandit challenge.

## Connection

```bash
ssh bandit33@bandit.labs.overthewire.org -p 2220
```

## Solution

After logging in, list the files in the home directory:

```bash
ls
```

Output:

```
README.txt
```

Read the file:

```bash
cat README.txt
```

The file contains the final message confirming that the Bandit wargame has been completed.

## Commands Used
```
| Command | Purpose |
|---------|---------|
| `ls` | Lists files and directories |
| `cat` | Displays the contents of a file |
```
## What I Learned

- Reviewed Linux command-line fundamentals learned throughout Bandit.
- Practiced SSH connections and remote server access.
- Improved understanding of file handling and system administration concepts.
- Completed all Bandit levels from Level 0 to Level 33.

## Screenshot

![level33 completion](</assets/level33-work.png>)

## Completion

Successfully completed the OverTheWire Bandit wargame and documented all levels in this repository.