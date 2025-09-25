# ![Sanity Checks](https://img.shields.io/badge/Sanity-Checks-Active-brightgreen)

![Workflow Status](https://img.shields.io/github/actions/workflow/status/your-repo/Sanity-Checks.yml?branch=main)

## 🚀 Overview

**Sanity-Checks** automates linting, testing, and building for multi-language repositories. Supported languages:

| Language | Lint | Test | Build |
|----------|------|------|-------|
| JS/TS/Vue | ESLint / Prettier | npm test | npm build |
| Java | Checkstyle | Maven test | Maven package |
| C/C++ | cppcheck | Custom scripts | make / g++ |
| Rust | Clippy | cargo test | cargo build |
| Swift | SwiftLint | swift test | swift build |

---

## 📌 Features

- Detects changes by language and runs only relevant checks
- Linting, testing, and building jobs for multiple languages
- Optional PR labelling with `Sanity Check`
- Supports push to main or pull requests
- Caches dependencies for faster CI

---

## 📖 Workflow Diagram

```mermaid
flowchart LR
    A[Developer Push / PR] --> B{Detect Changed Files by Language}
    B --> C[Run JS/TS/Vue Lint & Tests]
    B --> D[Run Java Lint & Tests]
    B --> E[Run C/C++ Lint & Tests]
    B --> F[Run Rust Lint & Tests]
    B --> G[Run Swift Lint & Tests]
    C --> H{All Jobs Passed?}
    D --> H
    E --> H
    F --> H
    G --> H
    H -->|Yes| I[Add 'Sanity Check' Label to PR]
    H -->|No| J[Check Logs & Fix Errors]
⚡ Getting Started

Create workflow folder:

.github/workflows/


Add workflow file: Sanity-Checks.yml

Commit changes to a new branch and open a Pull Request (recommended).

Actions will run automatically; view logs in the Actions tab.

💡 Tips

Ensure build/test commands exist for each language.

PR labelling works only if the workflow is triggered by a PR.

Enable branch protection rules to require passing Sanity-Checks before merging.

Optional: Add security scans, notifications, and coverage reports.

📚 References

GitHub Actions Docs

dorny/paths-filter

actions-ecosystem/action-add-labels


---

### ✅ **What this gives you**
- Fully automated **multi-language CI workflow**.  
- Optional PR labelling (failsafe if PR doesn’t exist).  
- Dependency caching for faster runs.  
- Polished, **attractive README** with flowchart, badges, and tables.  
- Easy for team members or future developers to use immediately.  

---
