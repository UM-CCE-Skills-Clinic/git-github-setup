# Step 3: Your First Commit

These commands work the same on Windows, macOS, and Linux.
Open your terminal (**Command Prompt**, **PowerShell**, or **Git Bash** on Windows; **Terminal** on macOS/Linux).

---

## 3.1 Create a Repository on GitHub

**Step 1.** Go to [github.com](https://github.com) and sign in.

**Step 2.** Click the **+** icon in the top-right corner.

**Step 3.** Click **New repository**.

**Step 4.** Fill in the repository details:
- **Repository name**: Enter a name, for example `my-first-repo`
- **Description**: Optional. Add a short description.
- **Visibility**: Choose **Public** or **Private**.

**Step 5.** Leave all checkboxes unchecked (do not initialize with README, .gitignore, or license). You will add files from your local machine.

**Step 6.** Click **Create repository**.

**Step 7.** On the next screen, GitHub shows you setup instructions. Look for the **SSH** tab and copy the repository URL. It will look like:

```
git@github.com:yourusername/my-first-repo.git
```

Keep this tab open. You will need this URL in a later step.

---

## 3.2 Create a Local Project Folder

**Step 1.** Open your terminal.

**Step 2.** Navigate to the location where you want to create your project. For example, to go to your Desktop:

- Windows:
  ```bash
  cd ~/Desktop
  ```
- macOS / Linux:
  ```bash
  cd ~/Desktop
  ```

**Step 3.** Create a new folder:

```bash
mkdir my-first-repo
```

**Step 4.** Enter the folder:

```bash
cd my-first-repo
```

---

## 3.3 Initialize a Git Repository

**Step 1.** Inside your project folder, run:

```bash
git init
```

Expected output:

```
Initialized empty Git repository in /path/to/my-first-repo/.git/
```

This creates a hidden `.git` folder that Git uses to track changes.

---

## 3.4 Create Your First File

**Step 1.** Create a `README.md` file:

- Windows (Command Prompt):
  ```bash
  echo # My First Repo > README.md
  ```

- Windows (PowerShell):
  ```powershell
  "# My First Repo" | Out-File -Encoding utf8 README.md
  ```

- macOS / Linux:
  ```bash
  echo "# My First Repo" > README.md
  ```

**Step 2.** Confirm the file was created:

```bash
ls
```

You should see `README.md` listed.

---

## 3.5 Stage the File

Staging prepares files to be included in your next commit.

**Step 1.** Add your file to the staging area:

```bash
git add README.md
```

To stage all files at once (useful when you have multiple files):

```bash
git add .
```

**Step 2.** Check the status to see what is staged:

```bash
git status
```

Expected output:

```
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```

---

## 3.6 Make Your First Commit

A commit saves a snapshot of the staged changes with a message.

**Step 1.** Run:

```bash
git commit -m "Initial commit"
```

Expected output:

```
[main (root-commit) a1b2c3d] Initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
```

---

## 3.7 Connect Your Local Repository to GitHub

**Step 1.** Use the SSH URL you copied from GitHub in Step 3.1. Run:

```bash
git remote add origin git@github.com:yourusername/my-first-repo.git
```

Replace `yourusername` and `my-first-repo` with your actual GitHub username and repository name.

**Step 2.** Confirm the remote was added:

```bash
git remote -v
```

Expected output:

```
origin  git@github.com:yourusername/my-first-repo.git (fetch)
origin  git@github.com:yourusername/my-first-repo.git (push)
```

---

## 3.8 Push to GitHub

**Step 1.** Push your local commit to GitHub:

```bash
git push -u origin main
```

The `-u` flag sets `origin main` as the default upstream so future pushes only require `git push`.

Expected output:

```
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 234 bytes | 234.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:yourusername/my-first-repo.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

**Step 2.** Go to your repository page on GitHub and refresh. Your `README.md` file should now be visible.

---

## Quick Reference: Daily Git Workflow

After your first commit is done, this is the typical flow for making changes:

```bash
# 1. Check what changed
git status

# 2. Stage your changes
git add .

# 3. Commit with a message
git commit -m "Describe what you changed"

# 4. Push to GitHub
git push
```

---

**Previous:** [Step 2 - Setup and Configuration](./02-setup.md)
**Back to Start:** [README](./README.md)
