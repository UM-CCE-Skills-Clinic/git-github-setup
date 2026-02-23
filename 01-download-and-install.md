# Step 1: Download and Install Git

---

## Windows

### Option A: Using the Installer (Recommended for Beginners)

**Step 1.** Open your browser and go to:

```
https://git-scm.com/download/win
```

**Step 2.** The download should start automatically. If not, click the link for the 64-bit version.

**Step 3.** Run the downloaded `.exe` file.

**Step 4.** Follow the installer wizard. The default options are fine. Click **Next** on each screen, then click **Install**.

**Step 5.** Once installation is complete, click **Finish**.

**Step 6.** Verify the installation. Open **Command Prompt** or **PowerShell** and run:

```bash
git --version
```

Expected output (version number may differ):

```
git version 2.47.0.windows.2
```

---

### Option B: Using winget (Windows Package Manager)

**Step 1.** Open **PowerShell** or **Command Prompt**.

**Step 2.** Run:

```bash
winget install --id Git.Git -e --source winget
```

**Step 3.** Verify the installation:

```bash
git --version
```

---

### PowerShell Execution Policy Fix (Windows Only)

If you run a command in PowerShell and see an error like:

```
cannot be loaded because running scripts is disabled on this system
```

Fix it by running this command in PowerShell:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

When prompted, type `Y` and press **Enter**.

This allows locally created scripts to run and remote scripts to run only if they are signed. It only affects your user account, not the entire system.

---

## macOS

### Option A: Using Homebrew (Recommended)

**Step 1.** If you do not have Homebrew installed, open **Terminal** and run:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Step 2.** Install Git:

```bash
brew install git
```

**Step 3.** Verify the installation:

```bash
git --version
```

---

### Option B: Using Xcode Command Line Tools

**Step 1.** Open **Terminal** and run:

```bash
git --version
```

**Step 2.** If Git is not installed, macOS will prompt you to install the Xcode Command Line Tools. Click **Install** and follow the prompts.

**Step 3.** Once complete, verify:

```bash
git --version
```

---

## Linux

### Ubuntu / Debian

**Step 1.** Open a terminal.

**Step 2.** Update your package list:

```bash
sudo apt update
```

**Step 3.** Install Git:

```bash
sudo apt install git -y
```

**Step 4.** Verify the installation:

```bash
git --version
```

---

### Fedora / RHEL / CentOS

**Step 1.** Open a terminal.

**Step 2.** Install Git:

```bash
sudo dnf install git -y
```

**Step 3.** Verify the installation:

```bash
git --version
```

---

### Arch Linux

**Step 1.** Open a terminal.

**Step 2.** Install Git:

```bash
sudo pacman -S git
```

**Step 3.** Verify the installation:

```bash
git --version
```

---

## All Platforms: Verify Git is Ready

Run this command in your terminal:

```bash
git --version
```

If a version number is printed, Git is installed and ready. Proceed to the next step.

---

**Next:** [Step 2 - Setup and Configuration](./02-setup.md)
