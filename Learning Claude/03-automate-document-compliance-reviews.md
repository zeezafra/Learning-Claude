# 03. Automate document compliance reviews

> Source: <https://app.notion.com/p/38b70dfa56c48051a2bfc8acd79e7415>  
> Parent: [Building Real Tools](README.md) · [Learning Claude](../README.md)

---

## Overview
Organisations produce a high volume of documents — newsletters, reports, blog posts, and more. Keeping the tone and style consistent across all of them typically requires slow, manual review. This lesson shows how Claude Code can **scan entire folders of documents** against a custom rubric and automate that compliance process.

---

## 1. The Setup

### What You Need
- A **marketing rubric** document — a set of rules/standards that documents should conform to.
- A **folder of documents** to be reviewed (e.g. Word docs, PDFs, PowerPoints — a mix of formatting levels to test what works).

### Adding Files
- Use Claude's `open` command (or the bash tool) to open your project folder and drop files in directly.
- Documents with various formatting complexity were added to test the limits of what the tool can handle.

---

## 2. Building the Compliance Tool

### The Prompt
Claude was asked to:
- Create a **Python tool** that reviews each document against the marketing rubric.
- **Score** each document according to the rubric.
- **Generate a compliance report**.
- **Export structured data** for use in a future dashboard.
- Include **suggested edits** for any sections that violate the rubric.

Claude automatically installs any required Python modules — once installed, they're available for future projects too.

---

## 3. Setting Up an Anthropic API Key

Because this tool uses AI to analyse the documents, it requires an **Anthropic API key**. Here's how to get one:

**Step 1 — Log in to the Anthropic Console**
- Go to the Anthropic Console and navigate to **Manage → API Keys**.

**Step 2 — Create a New Key**
- Click **Create Key**.
- Choose a **workspace** (workspaces are used to organise different projects; the default is fine).
- Name the key (Claude will suggest a name).
- **Copy the key immediately** — it is only shown once.

**Step 3 — Store It in an Environment File**
- An **environment file** (`.env`) is where you securely store keys and secrets needed to run projects.
- Claude will create this file for you automatically when asked.
- **Important:** The `.env` file should sit **outside your project subfolders** (e.g. at the root level), so it can be shared across multiple projects.
- Open the file in a code editor (e.g. VS Code using the `code` command) and paste in your API key.
- Save the file and continue.

> ⚠️ **Security reminder:** Keep your `.env` file private. Never share it publicly or commit it to version control.

---

## 4. Viewing the Compliance Report

Once the tool runs, Claude returns a compliance report identifying issues across the files. You can open it using `open ./[filename]` in the terminal to view it in the browser.

---

## 5. Building an Interactive Dashboard

To make the results more visual and useful, Claude was asked to build a **compliance dashboard** on top of the report data.

### First attempt:
- Claude built the dashboard but added it to the existing **financial dashboard** from a previous lesson — not what was wanted.

### Correction prompt:
- Asked Claude to create a **separate, more detailed dashboard** for the compliance data.

### Final dashboard included:
- Document **compliance scores**.
- A **heat map** to make issues easy to spot at a glance.
- **Original text** flagged for changes, with suggested alternatives.

---

## 6. Auto-Fix Feature

To push the tool further, a **"Fix" button** was added to the dashboard.

### What it does:
- When clicked, triggers Claude to create **corrected versions** of all documents using the rubric.
- Saves fixed files to a dedicated **`/fixed`** folder.

### Current limitations (honest assessment):
- Models at the time of recording are **not yet reliable** at fixing documents in place — especially formatted files.
- Testing on a Word document showed that Claude **stripped much of the formatting** during the correction process.
- Auto-fixing may work better on **plain text or markdown documents** than on richly formatted files like `.docx`.

> **Verdict:** The presenter would not rely on auto-fixing for production use at this stage, but expects this capability to improve significantly in the future.

---

## 7. Reusability

All the scripts Claude built are saved in the **`/scripts`** folder of the project. This means:
- You can **re-run them any time** documents are updated.
- The dashboard will automatically reflect the latest compliance data.
- No need to rebuild the tool from scratch each time — just run the existing script.

---

## Key Takeaways
- Claude Code can scan **entire folders** of documents and assess them against a custom rubric automatically.
- The tool generates a **scored compliance report** with suggested edits — replacing repetitive manual review work.
- API keys are needed for AI-powered tools and should always be stored in a **`.env` file**, kept private, and placed at the root level so they're reusable across projects.
- Dashboards with **heat maps** make compliance issues much easier to spot at a glance.
- **Auto-fixing documents** is promising but not yet production-ready for richly formatted files — works better for simpler document types.
- All generated scripts are **saved and reusable**, making the whole system easy to maintain going forward.

---

**Previous:** [02. Build a financial dashboard with Python](02-build-a-financial-dashboard-with-python.md)  
**Next:** [04. Plan projects with Claude](04-plan-projects-with-claude.md)
