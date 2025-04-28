# Proof of Concept Pull Request on GitHub
![image](https://github.com/user-attachments/assets/41fd50ae-607d-4273-85fa-d0b9bcd4228b)

### Author
| Created     | Version | Author        | Modifed | Comment           | Reviewer   |
|-------------|---------|---------------|-------|------------|------------------|
| 28-04-2025  | V1      | Yuvraj Singh |  | Internal Review   | Siddharth Pawar  |

## Table of Content

- [Introduction](#introduction)
- [Pull Request via GitHub GUI (Web Interface)](#pull-request-via-github-gui-web-interface)
  - [Step 1: Clone a GitHub Repository](#step-1-clone-a-github-repository)
  - [Step 2: Create a New Branch](#step-2-create-a-new-branch)
  - [Step 3: Make Changes](#step-3-make-changes)
  - [Step 4: Push Your Branch](#step-4-push-your-branch)
  - [Step 5: Open GitHub Website](#step-5-open-github-website)
  - [Step 6: Fill in PR Details](#step-6-fill-in-pr-details)
- [Pull Request via GitHub CLI (`gh`)](#pull-request-via-github-cli-gh)
  - [Step 1: Install and Authenticate GitHub CLI](#step-1-install-and-authenticate-github-cli)
  - [Step 2: Setup](#step-2-setup)
  - [Step 3: Create Pull Request Using `gh`](#step-3-create-pull-request-using-gh)
  - [Step 4: Confirm](#step-4-confirm)
- [Quick Comparison Table](#quick-comparison-table)
- [Conclusion](#conclusion)
- [Contact](#contact)
- [References](#references)

----
## Introduction

This guide focuses on the process of creating Pull Requests using both the GitHub web interface (GUI) and the GitHub Command Line Interface (CLI), providing step-by-step instructions for each method to facilitate efficient collaboration and code integration.

---

## Pull Request via GitHub GUI (Web Interface)

### Step 1: Clone a GitHub Repository

```
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

### Step 2: Create a New Branch
```bash
git checkout -b feature/my-new-feature
```

### Step 3: Make Changes
Example:
```bash
echo "Hello World!" > hello.txt
git add hello.txt
git commit -m "Add hello.txt file"
```

### Step 4: Push Your Branch
```bash
git push origin feature/my-new-feature
```

### Step 5: Open GitHub Website
- Navigate to your repository on GitHub.
- GitHub will show a banner with a "Compare & pull request" button. Click it.

Alternatively:
- Go to the **Pull Requests** tab.
- Click **New Pull Request**.
- Choose **base branch** (e.g., `main`) and **compare branch** (`feature/my-new-feature`).
- Click **Create Pull Request**.

### Step 6: Fill in PR Details
- Title: `Add hello.txt file`
- Description: `Created a simple hello.txt file.`
- Click **Create Pull Request**.

Pull Request creation is complete.

---

## Pull Request via GitHub CLI (`gh`)

### Step 1: Install and Authenticate GitHub CLI
Install:
```bash
sudo apt install gh          # Ubuntu/Debian
brew install gh              # MacOS
choco install gh             # Windows
```

Login:
```bash
gh auth login
```
Follow the prompts to authenticate.

### Step 2: Setup
- Create a branch
- Make changes
- Push the branch to GitHub

(Steps are identical to those mentioned above.)

### Step 3: Create Pull Request Using `gh`
Simple interactive mode:
```bash
gh pr create
```
- It will ask for:
  - Base branch (e.g., `main`)
  - Head branch (e.g., `feature/my-new-feature`)
  - PR title and body

Or, non-interactive command:
```bash
gh pr create --base main --head feature/my-new-feature --title "Add hello.txt file" --body "Created a simple hello.txt file."
```

### Step 4: Confirm
You can view the PR in a browser:
```bash
gh pr view --web
```

Pull Request creation is complete.

---

## Quick Comparison Table

| Step                   | GitHub GUI                                  | GitHub CLI (`gh`)                               |
|-------------------------|--------------------------------------------|-------------------------------------------------|
| Push branch             | Push normally                              | Push normally                                  |
| Create PR               | Website ➔ Compare & PR button              | `gh pr create` or `gh pr create --base --head`  |
| Fill PR details         | Web form                                   | Command line flags or interactive prompts       |
| View PR                 | On GitHub website                         | `gh pr view --web`                              |

---

## Conclusion
Both these approaches enable developers to contribute changes efficiently, with the CLI offering a faster, scriptable method especially useful for power users and automated workflows.
Understanding both methods ensures flexibility and productivity, depending on the development environment and use case.

---

## Contact

| Name| Email Address      |
|-----|--------------------------|
| Yuvraj Singh | yuvraj.singh.snaatak@mygurukulam.co |

---

## References

| Source                                                                                     | Description                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------ |
| GitHub Docs - About Pull Requests | [visit](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) |
| GitHub CLI Documentation | [visit](https://cli.github.com/manual/) | 
| GitHub Docs - Creating a Pull Request | [visit](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) | 
