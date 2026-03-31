# 🚀 DevSecOps End-To-End Pipeline Project (Simple Explanation)

This project demonstrates how to automatically **Code -> Build -> Test -> deploy a website using GitHub Actions with a Github Action approach**.

The website is automatically deployed to **EC2 Server** whenever code is pushed to the repository.

This project is part of my **DevOps learning journey** to practice CI/CD automation and DevSecOps workflows.

---

# 📌 Project Overview

This repository shows how developers can:

- Automate deployment using **GitHub Actions**
- Use **Git as the single source of truth (GitOps)**
- Deploy a static website automatically to **GitHub Pages**
- Trigger CI/CD pipelines on every code push

---

# 🏗️ Project Architecture
```bash
Developer Push Code
│
▼
GitHub Repository
│
▼
GitHub Actions Workflow
│
▼
Build & Push to dockerhub
│
▼
Test code quality
│
▼
Deploy Process
│
▼
EC2 Hosting

```
---

# ⚙️ Tech Stack

- Version Control: **Git & GitHub**
- CI/CD Tool: **GitHub Actions**
- Code Quality: **flake8**
- Deployment Platform: **EC2 Instance**
- Workflow Language: **YAML**
- Approach: **GitOps**

---

# 📂 Project Structure
github-actions-practice
```bash
│
├── index.html
├── style.css
├── script.js
│
└── .github
└── workflows
└── deploy.yml
```

### Important Folder

`.github/workflows/`

This directory contains the **GitHub Actions workflow files** that define the CI/CD pipeline.

---

## 🔄 CI/CD Workflow Explanation (Step-by-Step)

```bash
name: portfolio-deploy

on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  id-token: write
  pages: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deploy-pages.outputs.page_url }}

    steps:
      #Get access to your portfolio code via pre built action
      #Clone the code from github
      #Step = 1
      - name: checkout code
        uses: actions/checkout@v4

      #Step = 2
      #Setup Github pages
      - name: Setup github pages
        uses: actions/configure-pages@v4

      #Step = 3
      #Static code artifacts
      - name: Upload static files
        uses: actions/upload-pages-artifact@v4
        with:
          path: "." #Path to your static code artifacts, in this case the root directory of the repository

      #Step = 4
      #Deploy to Github pages
      - name: Deploy to Github pages
        uses: actions/deploy-pages@v4
        with:
          url: ${{ steps.deploy-pages.outputs.page_url }}

```
This triggers the GitHub Actions pipeline.

## Build or Prepare Website
The workflow automatically deploys the website to GitHub Pages.



Example:
```bash
(https://username.github.io/repository-name)
```

## 🎯 Key Learnings
Through this project, I learned:

  - How to build CI/CD pipelines using GitHub Actions
  - How GitOps works using Git as the source of truth
  - How to automate deployments
  - How GitHub Pages hosting works
  - How YAML workflow pipelines are structured

## 🚀 Why GitHub Actions Instead of Jenkins?
Many organizations prefer GitHub Actions because:

- Native integration with GitHub repositories
- No server maintenance required
- Simple YAML configuration
- Large marketplace of reusable actions
- Faster setup for CI/CD pipelines
