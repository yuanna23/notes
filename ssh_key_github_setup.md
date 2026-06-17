# SSH Key and GitHub Setup on SMU HPC

## Goal

Connect HPC, VS Code, and GitHub using SSH authentication.

Workflow:

VS Code → HPC → GitHub

---

## Check Git Installation

**Directory:** Any directory on HPC (e.g., `~`)

```bash
git --version
```

Example:

```text
git version 2.34.1
```

---

## Configure Git User Information

**Directory:** Any directory on HPC (e.g., `~`)

```bash
git config --global user.name "yuanna23"
git config --global user.email "yuannawu004@gmail.com"
```

Check:

```bash
git config --global --list
```

---

## Generate SSH Key

**Directory:** Home directory (`~`)

Create a new SSH key:

```bash
ssh-keygen -t ed25519 -C "yuannawu004@gmail.com"
```

Notes:

* Press Enter to accept the default file location.
* Passphrase is optional.
* The email is only a label/comment.

The key files will be stored in:

```text
~/.ssh/id_ed25519
~/.ssh/id_ed25519.pub
```

---

## View Public Key

**Directory:** Any directory on HPC (e.g., `~`)

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the entire line.

---

## Add SSH Key to GitHub

**Directory:** GitHub website (browser)

GitHub:

Settings → SSH and GPG Keys → New SSH Key

Title:

```text
SMU-HPC
```

Paste the public key.

---

## Test Connection

**Directory:** Any directory on HPC (e.g., `~`)

```bash
ssh -T git@github.com
```

Successful output:

```text
Hi yuanna23! You've successfully authenticated,
but GitHub does not provide shell access.
```

---

## Create a Local Repository

**Directory:** Project folder to be tracked by Git

Example:

```bash
cd ~/notes
```

Initialize Git:

```bash
git init
```

---

## Add Files

**Directory:** Repository root directory (e.g., `~/notes`)

```bash
git add .
```

---

## Commit Changes

**Directory:** Repository root directory (e.g., `~/notes`)

```bash
git commit -m "git basic notes"
```

---

## Connect Repository to GitHub

**Directory:** Repository root directory (e.g., `~/notes`)

```bash
git remote add origin git@github.com:yuanna23/notes.git
```

Check:

```bash
git remote -v
```

---

## Upload to GitHub

**Directory:** Repository root directory (e.g., `~/notes`)

First push:

```bash
git branch -M main
git push -u origin main
```

Future updates:

```bash
git add .
git commit -m "update notes"
git push
```

---

## Key Lessons Learned

1. VS Code is only an editor.
2. Python runs on HPC, not on the local Mac.
3. SSH keys allow password-free authentication.
4. GitHub stores code and notes.
5. Git tracks versions of files.
6. `git push` uploads local commits to GitHub.
7. `origin` is the nickname of the remote GitHub repository.
8. Global Git and SSH commands can be run from almost any directory.
9. Repository-specific Git commands (`git add`, `git commit`, `git push`) must be run inside the repository directory.
