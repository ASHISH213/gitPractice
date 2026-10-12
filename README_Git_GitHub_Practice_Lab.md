<div align="center">

# 🚀 Git & GitHub Practice Lab

### A hands-on, beginner-friendly guide to learning Git, GitHub, and real-world version control

**Learn → Practice → Break things safely → Fix them → Build confidence**

<p>
  <img src="https://img.shields.io/badge/Git-Version%20Control-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git">
  <img src="https://img.shields.io/badge/GitHub-Collaboration-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  <img src="https://img.shields.io/badge/Level-Beginner%20to%20Intermediate-2ea44f?style=for-the-badge" alt="Level">
  <img src="https://img.shields.io/badge/Approach-Hands--on-6f42c1?style=for-the-badge" alt="Hands-on">
</p>

**Repository purpose:** A practical notebook for Git and GitHub commands, workflows, troubleshooting, and completed practice tasks.

</div>

---

## 🧭 Learning dashboard

Use this repository as a lab, not just a list of commands. Run each command in your own practice repository and tick off the task only after you have completed it.

| Stage | What you'll learn | Status |
|---|---|---|
| 1 | Setup, configuration, and Git basics | ⬜ Not started |
| 2 | Create a repository and make commits | ⬜ Not started |
| 3 | Connect a local repository to GitHub | ⬜ Not started |
| 4 | Branching, merging, and conflict resolution | ⬜ Not started |
| 5 | Undo changes safely and recover work | ⬜ Not started |
| 6 | Pull requests and collaboration | ⬜ Not started |
| 7 | Tags, releases, `.gitignore`, and history | ⬜ Not started |
| 8 | Advanced workflows and final challenge | ⬜ Not started |

> **Recommended routine:** Learn one concept, run the commands, inspect the result with `git status` or `git log`, and write down what changed.

## 📚 Table of contents

