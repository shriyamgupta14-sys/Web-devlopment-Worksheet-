# P4 – GitHub README and Version Tags

**Goal:** publish the portfolio on GitHub with a professional README and tagged releases.

## 1. Create the GitHub repository

On GitHub: **New repository** → name `portfolio` → Public → do **not** add a README (you already have one) → **Create**.

```bash
git remote add origin https://github.com/<your-username>/portfolio.git
git remote -v
git push -u origin main
```

## 2. Write a good README.md

````markdown
# My Portfolio

A responsive personal portfolio website built with HTML and CSS.

## Live Demo
https://<your-username>.github.io/portfolio/

## Features
- Semantic HTML5 structure
- Responsive layout (Flexbox and Grid)
- Sticky navigation bar
- Projects section with card layout

## Tech Stack
- HTML5
- CSS3

## Project Structure
```
portfolio/
├── index.html
├── css/style.css
└── images/
```

## Getting Started
```bash
git clone https://github.com/<your-username>/portfolio.git
cd portfolio
# open index.html in your browser
```

## Author
**Your Name** – [GitHub](https://github.com/<your-username>)
````

Commit it:

```bash
git add README.md
git commit -m "Add detailed README"
git push
```

## 3. Create version tags

Use **semantic versioning**: `MAJOR.MINOR.PATCH`.

```bash
git tag -a v1.0.0 -m "First stable release of the portfolio"
git tag                      # list tags
git show v1.0.0              # inspect a tag
git push origin v1.0.0       # push one tag
# or push all tags
git push origin --tags
```

## 4. Release a later version

```bash
# after more commits
git tag -a v1.1.0 -m "Add projects grid and responsive navbar"
git push origin v1.1.0
```

| Change type | Example bump |
|-------------|--------------|
| Bug fix | `v1.0.0` → `v1.0.1` |
| New feature (backward compatible) | `v1.0.1` → `v1.1.0` |
| Big redesign | `v1.1.0` → `v2.0.0` |

## 5. Publish a GitHub Release (optional)

GitHub → **Releases** → **Draft a new release** → choose tag `v1.0.0` → add notes → **Publish release**.

## 6. Delete a wrong tag

```bash
git tag -d v1.0.0
git push origin --delete v1.0.0
```
