# 🚢 Deployment & GitHub Actions Guide

This document details how to configure GitHub Actions permissions so that the Contribution Snake workflow operates automatically without errors.

---

## 🔐 GitHub Workflow Permissions Setup

For GitHub Actions to push generated assets to the `output` branch:

1. Navigate to your repository on **GitHub.com**.
2. Click **Settings** -> **Actions** -> **General**.
3. Scroll down to **Workflow permissions**.
4. Select **Read and write permissions**.
5. Check **Allow GitHub Actions to create and approve pull requests**.
6. Click **Save**.

---

## ⚡ GitHub Actions Workflow Details (`snake.yml`)

The workflow runs on two triggers:
- **Cron Schedule**: Automatically every night at midnight UTC (`0 0 * * *`).
- **Workflow Dispatch**: Manual execution button inside GitHub Actions UI.

```yaml
name: Generate Contribution Snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark&color_snake=#06B6D4&color_dots=#1E293B,#2563EB,#7C3AED,#06B6D4,#38BDF8
      - uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

---

## 🎯 Verification checklist

- [x] Repository matches GitHub username.
- [x] Workflow permissions set to `Read and write`.
- [x] `snake.yml` executed manually once.
- [x] `output` branch contains `github-contribution-grid-snake-dark.svg`.
