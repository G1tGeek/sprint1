

# GitHub Setup Documentation

![logo](https://miro.medium.com/v2/resize:fit:1125/1*E-TJsd6C1rwWMiiLJt5xxA.png)

### Author
| Created     | Version | Author        | Modifed | Comment           | Reviewer   |
|-------------|---------|---------------|-------|------------|------------------|
| 27-04-2025  |  V1        | Yuvraj Singh |            | Internal Review   | Siddharth Pawar  |
| 29-04-2025  |  V2        | Yuvraj Singh |            | L0 Review         | Naveen Haswani |
|             |  V3        | Yuvraj Singh |            | L1 Review         | Deepak Nishad |
|             |  V4        | Yuvraj Singh |            | L2 Review         | Ashwani Singh |

---

## Table of Contents

<details>
<summary>1. Introduction</summary>

- [Introduction](#introduction)  
- [What is GitHub](#what-is-github)  
- [Why GitHub](#why-github)

</details>

<details>
<summary>2. Requirements</summary>

- [Pre-requisites](#pre-requisites)  
- [Software Overview](#software-overview)  
- [System Requirement](#system-requirement)  
- [Important Ports](#important-ports)

<details>
  <summary>Dependencies</summary>

  - [Run-time Dependency](#run-time-dependency)  
  - [Other Dependency](#other-dependency)

</details>

</details>

<details>
<summary>3. Setup Guide</summary>

- [How to Setup/Install GitHub](#how-to-setupinstall-github)  
- [Configuration](#configuration)

</details>

<details>
<summary>4. Wrap-up</summary>

- [Conclusion](#conclusion)  
- [Contact](#contact)  
- [References](#references)

</details>

---

## Introduction

This document provides a structured guide for setting up GitHub, a widely used cloud-based version control and collaboration platform. It is designed following a software documentation template to ensure clarity, organization, and ease of understanding for users and teams establishing their GitHub workflows. 

## What is Github

For detailed understanding of Github [click here.](https://github.com/snaatak-Downtime-Crew/Documentation/blob/SCRUMS-93-PRINCE/vcs_design%20%2B%20poc/features%20of%20vcs/github%20features/README.md)

## Why GitHub

To understand why GitHub is our choice for VCS during this project [click here.](https://github.com/snaatak-Downtime-Crew/Documentation/blob/SCRUMS-95-Vardaan/vcs_design%20%2B%20poc/features%20of%20vcs/conclusion%20document/README.md)


## Pre-requisites

| License Type        | Description                                             | Commercial Use | Open Source |
|---------------------|---------------------------------------------------------|----------------|-------------|
| GitHub Free / Paid Plans | Offers free public/private repositories; paid plans offer more features. | Yes            | Yes         |

## Software Overview

| Software | Version |
|----------|---------|
| Git      | 2.43.0 (or latest stable) |
| GitHub   | Web-based service (always latest) |

## System Requirement

| Requirement           | Minimum Recommendation            |
|------------------------|-----------------------------------|
| Processor/Instance Type | Dual-Core / T2.micro instance      |
| RAM                    | 2 Gigabytes or Higher             |
| ROM (Disk Space)       | 5 Gigabytes or Higher             |
| OS Required            | Linux (Ubuntu 20.04 or later) / Windows 10 or later / macOS |

## Important Ports

| Ports | Description |
|-------|-------------|
| 443   | Used for secure HTTPS connection to GitHub servers. |
| 22    | (Optional) Used for SSH connection to GitHub repositories. |

## Dependencies

### Run-time Dependency

| Run-time Dependency | Version | Description                                  |
|---------------------|---------|----------------------------------------------|
| Git                 | 2.43.0  | Required to manage repositories locally.     |

### Other Dependency

| Other Dependency | Version | Description                   |
|------------------|---------|-------------------------------|
| OpenSSH          | 8.0+    | Needed for SSH authentication to GitHub. |

## How to Setup/Install GitHub

### Step-by-Step Installation Instructions

1. **Update your system** 
[Go to this link for ubuntu basic commands.](https://github.com/snaatak-Downtime-Crew/Documentation/blob/main/common_stack/operating_system/ubuntu/sop/commoncommands/README.md#1-basic-system-commands)

2. **Install Git**:

   ```
   sudo apt install git && git --version
   ```

4. **Create a GitHub Account**:

   - Visit [https://github.com/](https://github.com/) and sign up.

6. **Configure Git Locally**:

   ```
   git config --global user.name "Your Name"
   git config --global user.email "youremail@example.com"
   ```

8. **Generate and Add SSH Key (Recommended)**:

   ```
   ssh-keygen -t ed25519 -C "youremail@example.com"
   ```
   - Copy the public key and add it to GitHub → Settings → SSH and GPG keys.

10. **Clone or Create a Repository**:
   
   ```
   git clone git@github.com:username/repository.git
   ```

11. **Basic Git Commands**:
   
   - `git add .` → Add changes
   - `git commit -m "your message"` → Commit changes
   - `git push origin main` → Push changes to GitHub

## Configuration

Configuration refers to setting up Git locally and linking it securely to GitHub.

- Set default branch name (optional):
  ```
  git config --global init.defaultBranch main
  ```
- Setup credential helper for GitHub CLI authentication:
  ```
  gh auth login
  ```
- (Optional) Set custom Git aliases for faster workflows:
  ```bash
  git config --global alias.co checkout
  git config --global alias.br branch
  git config --global alias.cm commit
  ```

## Conclusion
 Configuring Git and GitHub properly does not only improves productivity but also enhances code security, traceability, and project scalability. Whether working individually or within a team, GitHub's ecosystem empowers developers to build, test, and deploy projects with greater confidence and agility.

## Contact

| Name| Email Address      |
|-----|--------------------------|
| Yuvraj Singh | yuvraj.singh.snaatak@mygurukulam.co |


## References

| Source                                                                                     | Description                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------ |
| GitHub Official Documentation | [Visit](https://docs.github.com/en) |
| Pro Git Book | [Visit](https://git-scm.com/book/en/v2) |
| GitHub CLI Documentation | [Visit](https://cli.github.com/manual/) | 
| Git Installation Guide | [Visit](https://git-scm.com/downloads) | 
| GitHub SSH Key Setup Guide | [Visit](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) | 