- [1. What are Git and GitHub?](#1-what-are-git-and-github)
- [2. Install and configure Git](#2-install-and-configure-git)
- [3. Understand the Git workflow](#3-understand-the-git-workflow)
- [4. Start a local repository](#4-start-a-local-repository)
- [5. Essential everyday commands](#5-essential-everyday-commands)
- [6. Connect to GitHub](#6-connect-to-github)
- [7. Branches and merging](#7-branches-and-merging)
- [8. Merge conflicts](#8-merge-conflicts)
- [9. Undo, restore, and recover](#9-undo-restore-and-recover)
- [10. Remote repositories and synchronization](#10-remote-repositories-and-synchronization)
- [11. Pull requests and collaboration](#11-pull-requests-and-collaboration)
- [12. `.gitignore`, tags, and releases](#12-gitignore-tags-and-releases)
- [13. Inspect history and compare changes](#13-inspect-history-and-compare-changes)
- [14. Stash and cherry-pick](#14-stash-and-cherry-pick)
- [15. GitHub security and good habits](#15-github-security-and-good-habits)
- [16. Troubleshooting](#16-troubleshooting)
- [17. Practice sessions](#17-practice-sessions)
- [18. Final practical project](#18-final-practical-project)
- [19. Quick command reference](#19-quick-command-reference)
- [20. Learning resources](#20-learning-resources)

---

## 1. What are Git and GitHub?

- **Git** is a distributed version-control system. It records changes to files so you can inspect history, compare versions, create branches, and recover work.
- **GitHub** is a hosting and collaboration platform for Git repositories. It adds pull requests, issues, reviews, project tools, and automation.

| Term | Meaning |
|---|---|
| Repository (repo) | A project tracked by Git |
| Working tree | Files you are currently editing |
| Staging area / index | Changes selected for the next commit |
| Commit | A saved snapshot with a message and identifier |
| Branch | A movable line of development |
| Remote | A named reference to another repository, often on GitHub |
| `origin` | The conventional name for the main remote |
| `HEAD` | The commit or branch position you currently have checked out |
| Merge | Combines histories from different branches |
| Pull request (PR) | A GitHub proposal to review and merge changes |
| Clone | Copies a remote repository to your computer |
| Fetch | Downloads remote history without merging it into your current branch |
| Pull | Fetches changes and integrates them into the current branch |

### The basic lifecycle

```text
Edit files
   ↓
git add
   ↓
Staging area
   ↓
git commit
   ↓
Local repository
   ↓
git push
   ↓
GitHub remote repository
```

A commit is local until you push it. A file being visible in your folder does not automatically mean Git is tracking it.

## 2. Install and configure Git

### Install

- **Windows:** Download Git from [git-scm.com/download/win](https://git-scm.com/download/win). Git Bash is useful, and Git also works from PowerShell.
- **macOS:** Install Xcode Command Line Tools with `xcode-select --install`, or use the installer at [git-scm.com](https://git-scm.com/).
- **Linux:** Use your distribution's package manager, for example `sudo apt install git` on Debian/Ubuntu.

Verify the installation:

```bash
git --version
```

### Set your identity

Use the name and email you want recorded in commits. For GitHub contribution attribution, use an email address associated with your GitHub account or your GitHub-provided `noreply` address.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --global --list
```

Set a default editor if needed:

```bash
# Example: Visual Studio Code
git config --global core.editor "code --wait"
```

> These settings identify commits; they do not sign you in to GitHub. Authentication is configured separately.

## 3. Understand the Git workflow

Git commonly tracks changes through three areas:

1. **Working tree:** edits you make in files.
2. **Staging area:** changes you select using `git add`.
3. **Repository history:** snapshots recorded by `git commit`.

Useful inspection commands:

```bash
git status
git diff
git diff --staged
git log --oneline
```

- `git diff` shows unstaged changes.
- `git diff --staged` shows changes selected for the next commit.
- `git status` summarizes tracked, untracked, staged, and branch state.

## 4. Start a local repository

### Option A: Create a new project

```bash
mkdir git-practice
cd git-practice
git init
git status
```

Create a file named `README.md` and add:

```markdown
# Git Practice

My first repository for learning Git and GitHub.
```

Then:

```bash
git status
git add README.md
git status
git commit -m "Add initial README"
git log --oneline
```

### Option B: Clone an existing repository

```bash
git clone https://github.com/OWNER/REPOSITORY.git
cd REPOSITORY
```

Replace `OWNER` and `REPOSITORY` with the actual account and repository. Cloning normally creates a directory and configures the original repository as `origin`.

## 5. Essential everyday commands

### Inspect and navigate

| Command | Purpose |
|---|---|
| `git status` | Show current changes and branch state |
| `git status --short` | Compact status output |
| `git log` | Show commit history |
| `git log --oneline --graph --decorate --all` | Compact visual history |
| `git show` | Inspect a commit |
| `git diff` | Show unstaged changes |
| `git diff --staged` | Show staged changes |
| `git branch` | List local branches |
| `git branch -a` | List local and remote-tracking branches |
| `git remote -v` | Show remote URLs |

### Stage and commit

```bash
git add README.md        # Stage one file
git add .                # Stage changes under the current directory
git add -p               # Interactively choose parts of changes
git commit -m "Describe the change"
git commit --amend       # Amend the most recent commit; use carefully
```

**Commit-message examples**

```text
Add Git installation notes
Fix typo in branching guide
Update practice session checklist
Document merge conflict resolution
```

Prefer small commits that explain *why* a change was made. `git add .` can stage more than intended, so inspect `git status` before committing.

### Rename and remove tracked files

```bash
git mv old-name.txt new-name.txt
git rm old-name.txt
git rm --cached secret.txt
```

- `git mv` renames a tracked file and stages the change.
- `git rm` removes a file and stages the removal.
- `git rm --cached` removes a file from Git's index but leaves it on disk. Add it to `.gitignore` if appropriate.

## 6. Connect to GitHub

### Method A: Create a GitHub repository, then push

1. Sign in to [GitHub](https://github.com/).
2. Create a **new repository**.
3. If you already have local files, avoid initializing the remote with a README, license, or `.gitignore` unless you know how you will reconcile the histories.
4. In your local project, run the following commands, replacing the URL with your repository URL:

```bash
git remote add origin https://github.com/OWNER/REPOSITORY.git
git remote -v
git branch -M main
git push -u origin main
```

`-u` sets the upstream branch so future pushes can often use `git push`.

### Method B: Clone first, then work

```bash
git clone https://github.com/OWNER/REPOSITORY.git
cd REPOSITORY
# Edit or create files
git add .
git commit -m "Add practice notes"
git push
```

### Authentication: HTTPS or SSH

GitHub does not accept your account password for ordinary Git HTTPS authentication. Use an approved sign-in flow, a credential manager, or a personal access token when prompted by an appropriate tool. **Never put a token directly in a remote URL or commit it to a repository.**

For SSH setup, follow GitHub's current instructions: [Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh). Test with:

```bash
ssh -T git@github.com
```

### Common remote commands

```bash
git remote -v
git remote add origin https://github.com/OWNER/REPOSITORY.git
git remote set-url origin https://github.com/OWNER/REPOSITORY.git
git fetch origin
git push -u origin main
```

If `origin` already exists, use `git remote set-url` rather than adding it again.

## 7. Branches and merging

Branches let you develop a change without immediately changing the main line of work.

### Create and switch branches

```bash
git branch
git switch -c feature/add-notes
# Make changes and commit them
git add .
git commit -m "Add notes feature"
git switch main
```

Older tutorials may use `git checkout -b feature/add-notes`. `git switch` is the more focused command for changing branches.

### Merge a branch

```bash
git switch main
git merge feature/add-notes
git log --oneline --graph --decorate --all
```

Delete a branch after its work is safely merged:

```bash
git branch -d feature/add-notes
```

Delete a remote branch only when you are sure it is no longer needed:

```bash
git push origin --delete feature/add-notes
```

### Branch naming examples

- `feature/add-search`
- `fix/readme-typo`
- `docs/git-workflow`
- `chore/update-dependencies`

## 8. Merge conflicts

A conflict happens when Git cannot automatically combine competing changes, often because the same lines were changed on two branches.

### Practice a conflict safely

1. Create a practice repository and commit a file containing `Status: learning`.
2. Create branch `feature/status` and change the line to `Status: practicing`; commit it.
3. Switch back to `main` and change the same line to `Status: reviewing`; commit it.
4. Merge the feature branch:

```bash
git merge feature/status
```

Git may report a conflict. Open the file. Conflict markers look like:

```text
<<<<<<< HEAD
Status: reviewing
=======
Status: practicing
>>>>>>> feature/status
```

Edit the file to the desired final content and **remove all conflict markers**. Then:

```bash
git status
git add path/to/conflicted-file
git commit
```

If you want to abandon the merge before completing it:

```bash
git merge --abort
```

Do not blindly choose “ours” or “theirs” without understanding which content you want to preserve. Always inspect the final file and run relevant tests.

## 9. Undo, restore, and recover

> **Safety rule:** Before using a destructive command, run `git status` and consider making a backup. Commands that rewrite history can affect collaborators.

| Situation | Command | What it does |
|---|---|---|
| Unstage a file | `git restore --staged FILE` | Removes it from staging; keeps working-tree edits |
| Discard unstaged edits to a tracked file | `git restore FILE` | Replaces working copy with indexed/committed content; local edits may be lost |
| Undo a published commit safely | `git revert COMMIT_ID` | Creates a new commit that reverses the selected commit |
| Move branch back one commit, keeping changes staged | `git reset --soft HEAD~1` | Rewrites local branch history; keeps changes staged |
| Move branch back one commit, keeping changes unstaged | `git reset HEAD~1` | Default mixed reset; keeps file changes in working tree |
| Force working tree and index to a commit | `git reset --hard COMMIT_ID` | Discards tracked changes; destructive |
| Find previous branch positions | `git reflog` | Shows local reference movement history |

Examples:

```bash
git restore --staged README.md
git restore README.md
git revert HEAD
git reflog
```

Use `git revert` for changes already shared with others in most normal cases. Avoid `git reset --hard` unless you fully understand what will be discarded. `git reflog` can help recover a recent local commit or branch position, but it is not a substitute for backups.

## 10. Remote repositories and synchronization

### Fetch versus pull

```bash
git fetch origin
git log --oneline --graph --decorate --all
git pull
```

- `git fetch` downloads remote updates but does not itself merge them into your current branch.
- `git pull` fetches and integrates updates; the integration may use merge or rebase depending on configuration and flags.

### Push your commits

```bash
git status
git push
```

If the branch has no upstream configured:

```bash
git push -u origin YOUR-BRANCH
```

### Handle a rejected push

A rejection often means the remote has commits you do not have locally. First inspect the state:

```bash
git status
git fetch origin
git log --oneline --graph --decorate --all
```

Then integrate the remote changes using the workflow appropriate to the repository. For a simple branch where your team permits rebase:

```bash
git pull --rebase
git push
```

Resolve any conflicts, continue the rebase as instructed by Git, and test before pushing. Do not default to `git push --force`; if a force push is genuinely needed on a branch you own, prefer `--force-with-lease` and understand the impact.

## 11. Pull requests and collaboration

A typical GitHub pull-request workflow:

1. Sync your local `main` branch.
2. Create a descriptive feature branch.
3. Make a focused change and commit it.
4. Push the branch to GitHub.
5. Open a pull request from the branch into `main`.
6. Explain the goal, changes, testing, and any risks.
7. Review the diff and address feedback.
8. Ensure required checks pass, then merge according to the project's policy.
9. Delete the merged branch if it is no longer needed and sync locally.

Example:

```bash
git switch main
git pull
git switch -c docs/improve-git-guide
# Edit files
git diff
git add README.md
git commit -m "Improve Git guide"
git push -u origin docs/improve-git-guide
```

On GitHub, open a pull request and select the correct **base** (`main`) and **compare** (your feature branch). A pull request is a review and merge workflow, not a Git command.

## 12. `.gitignore`, tags, and releases

### Create a `.gitignore`

Example for common local files:

```gitignore
# Environment variables and secrets
.env
.env.*
!.env.example

# Dependencies and build output
node_modules/
dist/
build/

# Logs and local files
*.log
.DS_Store
Thumbs.db
.vscode/
```

Customize this for your technology stack. Do not ignore files the project needs to build, and do not assume `.gitignore` removes files already tracked.

If a file is already tracked and should stop being tracked:

```bash
git rm --cached .env
git add .gitignore
git commit -m "Stop tracking local environment file"
```

If a real secret was committed, removing it in a later commit does **not** make it safe: revoke/rotate it immediately and follow the hosting platform's guidance for sensitive-data removal.

### Tags

Tags identify particular points in history, commonly releases.

```bash
git tag
git tag -a v1.0.0 -m "First stable release"
git show v1.0.0
git push origin v1.0.0
git push origin --tags
```

Use annotated tags for releases in many workflows. GitHub Releases can then be created from a tag in the repository's web interface.

## 13. Inspect history and compare changes

```bash
git log
git log --oneline
git log --oneline --graph --decorate --all
git show HEAD
git show COMMIT_ID
git diff main..feature/add-notes
git diff --stat
git blame README.md
git shortlog -sn
```

- `git log` displays history.
- `git show` inspects a commit or object.
- `git diff` compares content or revisions.
- `git blame` shows the last commit that changed each line; it is a tracing aid, not proof of responsibility.
- `git shortlog -sn` summarizes commit counts by author.

Replace example branch names and IDs with ones that exist in your repository.

## 14. Stash and cherry-pick

### Temporarily set aside uncommitted work

```bash
git stash push -m "WIP: unfinished documentation"
git stash list
git stash show -p
git stash apply
git stash pop
```

- `apply` reapplies a stash but keeps it in the stash list.
- `pop` reapplies it and removes it if the operation succeeds.
- Check for conflicts and verify the result before continuing.

### Copy one commit to another branch

```bash
git log --oneline
git switch target-branch
git cherry-pick COMMIT_ID
```

Cherry-pick applies the changes introduced by a commit onto the current branch, creating a new commit. It can conflict; resolve the files, stage them, and continue or abort as Git instructs.

## 15. GitHub security and good habits

- Never commit passwords, API keys, private keys, access tokens, production `.env` files, or customer data.
- Use least-privilege credentials and rotate a credential immediately if exposed.
- Add a suitable `.gitignore` before creating sensitive local files.
- Keep commits focused and messages meaningful.
- Inspect `git status` and `git diff` before staging and committing.
- Use branches and pull requests for reviewable changes.
- Protect important branches and enable appropriate repository security features.
- Review third-party actions, scripts, and dependencies before trusting them.
- Do not use force-push on shared branches without explicit agreement.
- Remember that a public repository is visible to everyone; never upload confidential company code or information.

## 16. Troubleshooting

### `fatal: not a git repository`

You are not in a directory inside a Git repository, or the repository has not been initialized.

```bash
pwd
git status
cd path/to/your/repository
```

Use `git init` only if you intend to create a new repository in the current directory.

### `Author identity unknown`

Configure the commit identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

### `remote origin already exists`

Inspect and update the remote instead of adding it again:

```bash
git remote -v
git remote set-url origin https://github.com/OWNER/REPOSITORY.git
```

### `src refspec main does not match any`

Often the branch name differs or no commit exists yet:

```bash
git status
git branch --show-current
git log --oneline
```

Create and commit the initial content, confirm the branch name, then push the correct branch.

### `Permission denied (publickey)`

SSH authentication is not configured correctly or the wrong key is being used. Follow GitHub's [SSH troubleshooting guide](https://docs.github.com/en/authentication/troubleshooting-ssh).

### Merge conflict

Inspect `git status`, edit each conflicted file, remove conflict markers, stage the resolved files, then complete the merge or rebase as Git instructs.

### Accidentally committed the wrong file

If the commit is local and not shared, carefully choose a restore/reset approach after inspecting status and history. If it contains a credential, revoke it immediately. If it was pushed, coordinate with collaborators before rewriting history.

---

## 17. Practice sessions

Complete the sessions in order. Use a disposable practice repository so mistakes are safe. Check off a task only after you have run the commands and inspected the result.

### Session 1 — Setup and first commit

- [ ] Install Git and run `git --version`.
- [ ] Configure your name and email.
- [ ] Create a directory named `git-practice-lab`.
- [ ] Run `git init`.
- [ ] Create `README.md` with a project title and description.
- [ ] Run `git status`, `git add README.md`, and `git commit -m "Add initial README"`.
- [ ] Inspect the result with `git log --oneline`.

**Success criteria:** You can explain the difference between a working-tree change, a staged change, and a commit.

### Session 2 — Track edits and compare changes

- [ ] Add a section named `Learning goals` to `README.md`.
- [ ] Run `git diff` before staging.
- [ ] Stage the file and run `git diff --staged`.
- [ ] Commit the change with a meaningful message.
- [ ] Use `git show HEAD` to inspect the latest commit.
- [ ] Make another edit, then unstage it with `git restore --staged README.md` (after staging it).
- [ ] Confirm the edit remains in your working tree.

**Success criteria:** You can explain why staging gives you control over what enters a commit.

### Session 3 — Publish to GitHub

- [ ] Create an empty repository on GitHub.
- [ ] Add the remote using `git remote add origin YOUR_REPOSITORY_URL`.
- [ ] Confirm it with `git remote -v`.
- [ ] Push the `main` branch using `git push -u origin main`.
- [ ] Refresh GitHub and verify the files and commit history.
- [ ] Make a local edit, commit it, and push again.

**Success criteria:** Your local repository and GitHub repository show the expected commit history.

### Session 4 — Branch and merge

- [ ] Create `feature/profile`.
- [ ] Add a `profile.md` file and commit it on that branch.
- [ ] Switch to `main` and verify `profile.md` is not present there (unless you created it separately).
- [ ] Merge `feature/profile` into `main`.
- [ ] Inspect the result with `git log --oneline --graph --decorate --all`.
- [ ] Delete the local feature branch after confirming the merge.

**Success criteria:** You can explain why branches help isolate work.

### Session 5 — Resolve a merge conflict

- [ ] Create a text file with one simple status line and commit it.
- [ ] Create a branch and change that same line; commit the change.
- [ ] On `main`, change the same line differently and commit it.
- [ ] Merge the feature branch and inspect the conflict.
- [ ] Resolve the file manually, remove conflict markers, and complete the merge.
- [ ] Confirm `git status` is clean and the final content is correct.

**Success criteria:** You can resolve a conflict without losing either intended change.

### Session 6 — Undo safely

- [ ] Create and commit a file named `undo-practice.txt`.
- [ ] Edit it without committing and inspect `git diff`.
- [ ] Use `git restore undo-practice.txt` only after confirming you no longer need those uncommitted edits.
- [ ] Make a new commit and use `git revert COMMIT_ID` to reverse it.
- [ ] Inspect `git log --oneline`.
- [ ] Run `git reflog` and explain what it records.

**Success criteria:** You understand the difference between restoring file content, reverting a commit, and resetting a branch.

### Session 7 — `.gitignore` and repository hygiene

- [ ] Add `.env` and `*.log` to `.gitignore`.
- [ ] Create a dummy `.env` containing **fake, non-secret sample data only**.
- [ ] Run `git status` and verify the `.env` file is ignored.
- [ ] Add a safe `.env.example` containing placeholder values.
- [ ] Commit the `.gitignore` and `.env.example`.
- [ ] Confirm no credentials or private data appear in GitHub.

**Success criteria:** You can distinguish a local configuration file from a safe example template.

### Session 8 — Pull request workflow

- [ ] Create a branch named `docs/pr-practice`.
- [ ] Make a small documentation improvement.
- [ ] Commit and push the branch.
- [ ] Open a pull request on GitHub with a useful title and description.
- [ ] Review the changed files and diff.
- [ ] Merge the PR using the repository's available merge option.
- [ ] Sync your local `main` and remove the feature branch if appropriate.

**Success criteria:** You can describe the full branch → push → pull request → review → merge workflow.

### Session 9 — Stash and recover work

- [ ] Make an uncommitted edit.
- [ ] Save it with `git stash push -m "practice stash"`.
- [ ] Confirm the working tree is clean.
- [ ] View the stash list and inspect the patch.
- [ ] Reapply the change with `git stash apply`.
- [ ] Confirm the edit is back and understand when to use `apply` versus `pop`.

**Success criteria:** You can temporarily set work aside without creating a commit.

### Session 10 — Tags and release

- [ ] Confirm your working tree is clean.
- [ ] Create an annotated tag named `v1.0.0`.
- [ ] Inspect it with `git show v1.0.0`.
- [ ] Push the tag to GitHub.
- [ ] Create a GitHub Release from the tag if the repository workflow calls for it.

**Success criteria:** You can explain how a tag identifies a specific point in history.

---

## 18. Final practical project

### 🎯 Build a version-controlled documentation project

Create a repository named `git-github-handbook` containing:

```text
git-github-handbook/
├── README.md
├── commands/
│   ├── everyday-commands.md
│   ├── branching-and-merging.md
│   └── undo-and-recovery.md
├── practice/
│   ├── session-checklist.md
│   └── troubleshooting.md
├── .gitignore
└── LICENSE
```

### Requirements

- [ ] Write a clear root README with a table of contents.
- [ ] Make at least 10 meaningful commits.
- [ ] Use at least 3 feature/documentation branches.
- [ ] Merge a branch using a pull request.
- [ ] Resolve one intentional merge conflict.
- [ ] Add and verify a `.gitignore`.
- [ ] Demonstrate a safe `git revert`.
- [ ] Create and push an annotated version tag.
- [ ] Add screenshots or terminal output to document your learning (never include secrets).
- [ ] Finish with a clean working tree and a useful project description on GitHub.

### Self-assessment

Give yourself one point for each completed requirement above.

- **0–3:** Repeat the setup and everyday-command sessions.
- **4–7:** Practice branches, conflicts, and undo commands.
- **8–10:** You have a good foundation; practice collaboration and troubleshooting on a team-style project.

This is a learning checklist, not a professional certification.

## 19. Quick command reference

| Goal | Command |
|---|---|
| Check version | `git --version` |
| Initialize repo | `git init` |
| Clone repo | `git clone URL` |
| Check status | `git status` |
| Stage a file | `git add FILE` |
| Commit staged changes | `git commit -m "Message"` |
| See history | `git log --oneline` |
| See all branch history | `git log --oneline --graph --decorate --all` |
| See working-tree changes | `git diff` |
| See staged changes | `git diff --staged` |
| List branches | `git branch` |
| Create and switch branch | `git switch -c BRANCH` |
| Switch branch | `git switch BRANCH` |
| Merge branch into current branch | `git merge BRANCH` |
| Add remote | `git remote add origin URL` |
| List remotes | `git remote -v` |
| Download remote updates | `git fetch origin` |
| Integrate remote updates | `git pull` |
| Push branch | `git push` |
| First push with upstream | `git push -u origin BRANCH` |
| Unstage file | `git restore --staged FILE` |
| Discard unstaged file edits | `git restore FILE` |
| Revert a commit | `git revert COMMIT_ID` |
| View recovery history | `git reflog` |
| Stash changes | `git stash push -m "message"` |
| Reapply stash | `git stash apply` |
| Create annotated tag | `git tag -a v1.0.0 -m "Release"` |
| Push one tag | `git push origin v1.0.0` |
| Show current branch | `git branch --show-current` |

Replace placeholders such as `FILE`, `BRANCH`, `URL`, and `COMMIT_ID` with real values. Do not copy destructive commands blindly.

## 20. Learning resources

- [Official Git website](https://git-scm.com/)
- [Pro Git book — free online](https://git-scm.com/book/en/v2)
- [Git reference](https://git-scm.com/docs)
- [GitHub Docs](https://docs.github.com/)
- [GitHub Skills — interactive courses](https://skills.github.com/)
- [GitHub: Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
- [GitHub: About pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

---

<div align="center">

### ⭐ Keep practicing

**The goal isn't to memorize every command. It's to understand the state of your repository, inspect before you act, and know how to recover safely.**

If this guide helps you, consider starring the repository and improving these notes as you learn.

</div>
