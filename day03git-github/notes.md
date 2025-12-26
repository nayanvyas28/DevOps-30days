# Day 03 – Git & GitHub for DevOps

## What is Git?
Git is a distributed version control system used to track code changes.

Git helps to:
- Track changes
- Collaborate with teams
- Roll back mistakes
- Maintain history

---

## What is GitHub?
GitHub is a cloud platform that hosts Git repositories.

Git vs GitHub:
- Git → version control tool
- GitHub → remote repository & collaboration platform

---

## Git Workflow (Basic)
1. Modify files
2. git add
3. git commit
4. git push
5. CI/CD pipeline triggers

---

## Essential Git Commands

### Setup
git config --global user.name "Your Name"
git config --global user.email "youremail@gmail.com"

---

### Repository Commands
git init
git clone <repo_url>
git status

---

### Staging & Commit
git add file.txt
git add .
git commit -m "Meaningful message"

---

### Branching
git branch
git branch dev
git checkout dev
git checkout -b feature-1

---

### Merging
git checkout main
git merge dev

---

### Remote Repository
git remote add origin <repo_url>
git push -u origin main
git pull origin main

---

## .gitignore
Used to ignore files like:
- node_modules
- .env
- build files

Example:
node_modules/
.env

---

## GitHub Pull Request (PR)
Pull Request is used to:
- Review code
- Merge branches safely
- Collaborate in teams

---

## Git in DevOps
- CI/CD triggers from Git push
- Infrastructure code stored in Git
- GitHub Actions read repo files

---

## What I Learned Today
- Git fundamentals and workflow
- Difference between Git and GitHub
- Branching and merging
- Importance of clean commit messages
- Git’s role in DevOps automation

---

## Interview Notes
- Git tracks changes, GitHub hosts code
- Branching isolates features
- PRs enable collaboration
- Git history helps rollback
