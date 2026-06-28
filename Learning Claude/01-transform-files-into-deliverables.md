# 01. Transform files into deliverables

> Source: <https://app.notion.com/p/38b70dfa56c48042a6dafe0b10367854>  
> Parent: [Building Real Tools](README.md) · [Learning Claude](../README.md)

---

### 🗂️ Session Management
- Claude Code **doesn't show previous conversations** in a chat-style UI — it uses the terminal instead.
- Sessions are **stored locally** and can be reopened with the `resume` command, which lists all past sessions.
- You can **rename a session** using `Ctrl + R` (e.g., rename to "insights") for easy retrieval later.
- Sessions are **workspace/folder-specific** — each folder keeps its own conversation history.

### ⌨️ Useful Commands

| Command | What it does |
|---------|-------------|
| `claude -c` | Opens Claude with the last conversation already loaded |
| `claude -r` | Shows a list of sessions to choose from |
| `Ctrl + A` | Shows conversations from **all folders**, not just the current workspace |
| `Escape` | Exits/dismisses a list or search view |
| `/copy` | Copies the last AI response to your clipboard (Markdown format) |
| `/export` | Saves the last response to a file (also offers clipboard copy option) |

### 📁 Working with Files
- Use the **`@` symbol** in a prompt to pull up a file picker from your current directory.
- You can also **start typing a filename** after `@` to filter matches, then press `Tab` to select.
- Claude reads files you reference and generates analysis based on their contents.

### 🔄 File → Deliverable Workflow (Demo)

1. **Read & Summarize** — Prompt: `Review @balance-sheet.xlsx @income-statement.xlsx — create a short executive summary describing the company's financial position.` Claude reads the spreadsheets and produces a concise analysis. It may ask if you want to save it to a file.

2. **Convert to a Document** — Follow-up: `Turn that summary into a professional financial report and save it as financialreport.docx` → generates a proper Word document, cleaner than raw Markdown.

3. **Generate Charts** — Prompt: `Create charts from the sales spreadsheets showing revenue trends and export them as image files.` → produces chart image files in your folder.

4. **Build a Presentation** — Prompt: `Create a PowerPoint presentation summarizing key insights from the spreadsheets — include charts and executive commentary.` → generates a `.pptx` file with charts and commentary included.

### 💡 Key Takeaway
> Once you understand how **sessions and workspaces** interact, Claude Code becomes much more than a chatbot — it's a tool that helps you **produce real artifacts from your data.**

---

**Previous:** [← Getting Started](../getting-started/README.md)  
**Next:** [02. Build a financial dashboard with Python](02-build-a-financial-dashboard-with-python.md)
