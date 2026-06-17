# Git Basics for Research

## 1. Clone a Repository

Download a repository from GitHub to your HPC or local computer.

```bash
git clone git@github.com:USERNAME/REPOSITORY.git
```

Example:

```bash
git clone git@github.com:yuanna23/python-learning.git
```

---

## 2. Check Repository Status

View modified, new, or untracked files.

```bash
git status
```

Example output:

```text
modified: analysis.py
untracked: results.csv
```

---

## 3. Add Files to Staging Area

Add all changed files:

```bash
git add .
```

Add a specific file:

```bash
git add analysis.py
```

---

## 4. Commit Changes

Save a snapshot of your work.

```bash
git commit -m "Update RNA-seq analysis script"
```

Examples:

```bash
git commit -m "Initial commit"
git commit -m "Add GEO download function"
git commit -m "Fix plotting bug"
```

---

## 5. Push Changes to GitHub

Upload commits to GitHub.

```bash
git push
```

Usually:

```bash
git push origin main
```

---

## 6. Pull Latest Changes

Download updates from GitHub.

```bash
git pull
```

Usually:

```bash
git pull origin main
```

---

# Typical Workflow

After modifying code:

```bash
git status
git add .
git commit -m "Describe your changes"
git push
```

---

# Useful Commands

View commit history:

```bash
git log
```

Short history:

```bash
git log --oneline
```

Check remote repository:

```bash
git remote -v
```

---

# Recommended Repository Structure

```text
research-project/
│
├── data/
├── scripts/
├── figures/
├── notebooks/
├── results/
├── README.md
└── environment.yml
```

---

# Good Commit Message Examples

```text
Add GEO data download script
Update Seahorse analysis
Fix normalization method
Add differential expression workflow
Generate Figure 2
```

Avoid:

```text
update
test
fix
123
```

---

# Personal Research Workflow

VS Code
↓
SMU HPC
↓
GitHub

Edit code → Commit → Push → Backup automatically

```
```
