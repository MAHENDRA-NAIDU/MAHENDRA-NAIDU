# 🎨 Customization Guide

This guide explains how to customize your GitHub Profile README colors, social links, tech stack badges, featured projects, and SVGs.

---

## 🎨 1. Color Palette Customization

The project uses a curated 2026 dark mode palette:

- **Primary**: `#2563EB` (Electric Royal Blue)
- **Secondary**: `#7C3AED` (Deep Violet)
- **Accent**: `#06B6D4` (Neon Cyan)
- **Background**: `#0B0F19` / `#0F172A` (Slate Glass)

To update colors in the SVGs (`banner.svg`, `hero.svg`, `coding.svg`, `profile.svg`, `footer.svg`), search and replace hex values inside the SVG `<defs>` block:

```xml
<stop offset="0%" stop-color="#2563EB"/>
<stop offset="50%" stop-color="#7C3AED"/>
<stop offset="100%" stop-color="#06B6D4"/>
```

---

## 🔗 2. Updating Social Badges & Links

In `README.md`, replace placeholder social URLs with your active accounts:

```markdown
<!-- LinkedIn -->
<a href="https://linkedin.com/in/YOUR_LINKEDIN_USERNAME" target="_blank">
  <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
</a>

<!-- LeetCode -->
<a href="https://leetcode.com/u/YOUR_LEETCODE_USERNAME/" target="_blank">
  <img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black" />
</a>

<!-- GeeksforGeeks -->
<a href="https://www.geeksforgeeks.org/user/YOUR_GFG_USERNAME/" target="_blank">
  <img src="https://img.shields.io/badge/GeeksforGeeks-2F8D46?style=for-the-badge&logo=geeksforgeeks&logoColor=white" />
</a>
```

---

## 💻 3. Customizing Featured Projects Cards

Update project links and descriptions inside `README.md`:

```html
<a href="https://github.com/YOUR_USERNAME/YOUR_PROJECT_REPO">
  <h3>🌾 AI Farmer Assistant</h3>
  <p>Intelligent Web Application helping farmers with crop recommendations and disease diagnosis using AI models.</p>
</a>
```

---

## 📊 4. GitHub Stats Configuration

In `README.md`, replace `YOUR_GITHUB_USERNAME` in stats card URLs with your actual username:

```markdown
https://github-readme-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true&theme=transparent...
```
