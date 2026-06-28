# 03. Navigate Claude Code and core commands

> Source: <https://app.notion.com/p/38a70dfa56c4801fba0bcf1607376973>  
> Parent: [Getting Started](README.md) · [Learning Claude](../README.md)

---

# Notes: Navigate Claude Code and Core Commands

## What is Claude Code?
- Claude Code works like a chatbot, but **runs directly in your terminal**, not inside a web browser.
- It operates inside the folder where you launch it.
- It can access and analyze files within that directory.

### Example
If you launch Claude Code inside a `finance` folder:
- It can see spreadsheets, documents, and other files in that folder.
- It can analyze those files and provide insights.

---

# File Analysis

Claude Code can:
- Detect files in a directory.
- Analyze spreadsheets and documents.
- Generate summaries and reports.
- Compare data across multiple files.

### Example Workflow
1. Claude detects 10 Excel files.
2. It writes Python code to analyze them.
3. User approves the script.
4. Claude executes the analysis.
5. Results are displayed in tables and summaries.

---

# Permission System

When Claude wants to perform actions, it may request permission.

### Options
- **Approve once** → Run the current command.
- **Always allow** → Future commands of the same type run without asking again.

### Common Permissions

| Permission | Purpose |
|------------|---------|
| Python | Analyze data, automate tasks |
| Web Search | Search the internet |
| Pip Install | Install Python packages |

---

# Tool Use

Claude can expand its capabilities using tools.

## Python Tool
Used for:
- Data analysis
- Automation
- File processing
- Report generation

Example:
```
Analyze Excel files
Create tables
Generate summaries
```

---

## Web Search Tool
Used for:
- Finding current information online
- Comparing local data with external trends

### Example
- Analyze company sales data.
- Search recent U.S. retail sales trends.
- Compare internal data with market trends.

---

## Agentic Behavior
Claude is an **agentic AI**, meaning:
- It tries to solve problems independently.
- If one method fails, it attempts another.
- It can install missing dependencies if permitted.

### Example
1. Document generation fails.
2. Claude identifies a missing library.
3. Requests permission to install it.
4. Tries again automatically.

---

# Creating Documents

Claude can generate real files, such as:
- Word documents
- Reports
- Executive summaries

### Example
Request:
> Create an executive summary and save it as a document.

Claude:
1. Generates the content.
2. Creates the file.
3. Saves it to your computer.

---

# Bash Mode

You can run terminal commands directly inside Claude Code.

### Syntax
```
!
```
The exclamation mark enters Bash mode.

---

# Useful Bash Commands

## Show Current Directory
```
pwd
```
Output:
```
/home/user/finance
```
Purpose:
- Displays your current working directory.

---

## List Files
```
ls
```
Purpose:
- Shows all files and folders in the current directory.

Example:
```
sales.xlsx
budget.xlsx
financialinsights.docx
```

---

# Opening Files

If a file exists in the current folder:
```
open ./filename.docx
```

### Explanation
- `./` means "current directory".
- `open` launches the file with its default application.

Example:
```
open ./financialinsights.docx
```
Result:
- Opens the document in Microsoft Word.

---

# Key Concept

Claude Code is more than a chatbot.

### Traditional Chatbot
- Generates text responses only.

### Claude Code
- Reads files.
- Runs code.
- Searches the web.
- Installs packages.
- Creates documents.
- Executes terminal commands.
- Works alongside you like a collaborator.

---

# Quick Summary

### Core Capabilities
- ✅ Analyze local files
- ✅ Run Python scripts
- ✅ Search the web
- ✅ Install packages with Pip
- ✅ Generate reports and documents
- ✅ Execute Bash commands
- ✅ Open applications and files
- ✅ Solve problems autonomously

### Important Commands
```
pwd
```
Show current directory.

```
ls
```
List files and folders.

```
open ./filename.docx
```
Open a file.

```
!
```
Enter Bash mode.

### Main Idea
> Claude Code is an AI assistant that works directly inside your computer's terminal, allowing it to analyze files, run code, use tools, and automate tasks rather than simply chatting.

---

**Previous:** [02. Understand the terminal and shell pt.2](02-understand-the-terminal-and-shell-pt2.md)  
**Next:** [Building Real Tools →](../building-real-tools/README.md)
