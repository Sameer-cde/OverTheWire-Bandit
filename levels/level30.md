
# Bandit Level 30 → 31

## Objective

Retrieve the password for **bandit31** by investigating Git tags in the cloned repository.

---

## Commands Used

- `git clone` – Clone the remote Git repository.
- `ls` – List repository files.
- `git status` – Check the repository status.
- `git log --oneline` – View the commit history in a compact format.
- `git tag` – List all available Git tags.
- `git show secret` – Display the contents of the `secret` tag.

---

## What I Learned

- Git tags are references to specific objects in a repository.
- Tags can contain important information beyond the current branch history.
- `git tag` lists all available tags.
- `git show <tag>` displays the object associated with a tag.
- Investigating Git metadata is an important skill when analyzing repositories.

---

## Troubleshooting

### Issue

The repository did not contain the password in its files or commit history.

### Solution

Listed all available tags:

```bash
git tag
```

Discovered the `secret` tag and inspected it using:

```bash
git show secret
```

The output revealed the password for the next Bandit level.

---

## Screenshots

![Proof](</assets/level30-work1.png>)
![Proof](</assets/level30-work2.png>)
![Proof](</assets/level30-work3.png>)