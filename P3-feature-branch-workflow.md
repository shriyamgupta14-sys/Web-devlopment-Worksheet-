# P3 – Feature-Branch Git Workflow

**Goal:** build a feature on its own branch and merge it back safely into `main`.

## 1. Check the starting point

```bash
git switch main
git status
git branch            # * main
```

## 2. Create a feature branch

```bash
git switch -c feature/navbar
git branch            # * feature/navbar   main
```

## 3. Work and commit on the branch

```bash
# edit index.html and css/style.css to add a navbar
git status
git add index.html css/style.css
git commit -m "Add navbar markup and styles"

# make a second improvement
git add .
git commit -m "Style navbar links and hover state"
git log --oneline
```

## 4. Push the branch to GitHub

```bash
git push -u origin feature/navbar
```

## 5. Merge back into main

Option A – locally:

```bash
git switch main
git pull origin main
git merge feature/navbar
git push origin main
```

Option B – on GitHub: open a **Pull Request** (base `main`, compare `feature/navbar`), review, then **Merge pull request**.

## 6. Clean up

```bash
git branch -d feature/navbar              # delete local branch
git push origin --delete feature/navbar   # delete remote branch
```

## 7. See the history

```bash
git log --oneline --graph --all
```

```
*   5f6e7d8 (HEAD -> main) Merge branch 'feature/navbar'
|\
| * 9c8b7a6 Style navbar links and hover state
| * 3d2c1b0 Add navbar markup and styles
|/
* a1b2c3d Initial commit: add portfolio starter files
```

## Handling a merge conflict

```bash
git merge feature/navbar
# CONFLICT in index.html
# 1. open the file, keep the correct lines, delete <<<<<<<, =======, >>>>>>>
git add index.html
git commit -m "Resolve merge conflict in index.html"
```

## Rule of thumb

`main` stays working. Every new feature gets its own branch, then is merged after review.
