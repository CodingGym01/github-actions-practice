# Git & GitHub Basics Practice

## 1. Multiple GitHub Accounts Setup Using SSH

### Existing Work GitHub SSH
Verified existing SSH connection:

```bash
ssh -T git@github.com
```

Output:
```bash
Hi harshcodes893! You've successfully authenticated
```

---

## 2. Created Personal SSH Key

Generated new SSH key for personal GitHub account:

```bash
ssh-keygen -t ed25519 -C "your-personal-email"
```

Saved as:

```bash
~/.ssh/id_ed25519_personal
```

---

## 3. Added SSH Key to GitHub

Copied public key:

```bash
cat ~/.ssh/id_ed25519_personal.pub
```

Added key in GitHub SSH settings.

---

## 4. SSH Config Setup

Created SSH config file:

```bash
nano ~/.ssh/config
```

Configuration:

```config
# Work GitHub
Host github-work
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519

# Personal GitHub
Host github-personal
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_personal
```

---

## 5. SSH Verification

### Work Account

```bash
ssh -T git@github-work
```

### Personal Account

```bash
ssh -T git@github-personal
```

---

# Git Basics Workflow

## 1. Clone Repository

```bash
git clone git@github-personal:CodingGym01/github-actions-practice.git
```

---

## 2. Configure Git Identity

```bash
git config user.name "CodingGym01"
git config user.email "your-email@gmail.com"
```

---

## 3. Create File

```bash
touch test.txt
```

Add content:

```bash
echo "This is just a practice file for demo" > test.txt
```

---

## 4. Check Git Status

```bash
git status
```

---

## 5. Add File to Staging

```bash
git add test.txt
```

---

## 6. Commit Changes

```bash
git commit -m "Adding first text file"
```

---

## 7. Push Changes

```bash
git push origin main
```

---

# Important Learning

## Git Commit vs Push

### Commit
Saves changes locally.

### Push
Uploads commits to GitHub.

---

# Branching Practice

## View Branches

```bash
git branch
```

---

## Create New Branch

```bash
git checkout -b feature/testing
```

OR

```bash
git switch -c feature/testing
```

---

## Switch Branches

```bash
git switch main
```

```bash
git switch feature/testing
```

---

# Important Git Debugging Commands

## Check Current Status

```bash
git status
```

## Check Remote URL

```bash
git remote -v
```

## Check Branches

```bash
git branch
```

---

# Important Learning About Remote URL

Initially repo was using HTTPS:

```bash
https://github.com/username/repo.git
```

This caused:

```bash
403 Permission Denied
```

Fixed by changing remote to SSH:

```bash
git remote set-url origin git@github-personal:CodingGym01/github-actions-practice.git
```

---

# Key Learnings

- SSH is preferred over HTTPS for professional workflows.
- Git commit saves locally.
- Git push uploads to GitHub.
- Branches isolate work safely.
- `git status` is the most important Git command.
- `git remote -v` helps debug remote issues.
