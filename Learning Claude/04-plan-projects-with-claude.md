# 04. Plan projects with Claude

> Source: <https://app.notion.com/p/38b70dfa56c48063a9d4cd32e34105dd>  
> Parent: [Building Real Tools](README.md) · [Learning Claude](../README.md)

---

## Overview
This lesson covers **how to approach working with Claude** depending on the size and complexity of your task. There is no single "correct" method — instead, there are four distinct approaches, each suited to different situations.

---

## The Four Approaches

### 1. Just Chat (No Plan Needed)
**Best for:** Simple, quick tasks where the goal is clear.

You don't always need a plan. For small tasks, just describe what you want and let Claude get on with it.

**Example used in the lesson:**
- Open a markdown file using the `@` symbol to reference it from a folder.
- Prompt: *"Rewrite it so the tone matches the marketing rubric, keep the structure the same, but tighten the language and remove the marketing clichés."*
- Claude edits the document directly.

**Key takeaway:** Don't overthink it. If it's a quick task, just chat with the tool.

---

### 2. Brain Dump + Brainstorming
**Best for:** Complex tasks where you have a vague idea and want Claude to help shape it.

This is the presenter's **personal favourite** approach. Instead of telling Claude exactly what to build, you describe the situation and invite it to ask questions and suggest solutions.

**How it works:**
1. **Brain dump** — tell Claude what you're trying to do in plain language. Include context, the problem, and any rough ideas.
2. **Invite creativity** — explicitly ask Claude to ask you questions and suggest a few different approaches to designing the system.
3. **Avoid over-specifying** — don't drown Claude in technical details upfront, as this limits its creativity.

**Example prompt used:**
> "I have a folder of marketing documents and a rubric. We currently review everything manually before publishing, and it's a little slow. I'm thinking about building some sort of tool that checks documents against that rubric and flags any issues. I'm not sure what the best approach would be. Ask me questions and suggest a few ways this system could be designed."

**What Claude did:**
- Recognised a related tool that had been built previously in the session.
- Instead of starting from scratch, suggested ways to improve the existing tool.
- Offered three different design options (A, B, or C) for the user to choose from — or ask further questions.

**Key takeaway:** Letting Claude ask questions **unlocks its creativity**. It will surface angles and ideas you hadn't considered.

---

### 3. Plan Mode
**Best for:** Vague ideas where you want to see a full implementation strategy before any work begins.

Plan Mode is a built-in Claude Code feature that makes Claude produce a **detailed plan** before taking any action. It's more thorough than a simple chat, but also takes significantly longer.

**How it works:**
1. Enter Plan Mode in Claude Code.
2. Give Claude a goal (e.g., *"Build a tool that analyses the financial spreadsheets in the folder, looks for trends in revenue and expenses, and generates a report."*).
3. Claude does a **deep analysis** of the existing folder contents first.
4. It then produces a comprehensive, step-by-step plan — including which scripts to create, what existing scripts to reuse, and what outputs will be generated.
5. You review the plan and can suggest changes, disagree with parts, or ask for modifications.
6. Once you accept the plan, Claude executes it.

**Example output from the lesson:**
- Created new scripts to analyse spreadsheets.
- Reused an existing `createcharts.py` script to generate charts.
- Produced a new presentation with financial analysis included.
- Created an `executivebriefing.py` script that can be re-run any time from the terminal.

**Pros and cons:**

| Pros | Cons |
|------|------|
| Comprehensive and detailed | Takes several minutes to complete |
| You retain full control before anything is built | Overkill for simple tasks |
| Great for complex or vague briefs | Not necessary for every task |

**Key takeaway:** Plan Mode is powerful for big projects, but a simple discussion is enough for most things. Use it when you genuinely need to see how Claude would structure an implementation.

---

### 4. Smart PRD Generator (Interactive Questionnaire)
**Best for:** Formal project planning, especially when building applications, and when you want to consider business goals alongside functionality.

This is a **custom tool** the presenter built, available at **itsplaytime.com → Agents → Smart PRD Generator**. It functions like an interactive Plan Mode — but instead of Claude deciding everything, it walks you through a structured questionnaire.

**How it works:**
- Claude takes on the role of a **product manager and UX architect**.
- It guides you through **8 sections**, asking one clarifying question at a time:
  1. Primary users
  2. Problems to solve
  3. Capabilities
  4. Inputs
  5. User flows
  6. Constraints
  7. Business goals
  8. *(additional sections)*
- For each section, Claude:
  1. Creates a **draft** based on what you've said so far.
  2. Asks a **clarifying question** to improve it.
  3. Revises the draft based on your answers.
  4. Moves to the next section once you type **"approve"**.
- At the end, Claude produces a **complete PRD (Product Requirements Document)** you can feed into Claude Code or any other tool to build the project with better context.

**Example from the lesson:**
- Starting prompt: *"Help me build a marketing document compliance system. Design the project architecture and implementation plan."*
- Claude asked about primary users first, drafting a user profile and refining it with each answer.
- User types "approve" to advance to the next section (*"Which problem do you want to solve?"*).

**Tip:** You can view the full underlying prompt on the website to understand how the system is structured — and adapt it for your own purposes.

**Key takeaway:** The PRD process forces you to think carefully about **product questions** (users, goals, constraints) before writing any code — making the end result significantly better.

---

## Choosing the Right Approach

| Situation | Best Approach |
|-----------|--------------|
| Quick, clear task | **Just Chat** |
| Vague idea, want creative input | **Brain Dump + Brainstorm** |
| Complex task, want a full plan first | **Plan Mode** |
| Building an app, want structured product thinking | **Smart PRD Generator** |

> *"There's no optimal way to build projects. Sometimes you want to discuss things with the tool by just chatting. A lot of people love Plan Mode because it's very detailed. But me, I like the PRD process because it helps me think about key product questions that I want to consider before I start building."*

---

**Previous:** [03. Automate document compliance reviews](03-automate-document-compliance-reviews.md)  
**Next:** [Extending Claude →](../extending-claude/README.md)
