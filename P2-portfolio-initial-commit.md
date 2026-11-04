# P2 – Portfolio Repository with an Initial Commit

**Goal:** turn the portfolio folder into a Git repository and make the first commit.

## 1. One-time Git setup

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
```

## 2. Initialise the repository

```bash
cd ~/Desktop/portfolio
git init
git status            # everything shows as "untracked"
```

## 3. Add starter content

```bash
echo "# My Portfolio" > README.md
```

Add a simple `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My Portfolio</title>
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <h1>Hello, I am building my portfolio</h1>
</body>
</html>
```

## 4. Stage and commit

```bash
git status             # see untracked files
git add .              # stage everything
git status             # files now show as "Changes to be committed"
git commit -m "Initial commit: add portfolio starter files"
```

## 5. Verify

```bash
git log --oneline
git status             # "nothing to commit, working tree clean"
```

Expected log:

```
a1b2c3d (HEAD -> main) Initial commit: add portfolio starter files
```

## Optional: add a `.gitignore`

```bash
printf ".DS_Store\nnode_modules/\n*.log\n" > .gitignore
git add .gitignore
git commit -m "Add .gitignore"
```

## Concepts to remember

- **Working directory** → files you edit
- **Staging area** (`git add`) → changes ready to save
- **Local repository** (`git commit`) → saved snapshots on your PC
