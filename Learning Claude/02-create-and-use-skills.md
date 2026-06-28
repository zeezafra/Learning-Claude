# 02. Create and Use Skills

> Source: <https://app.notion.com/p/38b70dfa56c48089ac3ff7b03ab41bff>  
> Parent: [Extending Claude](README.md) · [Learning Claude](../README.md)

---

## Overview
Skills are the **newer, more powerful evolution of custom commands**. Where a command is a single file that triggers one action, a skill is a full **folder** that can contain scripts, templates, examples, and reference documents — giving Claude everything it needs to handle complex, multi-step tasks.

---

## 1. Skills vs. Commands — What's the Difference?

| | Commands | Skills |
|--|---------|--------|
| **Structure** | Single `.md` file | A folder containing multiple files |
| **Complexity** | Simple, single actions | Complex, multi-step workflows |
| **Metadata** | None | YAML front matter (name, description, tools) |
| **Flexibility** | Limited | High — can include scripts, templates, examples |
| **Location** | `.claude/commands/` | `.claude/skills/` |
| **Default file** | `commandname.md` | `skill.md` inside a named subfolder |

> Skills are intended to **replace custom commands** over time, as they're significantly more flexible.

---

## 2. Skills vs. Built-in Commands

Claude Code includes built-in commands like `/help` and `/compact`. These are distinct from skills:
- **Built-in commands** are designed to **control the CLI environment** itself (e.g. clearing context, getting help).
- **Skills** (and custom commands) **generate prompts for Claude to execute** — they're about doing work, not managing the tool.

---

## 3. Creating a Skill

### Example 1 — Spreadsheet Summary

**Prompt used:**
> "Create a skill called Spreadsheet Summary that analyses Excel files and calculates totals, averages, and trends. Open the folder in Finder."

Claude creates the skill and can also open the folder location in Finder so you can see the files it's generating — a reminder that Claude can execute Finder commands and interact with your operating system directly.

---

### Example 2 — Presentation Builder (more complex)

**Prompt used:**
> "Create a skill called Presentation Builder that analyses the financial spreadsheets and reports in this project, generates useful charts when needed, and assembles a presentation summarising the most important insights."

**What Claude does:**
- Creates a **`.claude/skills/`** subfolder in the project directory.
- Inside it, creates a **`presentation-builder/`** folder (not just a single file like commands).
- Inside that folder, generates a **`skill.md`** file — the core instruction file for the skill.
- Confirm with "yes" to allow Claude to edit its own settings for the session.

---

## 4. YAML Front Matter — What It Is

Every skill's `skill.md` file begins with **YAML front matter**. This is a short block of structured metadata at the top of the file.

**YAML** (a simple, human-readable file format) defines key variables that Claude uses when loading the skill:

```yaml
name: Presentation Builder
description: Analyses financial data and generates a summarised presentation
tools:
  - python
  - spreadsheet_reader
  - chart_generator
```

It typically includes:
- **name** — the skill's display name.
- **description** — what the skill does.
- **tools** — the tools Claude will need to run it.

YAML front matter is what makes skills "smarter" than commands — Claude knows upfront what a skill is for and what resources it requires.

---

## 5. File Structure at a Glance

```
.claude/
├── commands/
│   ├── brief.md
│   └── create-charts.md
└── skills/
    ├── spreadsheet-summary/
    │   └── skill.md
    └── presentation-builder/
        └── skill.md
```

> **Note:** The `.claude` folder is a hidden folder (prefixed with a dot) and won't appear in Finder by default — see the tip below.

---

## 6. Running a Skill

Once a skill is created, you can invoke it with a natural language prompt — no special syntax needed.

**Example:**
> "Create a presentation summarising the financial data. Use the budget file in the data folder."

- Claude reads the skill, understands the task, and executes it.
- In the demo, it generated a presentation deck from a budget spreadsheet, which was then opened directly from the terminal.

---

## 7. Scope: Commands Are Local to a Directory

A quick but important note from the lesson — the `.claude` folder and its commands/skills are **local to the directory they were created in**. If you move to a different project folder, those commands and skills won't be available unless you create them there too (or copy the `.claude` folder across).

---

## Bonus Tip — Viewing Hidden Files on macOS

The `.claude` folder is a hidden file (starts with a dot) and won't appear in Finder by default. To toggle visibility:
- **Keyboard shortcut (temporary):** `Command + Shift + .` in Finder to show/hide hidden files.
- **Permanent setting:** Ask Claude — it can look up and run the terminal command to make hidden files always visible in Finder.

---

## Key Takeaways
- Skills are a **folder-based, more powerful replacement for custom commands** — better suited to complex, multi-step work.
- Each skill lives in its own subfolder inside `.claude/skills/` and contains a **`skill.md`** file with YAML front matter.
- **YAML front matter** tells Claude the skill's name, description, and what tools it needs — making skills self-contained and self-describing.
- Skills can be **customised by editing the folder contents** and are **easy to share** with teammates by copying the folder.
- Claude can interact with your **operating system directly** — opening Finder, running terminal commands, toggling file visibility, and more.
- Commands and skills are **local to the directory** they're created in.

---

**Previous:** [01. Create custom commands](01-create-custom-commands.md)  
**Next:** [03. Connect external tools with MCP servers](03-connect-external-tools-with-mcp-servers.md)
