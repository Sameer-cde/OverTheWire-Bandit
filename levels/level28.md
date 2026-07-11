

# Bandit Level 28 → 29

## Objective

Retrieve the password for **bandit29** by inspecting the Git commit history of the cloned repository.

---

## Commands Used

- `mkdir` – Create a temporary working directory.
- `cd` – Change directories.
- `git clone` – Clone the remote Git repository.
- `ls` – List repository files.
- `cat README.md` – View the current README.
- `git log` – Display the commit history.
- `git show HEAD~1` – View the previous commit and recover the original password.

---

## What I Learned

- Git stores the complete history of a project.
- Deleted or modified data can often be recovered from previous commits.
- `git log` is used to inspect commit history.
- `git show` displays the contents of a specific commit.
- `HEAD~1` refers to the commit immediately before the current one.

---

## Troubleshooting

### Issue
Initially thought the password should exist in the latest `README.md`.

### Solution
Examined the commit history with `git log` and viewed the previous commit using:

```bash
git show HEAD~1
```

The original password was present before the information leak was fixed.

---

## Screenshots

- Cloning the repository.
- Viewing `README.md`.
- Running `git log`.
- Running `git show HEAD~1`.
- Successfully obtaining the Bandit29 password.

![Proof](</assets/level28-running-gitlog.png>)
![Proof](</assets/level28-git-show-head1.png>)
![alt text](</assets/level28-password.png>)