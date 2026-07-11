# Bandit Level 29 → 30

## Objective

Retrieve the password for **bandit30** by investigating different Git branches in the cloned repository.

---

## Commands Used

- `mkdir` – Create a temporary working directory.
- `cd` – Change directories.
- `git clone` – Clone the remote Git repository.
- `ls` – List repository files.
- `cat README.md` – Read the current README file.
- `git branch -a` – Display all local and remote branches.
- `git checkout dev` – Create and switch to a local branch that tracks `origin/dev`.
- `cat README.md` – Read the README on the `dev` branch.

---

## What I Learned

- Git repositories can contain multiple branches.
- Sensitive information may exist on a different branch even if it is absent from the default branch.
- `git branch -a` lists both local and remote branches.
- `git checkout <branch>` creates a local tracking branch when switching to a remote branch for the first time.
- Always inspect other branches when investigating a Git repository.

---

## Troubleshooting

### Issue

The default `master` branch only displayed the message:

```
<no passwords in production>
```

### Solution

Listed all available branches using:

```bash
git branch -a
```

Discovered the `dev` branch and switched to it:

```bash
git checkout dev
```

Reading the `README.md` on the `dev` branch revealed the password for the next Bandit level.

---

## Screenshots

- Repository cloned successfully.
- Reading the README on the `master` branch.
- Listing all branches with `git branch -a`.
- Switching to the `dev` branch.
- Reading the README on the `dev` branch.
- Successfully obtaining the Bandit30 password.
# Screenshots:
![Proof](</assets/level29-repository-clone.png>)
![Proof](</assets/level29-cat-README.png>)
![Proof](</assets/level29-output.png>)