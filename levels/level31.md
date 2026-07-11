# Bandit level 32 -32 
# Objective

Push a file to the remote Git repository.

# Commands Used:
```
mkdir /tmp/bandit31
cd /tmp/bandit31

git clone ssh://bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo
cd repo

cat README.md
echo "May I come in?" > key.txt
cat .gitignore
git add -f key.txt

git status
git commit -m "Add key.txt"
git push origin master
```
# What I Learned

- How .gitignore prevents Git from tracking matching files.
- How to use git add -f to force-add an ignored file.
- How to commit and push changes to a remote Git repository.

* **Key Concept:**
- .gitignore tells Git which files to ignore.
- git add -f overrides .gitignore for a specific file.

# Screenshots:

![Proof](</assets/level31-start.png>)
![Proof](</assets/level31-running.png>)
![Proof](</assets/level31-running-2.png>)
![Proof](</assets/level31-output.png>)