# 02. Build a financial dashboard with Python

> Source: <https://app.notion.com/p/38b70dfa56c480819eeafd84216a5f72>  
> Parent: [Building Real Tools](README.md) · [Learning Claude](../README.md)

---

## Overview
This lesson demonstrates how to use the **Claude Code CLI** to build a fully functional, browser-based financial dashboard using Python — without writing a single line of code manually. Claude handles everything from organising your project files to installing libraries and fixing its own errors.

---

## 1. Organising Your Project Workspace

Before building the dashboard, the project folder was messy. Rather than manually reorganising it, Claude was prompted to do it automatically.

**Prompt used:**
> "Organise this workspace so it's easier to manage. Create folders (data, charts, scripts, etc.), move the existing files into the appropriate folders based on their type, keep the file names the same, and make sure you don't delete anything."

**What Claude did:**
- Wrote the appropriate bash commands to create folders and move files.
- Organised all files correctly, except one quick output file that didn't belong anywhere (this was deleted manually via Finder).

**Key takeaway:** File organisation is a simple but powerful example of the kind of automation Claude can handle so you don't have to.

---

## 2. Building the Financial Dashboard

### The Prompt
Claude was given a natural language instruction to:
- Read Excel files
- Analyse the data
- Generate charts
- Build a **web-based** dashboard (viewable in a browser)
- Save the code and install any required libraries

No specific libraries were named — Claude chose them independently.

### Libraries Claude Installed (via pip)

| Library | Purpose |
|---------|---------|
| **pandas** | Reading and analysing spreadsheet/Excel data |
| **Dash** | Creating web-based dashboards |
| **Plotly** | Generating interactive charts |

> **Tip:** `pip` is the tool that installs additional extensions (modules) to the Python language. Claude handles `pip install` commands automatically — you can tell it not to ask for permission each time.

### Cross-Platform Awareness
- Claude detects whether you're on a **Mac** or **PC** and issues the appropriate commands.
- On Mac, Python is called via `python3`; Claude handles this discrepancy automatically.

---

## 3. Claude's Agentic Error Handling

Claude may encounter errors while building — this is normal and expected.
- Due to its **agentic nature**, Claude automatically attempts to fix errors without you needing to intervene.
- It will keep trying to accomplish the task, modifying files as needed to reach its goal.
- You often won't even know an error occurred.

---

## 4. Understanding Local Servers & Ports

Claude runs a local web server to host the dashboard. Here's what that means:

### IP Addresses
- Website URLs (e.g., `linkedin.com`) are converted into **IP addresses**, which represent the physical location of a server on the internet.
- Your local computer can also run IP addresses **locally**, for previewing websites.

### Localhost
- The most common local address is **`127.0.0.1`**, also known as **localhost**.
- These two are interchangeable — `localhost` and `127.0.0.1` behave identically.

### Ports
- Local servers require a **port number** (e.g., `:3000`, `:3030`, `:8050`).
- Think of ports like **TV channels** — the computer can run different tools on different ports simultaneously.
- Claude chose **port 8050** for this dashboard.

---

## 5. Iterating on the Dashboard with a Screenshot

The initial dashboard had two issues:
1. **Legend labels overlapping** in the "Monthly Sales & Trends" and "Online Sales Trends" charts.
2. **Slow load time.**

Rather than trying to describe the visual problem in text, a screenshot was passed directly to Claude.

### How to Take a Screenshot on Mac
- `Command + Shift + 3` → full screen capture
- `Command + Shift + 4` → drag to select a specific region *(used here)*

The screenshot was dragged directly into the Claude chat as an image attachment, along with a note explaining the legend overlap and slow loading.

**Result:** Claude loaded a new server at the same address, and the updated dashboard:
- Loaded significantly faster.
- Had the legend overlap issue fixed.

**Key takeaway:** When describing a visual problem is difficult, an image does a much better job than text.

---

## 6. Summary & Key Takeaways
- With just a **few natural language prompts**, Claude handled both Python and Bash tasks entirely.
- No code was written manually.
- Claude selected and installed the appropriate libraries on its own.
- Claude self-corrected errors autonomously.
- Visual feedback (screenshots) can be passed to Claude to communicate UI issues more effectively than text descriptions.

---

**Previous:** [01. Transform files into deliverables](01-transform-files-into-deliverables.md)  
**Next:** [03. Automate document compliance reviews](03-automate-document-compliance-reviews.md)
