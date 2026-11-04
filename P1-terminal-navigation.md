# P1 – Project Folder and Terminal Navigation

**Goal:** create a portfolio project folder from the terminal and move around it confidently.

## 1. Where am I?

```bash
pwd                 # print working directory
ls                  # list files
ls -la              # list all files (including hidden) with details
```

## 2. Create the project structure

```bash
cd ~/Desktop                          # go to Desktop (or any folder you like)
mkdir portfolio                       # create the project folder
cd portfolio                          # enter it
mkdir css images docs                 # create sub-folders in one command
touch index.html css/style.css        # create empty files
touch docs/notes.txt
```

Resulting structure:

```
portfolio/
├── index.html
├── css/
│   └── style.css
├── images/
└── docs/
    └── notes.txt
```

## 3. Navigate

```bash
cd css              # go into css
pwd                 # /…/portfolio/css
cd ..               # go up one level
cd ../images        # go up, then into images
cd ~                # go to home directory
cd -                # jump back to previous folder
```

## 4. Inspect and edit

```bash
cat docs/notes.txt              # show file content
echo "Portfolio notes" >> docs/notes.txt   # append a line
ls -R                           # list everything recursively
tree                            # tree view (if installed)
```

## 5. Copy, move, rename, delete

```bash
cp index.html index-backup.html     # copy
mv index-backup.html docs/          # move
mv docs/index-backup.html docs/old-index.html   # rename
rm docs/old-index.html              # delete a file
rmdir images                        # delete an EMPTY folder
rm -r old-folder                    # delete a folder and its contents (careful!)
```

## 6. Open the project in VS Code

```bash
code .
```

## Command cheat-sheet

| Command | Purpose |
|---------|---------|
| `pwd` | show current directory |
| `ls`, `ls -la` | list files |
| `cd <dir>`, `cd ..`, `cd ~` | change directory |
| `mkdir <dir>` | create folder |
| `touch <file>` | create empty file |
| `cp`, `mv`, `rm` | copy, move/rename, delete |
| `cat <file>` | display file |
| `clear` | clear the screen |
