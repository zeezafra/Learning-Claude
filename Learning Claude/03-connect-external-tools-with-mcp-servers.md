# 03. Connect external tools with MCP servers

> Source: <https://app.notion.com/p/38b70dfa56c480989347d755a6f3c7b9>  
> Parent: [Extending Claude](README.md) · [Learning Claude](../README.md)

---

## Overview
Software systems don't naturally communicate with each other. While developers have long used **APIs** (Application Programming Interfaces) to bridge them, working with APIs typically requires learning specialised languages tailored to each service. **MCP servers remove that barrier entirely**, letting Claude connect to external tools and services using plain natural language. Uses external knowledge for your local files.

---

## 1. What Is MCP?

**MCP** stands for **Model Context Protocol**.

Think of it as a **universal translator** between Claude and any external system or data source. The MCP server sits in the middle and converts your natural language requests into the machine code that the external system understands — and brings the results back to Claude.

- Without MCP → you'd need to learn the API language for every service.
- With MCP → you just ask Claude in plain English.

---

## 2. Checking What MCP Servers Are Installed

To see which MCP servers are already available in your environment, run the built-in command:
```
/mcp
```
This displays a list of all installed MCP servers and their connection status. Some may require additional authentication before they're ready to use.

---

## 3. Installing a New MCP Server

MCP servers are available online — **GitHub** is a good place to find them. The lesson uses the **Wikipedia MCP server** as an example.

### What the Wikipedia MCP Server Does
- Search Wikipedia articles.
- Retrieve full article content.
- Pull other structured information from Wikipedia.

### Installation Steps

**Step 1 — Find the server on GitHub**  
Search GitHub for the MCP server you want (e.g. "Wikipedia MCP server"). Each listing includes a description of what it can do and installation instructions.

**Step 2 — Install via pip**  
Most MCP servers can be installed directly from the terminal using `pip`:
```bash
pip install mcp-server-wikipedia
```
Claude can run this installation command for you — just tell it to install and configure the server.

**Step 3 — Restart Claude**  
After installation, quit Claude and relaunch it:
```
exit
claude
```
Then run `/mcp` again to confirm the new server appears as connected and ready.

> The installed server is just a file saved on your computer — lightweight and easy to manage.

---

## 4. Using an MCP Server

Once connected, you use the server simply by mentioning it in your prompt. No special syntax required.

### Example 1 — External knowledge only

**Prompt:**
> "Use the Wikipedia MCP server to summarise the history of cloud computing and explain the major milestones that led to modern cloud platforms."

Claude pulls relevant Wikipedia articles and returns a structured summary with the information from those pages.

---

## 5. Combining MCP with Local Files

The real power of MCP comes from **blending external knowledge with your own local data**. Claude can pull information from an MCP server and cross-reference it with files in your project — in the same prompt.

### Example 2 — External knowledge + local spreadsheet

**Prompt:**
> "Use the Wikipedia MCP server to summarise the history of e-commerce, then compare that background with the trends shown in the spreadsheet US online retail sales."

**What Claude does:**
1. Fetches the e-commerce history article from Wikipedia via the MCP server.
2. Loads the local `US online retail sales` spreadsheet from the project folder.
3. Correlates the two data sources.
4. Produces insights that neither source could provide on its own.

---

## Key Takeaways
- **MCP (Model Context Protocol)** is a translator that lets Claude connect to external tools and services using natural language — no API coding required.
- Use `/mcp` to see which servers are installed and their connection status.
- New MCP servers are found on **GitHub** and installed via **`pip`** — Claude can handle the installation for you.
- After installing a server, **restart Claude** to activate it.
- To use a server, simply **mention it in your prompt** — no special commands needed.
- The biggest opportunity is **combining MCP data with local files** — pulling external knowledge and correlating it with your own project data to generate insights neither source could produce alone.

---

**Previous:** [02. Create and Use Skills](02-create-and-use-skills.md)  
**Next:** [← Back to Learning Claude](../README.md)
