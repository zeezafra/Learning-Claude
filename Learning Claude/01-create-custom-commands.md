# 01. Create custom commands

> Source: <https://app.notion.com/p/38b70dfa56c4800a93dbcbcd8f5f1b87>  
> Parent: [Extending Claude](README.md) · [Learning Claude](../README.md)

---

## Overview
Custom commands let you turn **frequently used workflows into simple, reusable shortcuts**. Instead of typing out long prompts repeatedly or remembering which Python scripts to run, you can create a short slash command that triggers the whole process for you with one word.

---

## 1. Creating Your First Command — `/brief`

### The Prompt
> "Create a command called `/brief` that scans the current folder and generates a short project summary called `summary.md`."

### What Claude Does
- Creates a hidden folder called **`.claude`** in your project directory.
- Inside it, creates a **`commands`** subfolder.
- Saves the command as a markdown file — in this case **`brief.md`**.

The command file is just a plain markdown document containing the instructions Claude will follow when the command is run. Claude writes this file for you automatically.

### Activating the New Command
Commands don't take effect in the current session immediately. To activate them:
1. Press **Ctrl + C twice** to quit Claude.
2. Type **`claude`** to relaunch.
3. The new slash command is now available to use.

### Running It
Type `/brief` and Claude scans the project folder and generates the summary output.

---

## 2. Editing a Command

Commands can be updated in two ways:

**Option A — Edit the file directly:**
- Open the `.claude/commands/brief.md` file in any text editor and modify the instructions manually.

**Option B — Tell Claude to update it (easier):**
- Just describe the change you want in plain language.
- Example: *"Update the `/brief` command so it exports as a `.docx` document instead of Markdown."*

### The Diff View
When Claude edits a command file, it shows a **diff view** — a side-by-side comparison of what's changing:
- **Red lines** = text being removed.
- **Green lines** = text being added.

In the example, Claude changed the output from `summary.md` to `summary.docx` and updated the formatting instructions from "clean markdown format" to "proper Word formatting with headings, paragraphs, and tables where appropriate."

Confirm the change by typing **"yes"** and Claude updates its own settings for the session.

---

## 3. Turning an Existing Script into a Command — `/create-charts`

If you already have Python scripts in your project, you can wrap them in a command so you never have to remember to invoke Python manually.

### The Prompt
> "Create a command called `/create-charts` that runs the `createcharts.py` script and creates charts from a folder or file."

### What Claude Does
- Reads the contents of `createcharts.py` to understand how it works.
- Figures out the most logical way to wrap it as a command.
- Creates the command so it can accept either:
  - A **specific Excel file** as a target, or
  - An **entire folder** of data files.

### Running It
Use the `@` symbol to reference a file or folder when calling the command:
```
/create-charts @data/sales_2024.xlsx
```
or
```
/create-charts @data/
```

---

## 4. Auto-Suggesting Commands

You don't have to think of commands yourself — you can ask Claude to scan your project and suggest useful ones based on what you've already been doing.

### The Prompt
> "Look through this project folder and create some commands for me based on the things we've been doing."

### What Happens
Claude analyses the project contents and proposes a set of commands that would automate your most common tasks — giving you a ready-made shortcut library tailored to your specific workflow.

---

## Where Commands Are Stored

| Location | Purpose |
|----------|---------|
| `.claude/commands/` | Folder where all custom command files live |
| `brief.md` | Example — instructions for the `/brief` command |
| `create-charts.md` | Example — instructions for the `/create-charts` command |

Each file is just a markdown document. You can view, edit, or share them like any other file.

---

## Key Takeaways
- Custom commands turn **repeatable workflows into one-word shortcuts** — no more typing out long prompts or remembering script names.
- Commands are stored as **plain markdown files** in `.claude/commands/` and are easy to inspect and edit.
- After creating a command, **quit and relaunch Claude** (Ctrl+C twice, then `claude`) for it to take effect.
- You can update commands by simply **telling Claude what to change** — no need to edit files manually.
- Existing Python scripts can be **wrapped as commands**, with the `@` symbol used to pass in target files or folders.
- Ask Claude to **scan your project and suggest commands** — it will build a tailored shortcut set based on your actual work.

---

**Previous:** [← Building Real Tools](../building-real-tools/README.md)  
**Next:** [02. Create and Use Skills](02-create-and-use-skills.md)
