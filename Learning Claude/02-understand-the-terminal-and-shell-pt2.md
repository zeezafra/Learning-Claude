# 02. Understand the terminal and shell pt.2

> Source: <https://app.notion.com/p/38a70dfa56c4800986aed8a88e4614b3>  
> Parent: [Getting Started](README.md) · [Learning Claude](../README.md)

---

# Lesson Notes: Understanding the Terminal & Shell
### Topic: Claude Code CLI — Installing and Getting Started

---

## 1. What is Claude Code?
- Similar to AI chat tools like ChatGPT or GitHub Copilot, but runs **directly inside your project folders** on your local machine.
- It can read and work with files already on your computer (code, PDFs, etc.).
- It can **run Linux commands** and control files — making it far more powerful than browser-based chatbots.

---

## 2. How the Terminal Works (Quick Recap)
- When you open a new terminal, you start inside your **user's home folder**.
- `ls` — lists files in the current directory.
- `pwd` — prints the current working directory (so you know where you are).
- `open .` — opens the current folder in Finder (macOS).
- **`.DS_Store`** — an invisible file macOS creates to store folder metadata. Nothing to worry about.

> ⚠️ **Important:** Claude Code CLI runs inside **whichever folder you're currently in** when you launch it. Always navigate to the right folder first!

---

## 3. Installing Claude Code

Run this command in your terminal:
```bash
curl -fsSL https://<install-url>.sh | bash
```

### Breaking Down the Command

| Part | Meaning |
|------|---------|
| `curl` | Downloads files from the internet directly in the terminal |
| `-f` | Fail silently if the server returns an error |
| `-s` | Silent mode — suppresses progress messages |
| `-S` | Still shows errors even in silent mode |
| `-L` | Follow redirects if the download URL has changed |
| `.sh` file | A **shell script** — a text file containing multiple terminal commands |
| `| bash` | Pipes the downloaded script into **bash** to execute it |

### What the Installer Does
- Downloads the Claude Code CLI.
- Places it somewhere in your **system PATH** (the list of folders your terminal searches when you type a command).

### Verify Installation
```bash
claude --version
# Example output: 2.1.66
```

---

## 4. First-Time Setup

When you run Claude for the first time, it walks you through setup:
1. **Theme** — Choose light or dark mode (dark is default/preferred by most devs).
2. **Account connection** — Three options:
   - Claude subscription (recommended — more usage, lower cost)
   - API key (pay per use)
   - Third-party platforms (e.g., Microsoft Foundry, Amazon Bedrock)
3. **Browser authorization** — Opens a browser to link your Claude account.
4. **Security notice** — Claude warns about prompt injection risks. Only use it with code you trust.
5. **Folder trust** — Every session, Claude asks if you trust the current working folder.
6. **Effort level** — Choose how much effort Claude puts into tasks (Standard = `1` is recommended to start).

---

## 5. Using the Claude Code Interface
- Works like a chatbot — type questions or instructions naturally.
- Shows **"thinking" prompts** while processing.
- Press **`?`** to see all keyboard shortcuts and common commands.

### Key Shortcuts

| Action | Command |
|--------|---------|
| Quit Claude | `Ctrl + C` (twice) |
| View shortcuts | `?` |
| Resume previous conversation | Run the resume command shown after exiting |

---

## 6. Why Claude Code CLI is Special
- Runs **local files and commands** from the terminal.
- Can read, analyze, and modify files in your project.
- Retains conversation context — you can resume where you left off.
- More powerful than web-based AI chatbots because it has **direct access to your machine**.

---

## Key Takeaways
- Always **navigate to your project folder** before launching Claude Code.
- The install command uses `curl` to download and `bash` to run a shell script.
- A **shell script (`.sh`)** is just a collection of terminal commands in a file.
- The **pipe (`|`)** sends the output of one command as input to another.
- Claude Code runs in your terminal like a chatbot but with full access to your local environment.

---

**Previous:** [01. Understand the terminal and shell pt.1](01-understand-the-terminal-and-shell-pt1.md)  
**Next:** [03. Navigate Claude Code and core commands](03-navigate-claude-code-and-core-commands.md)
