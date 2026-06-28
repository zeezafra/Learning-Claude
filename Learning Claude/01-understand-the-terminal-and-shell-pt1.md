# 01. Understand the terminal and shell pt.1

> Source: <https://app.notion.com/p/38a70dfa56c480ada926cd1742db24ba>  
> Parent: [Getting Started](README.md) · [Learning Claude](../README.md)

---

Note: Need to be comfortable on terminal  
Microsoft = Powershell

| Purpose | Windows CMD |
|---------|-------------|
| Show current directory | `cd` |
| List files/folders | `dir` |
| Detailed list | `dir /a` |
| Change directory | `cd folder` |
| Go up one level | `cd ..` |
| Go to root | `cd \` |
| Switch drive | `D:` |
| Create folder | `mkdir folder` |
| Remove empty folder | `rmdir folder` |
| Print text | `echo Hello` |
| Clear screen | `cls` |
| Show PATH | `echo %PATH%` |
| Run multiple commands | `cmd1 && cmd2` |
| Open current folder | `start .` |
| Open parent folder | `start ..` |
| Open VS Code | `code .` |

---

# Navigation Examples

### Check where you are
```shell
cd
```

### Go to D: drive
```shell
D:
```

### Go to a folder
```shell
cd D:\Projects\Portfolio
```

### Go back one folder
```shell
cd ..
```

### Go to root of D:
```shell
cd \
```

---

# Listing Files

### Show files and folders
```shell
dir
```

### Show hidden files too
```shell
dir /a
```

### Show only folders
```shell
dir /ad
```

---

# Creating Folders

### Create one folder
```shell
mkdir Portfolio
```

### Create nested folders
```shell
mkdir D:\Projects\Portfolio
```

---

# Echo (Print Text)
```shell
echo Hello World
```
Output:
```
Hello World
```

---

# Run Multiple Commands
```shell
cd D:\Projects && dir
```
This:
1. Goes to `D:\Projects`
2. Lists files

---

# Show PATH
```shell
echo %PATH%
```

---

# Open Folder in Explorer

Current folder:
```shell
start .
```

Parent folder:
```shell
start ..
```

Specific folder:
```shell
start D:\Projects
```

---

# Open VS Code

Current folder:
```shell
code .
```

Specific folder:
```shell
code D:\Projects\Portfolio
```

---

# Useful CMD Shortcuts

### Create file
```shell
type nul > index.html
```

### Create multiple files
```shell
type nul > index.html
type nul > style.css
type nul > script.js
```

### Delete file
```shell
del index.html
```

### Delete folder
```shell
rmdir /s Portfolio
```

### Rename file
```shell
ren old.txt new.txt
```

### Copy file
```shell
copy source.txt backup.txt
```

### Move file
```shell
move file.txt D:\Projects
```

---

# Portfolio Workflow Example
```shell
D:
mkdir Projects
cd Projects

mkdir Portfolio
cd Portfolio

type nul > index.html
type nul > style.css
type nul > script.js

code .
```

This will:
1. Switch to D:
2. Create `Projects`
3. Create `Portfolio`
4. Create HTML, CSS, and JS files
5. Open everything in VS Code

This is enough CMD knowledge to comfortably work on web development projects in VS Code on your D: drive.

---

**Next:** [02. Understand the terminal and shell pt.2](02-understand-the-terminal-and-shell-pt2.md)
