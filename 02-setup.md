# Step 2: Setup and Configuration

These commands work the same on Windows, macOS, and Linux unless noted otherwise.
Open your terminal (**Command Prompt**, **PowerShell**, or **Git Bash** on Windows; **Terminal** on macOS/Linux).

---

## 2.1 Set Your Username

Use your GitHub username exactly as it appears on your GitHub profile.

**Step 1.** Run:

```bash
git config --global user.name "your-github-username"
```

Replace `your-github-username` with your GitHub username. Keep the quotes.

**Step 2.** Confirm it was saved:

```bash
git config --global user.name
```

Expected output:

```
your-github-username
```

---

## 2.2 Set Your Email

Use the email address associated with your GitHub account. You can find it at github.com > Settings > Emails.

**Step 1.** Run:

```bash
git config --global user.email "your-github-email@example.com"
```

Replace `your-github-email@example.com` with your GitHub account email. Keep the quotes.

**Step 2.** Confirm it was saved:

```bash
git config --global user.email
```

Expected output:

```
your-github-email@example.com
```

---

## 2.3 Set the Default Branch Name to Main

This ensures new repositories use `main` instead of the older default `master`.

**Step 1.** Run:

```bash
git config --global init.defaultBranch main
```

**Step 2.** Confirm it was saved:

```bash
git config --global init.defaultBranch
```

Expected output:

```
main
```

---

## 2.4 Generate an SSH Key

An SSH key lets you connect to GitHub securely without typing your password each time.

**Step 1.** Run the following command. Replace `your-github-email@example.com` with your GitHub account email:

```bash
ssh-keygen -t ed25519 -C "your-github-email@example.com"
```

**Step 2.** You will see:

```
Enter file in which to save the key (/home/youruser/.ssh/id_ed25519):
```

Press **Enter** to accept the default location.

**Step 3.** You will see:

```
Enter passphrase (empty for no passphrase):
```

You can press **Enter** to skip (no passphrase) or type a passphrase for extra security. If you set a passphrase, you will need to enter it the first time you use the key per session.

**Step 4.** Press **Enter** again to confirm the passphrase (or leave blank again if you skipped it).

You will see output like:

```
Your identification has been saved in /home/youruser/.ssh/id_ed25519
Your public key has been saved in /home/youruser/.ssh/id_ed25519.pub
```

---

## 2.5 Start the SSH Agent and Add Your Key

The SSH agent holds your key in memory so you do not need to enter your passphrase repeatedly.

### Windows (Git Bash)

**Step 1.** Start the SSH agent:

```bash
eval "$(ssh-agent -s)"
```

**Step 2.** Add your private key:

```bash
ssh-add ~/.ssh/id_ed25519
```

### Windows (PowerShell)

**Step 1.** Start the SSH agent service:

```powershell
Get-Service -Name ssh-agent | Set-Service -StartupType Manual
Start-Service ssh-agent
```

**Step 2.** Add your private key:

```powershell
ssh-add $env:USERPROFILE\.ssh\id_ed25519
```

### macOS

**Step 1.** Start the SSH agent:

```bash
eval "$(ssh-agent -s)"
```

**Step 2.** Add your key to the agent and keychain:

```bash
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

Note: On older macOS versions use `-K` instead of `--apple-use-keychain`.

### Linux

**Step 1.** Start the SSH agent:

```bash
eval "$(ssh-agent -s)"
```

**Step 2.** Add your private key:

```bash
ssh-add ~/.ssh/id_ed25519
```

---

## 2.6 Copy Your SSH Public Key

You need to copy the contents of your public key file to paste it into GitHub.

### Windows (Git Bash or PowerShell)

```bash
cat ~/.ssh/id_ed25519.pub
```

Select and copy the entire output, starting from `ssh-ed25519` to the end of the line.

Or use this to copy directly to clipboard (PowerShell):

```powershell
Get-Content $env:USERPROFILE\.ssh\id_ed25519.pub | Set-Clipboard
```

### macOS

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

The key is now copied to your clipboard.

### Linux

```bash
cat ~/.ssh/id_ed25519.pub
```

Select and copy the entire output. Or if `xclip` is installed:

```bash
xclip -selection clipboard < ~/.ssh/id_ed25519.pub
```

---

## 2.7 Add Your SSH Key to GitHub

**Step 1.** Open your browser and go to [github.com](https://github.com). Sign in.

**Step 2.** Click your profile picture in the top-right corner.

**Step 3.** Click **Settings**.

**Step 4.** In the left sidebar, click **SSH and GPG keys**.

**Step 5.** Click the green **New SSH key** button.

**Step 6.** In the **Title** field, enter a name to identify this key. Use something descriptive like `Work Laptop` or `Home PC`.

**Step 7.** In the **Key** field, paste your public key. It should look like:

```
ssh-ed25519 AAAAC3Nza... your-github-email@example.com
```

**Step 8.** Click **Add SSH key**.

**Step 9.** If prompted, enter your GitHub password to confirm.

---

## 2.8 Test the SSH Connection

**Step 1.** Run:

```bash
ssh -T git@github.com
```

**Step 2.** If this is your first time connecting, you will see:

```
The authenticity of host 'github.com' can't be established.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Type `yes` and press **Enter**.

**Step 3.** Expected success output:

```
Hi yourusername! You've successfully authenticated, but GitHub does not provide shell access.
```

If you see your GitHub username in that message, the SSH connection is working correctly.

---

**Previous:** [Step 1 - Download and Install](./01-download-and-install.md)
**Next:** [Step 3 - Your First Commit](./03-first-commit.md)
