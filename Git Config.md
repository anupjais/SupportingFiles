# Git Configuration & GitHub Workflow

## 1. Configure Git

Configure your Git username and email globally. This will be used for all repositories on your system.

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Verify the global configuration

```bash
git config --global user.name
git config --global user.email
```

You can also view all global Git configuration:

```bash
git config --global --list
```

---

## 2. Configure Git for a Specific Repository

Sometimes a repository needs a different name or email from your global configuration.

Run these commands **inside the repository**:

```bash
git config user.name "Your Name"
git config user.email "your.email@example.com"
```

### Verify the local configuration

```bash
git config user.name
git config user.email
```

To see where Git is getting the configuration from:

```bash
git config --list --show-origin
```

> **Note:** Local repository configuration takes precedence over global configuration.

---

# Create a New Git Repository and Push It to GitHub

## 3. Initialize the Repository

Go to your project directory:

```bash
cd /path/to/your/project
```

Initialize Git:

```bash
git init
```

---

## 4. Add Files to Git

Add all files:

```bash
git add .
```

Or add a specific file:

```bash
git add README.md
```

Check what will be committed:

```bash
git status
```

---

## 5. Create the First Commit

```bash
git commit -m "Initial commit"
```

Use a meaningful commit message, for example:

```bash
git commit -m "Add currency conversion feature"
```

---

## 6. Set the Default Branch to `main`

If the repository is using another default branch name:

```bash
git branch -M main
```

This is generally required only during the initial repository setup.

---

## 7. Connect the Local Repository to GitHub

Create a repository on GitHub first, then add it as the `origin` remote:

```bash
git remote add origin https://github.com/your-git-username/your-repo-name.git
```

Verify the remote:

```bash
git remote -v
```

You should see something similar to:

```text
origin  https://github.com/your-git-username/your-repo-name.git (fetch)
origin  https://github.com/your-git-username/your-repo-name.git (push)
```

---

## 8. Push the Repository to GitHub

```bash
git push -u origin main
```

The `-u` option sets `origin/main` as the upstream branch.

After this, you can usually use simply:

```bash
git push
```

and:

```bash
git pull
```

---

# Updating an Existing Repository

Once the repository is already connected to GitHub, **do not run `git remote add origin` again**.

You can check the remote with:

```bash
git remote -v
```

Then:

## 9. Get the Latest Changes

```bash
git pull --rebase
```

Or:

```bash
git pull origin main --rebase
```

---

## 10. Make Your Changes

Edit/create/delete files as required.

Check the changes:

```bash
git status
```

You can also inspect the actual changes:

```bash
git diff
```

---

## 11. Stage the Changes

Add everything:

```bash
git add .
```

Or add specific files:

```bash
git add src/App.jsx
```

---

## 12. Commit the Changes

```bash
git commit -m "Describe your changes"
```

For example:

```bash
git commit -m "Fix currency conversion API"
```

---

## 13. Push the Changes

```bash
git push
```

Or explicitly:

```bash
git push origin main
```

---

# If Push Is Rejected

Sometimes you may see:

```text
! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/...'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally.
```

This means the remote repository contains commits that your local repository does not have.

### Recommended solution

First pull the remote changes using rebase:

```bash
git pull origin main --rebase
```

If there are no conflicts, push again:

```bash
git push origin main
```

---

# If There Are Merge Conflicts During Rebase

Git may tell you that there are conflicts.

Check the conflicting files:

```bash
git status
```

Open the files and resolve the conflict markers:

```text
<<<<<<< HEAD
your local changes
=======
remote changes
>>>>>>> ...
```

After resolving the conflicts:

```bash
git add .
```

Continue the rebase:

```bash
git rebase --continue
```

If Git reports more conflicts, resolve them and repeat:

```bash
git add .
git rebase --continue
```

When the rebase is complete:

```bash
git push origin main
```

### If you want to cancel the rebase

```bash
git rebase --abort
```

This returns your repository to the state it was in before the rebase.

---

# Force Push

Sometimes you intentionally rewrote local history and need to update the remote branch.

Avoid using:

```bash
git push --force
```

unless you understand the consequences.

A safer option is:

```bash
git push --force-with-lease
```

`--force-with-lease` checks that the remote branch has not changed unexpectedly before overwriting it.

Example:

```bash
git push --force-with-lease origin main
```

> ⚠️ **Warning:** Force pushing can overwrite commits on the remote repository. Be especially careful when working with shared repositories.

---

# Check Remote Configuration

Show the current remote:

```bash
git remote -v
```

Show more detailed information:

```bash
git remote show origin
```

---

# Change an Existing Remote URL

If `origin` already exists, don't use:

```bash
git remote add origin ...
```

Instead use:

```bash
git remote set-url origin https://github.com/your-git-username/your-repo-name.git
```

Verify:

```bash
git remote -v
```

---

# Remove a Remote

If you need to remove `origin`:

```bash
git remote remove origin
```

Then add it again if required:

```bash
git remote add origin https://github.com/your-git-username/your-repo-name.git
```

---

# Useful Git Commands

### Check repository status

```bash
git status
```

### View commit history

```bash
git log --oneline
```

### View branches

```bash
git branch
```

### View all branches

```bash
git branch -a
```

### Create a new branch

```bash
git switch -c feature-name
```

### Switch branches

```bash
git switch main
```

### View configured Git identity

```bash
git config user.name
git config user.email
```

### View all configuration

```bash
git config --list
```

---

# GitHub Authentication

When using GitHub over HTTPS, GitHub does **not** accept your normal GitHub account password for Git operations.

Depending on your setup, use one of these approaches:

* GitHub CLI / credential manager
* Personal Access Token (PAT)
* SSH authentication

For SSH, your remote will look like:

```bash
git@github.com:your-git-username/your-repo-name.git
```

You can check your current authentication/credential setup with:

```bash
git config --global --get credential.helper
```

---

# Typical Workflow

For an existing repository, the normal workflow is:

```bash
git pull --rebase

# Make your changes

git status
git add .
git commit -m "Describe your changes"
git push
```

For a brand-new local project:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/your-git-username/your-repo-name.git
git push -u origin main
```

---

# Quick Reference

| Task                       | Command                                            |
| -------------------------- | -------------------------------------------------- |
| Configure global name      | `git config --global user.name "Your Name"`        |
| Configure global email     | `git config --global user.email "you@example.com"` |
| Configure repository name  | `git config user.name "Your Name"`                 |
| Configure repository email | `git config user.email "you@example.com"`          |
| Initialize Git             | `git init`                                         |
| Check status               | `git status`                                       |
| Add all files              | `git add .`                                        |
| Commit                     | `git commit -m "message"`                          |
| Create branch              | `git switch -c branch-name`                        |
| Rename branch              | `git branch -M main`                               |
| Add remote                 | `git remote add origin URL`                        |
| Change remote              | `git remote set-url origin URL`                    |
| Check remote               | `git remote -v`                                    |
| Pull with rebase           | `git pull --rebase`                                |
| Push                       | `git push`                                         |
| First push                 | `git push -u origin main`                          |
| Continue rebase            | `git rebase --continue`                            |
| Abort rebase               | `git rebase --abort`                               |
| Safe force push            | `git push --force-with-lease`                      |
| View commits               | `git log --oneline`                                |
