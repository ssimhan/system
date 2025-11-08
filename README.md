# Claude Code Starter Repo

This repo scaffolds a Claude Code–based implementation system, adapted from best practices in the Nov 7 Office Hours.

Use this template to kick off any AI-assisted coding project using Claude Code + GitHub + Linear + Markdown.

---

## Claude Code Implementation Workflow — Inspired by Helen's System (Nov 7 Office Hours)

### Overview

This document outlines a repeatable Claude Code-based implementation workflow, informed by Helen's system and adapted for build-in-public or solo dev environments. It assumes use of:

* Claude Code (web and/or desktop)
* GitHub repo for all code + documentation
* Linear for milestone/sprint tracking
* Optional: Airtable for structured data tracking (vs Notion MCPs)

---

### 🧠 Philosophy

* **Codify everything**: Claude has no memory. Document all decisions and context in markdown files.
* **Chunk your work**: Smaller tasks = better Claude performance. Don’t ask for full apps in one go.
* **Ground your agents**: Keep your PRD/vision doc *in context* at all times.

---

### 🛠️ Folder Structure

```
/.github/          # Optional GitHub Actions
/claude/           # Implementation plan + learnings from Claude
  implementation-plan.md
  learnings/
/commands/         # Reusable Claude commands like /implement
/docs/             # Vision, setup instructions, etc.
  product-vision.md
  setup-instructions.md
/skills/           # Reusable Claude skills (e.g., refactor, frontend)
/scripts/          # Deployment, migrations, etc.
/src/              # App logic or script code
.gitignore         # Ignore system & build files
README.md          # Project overview and folder guide
package.json       # (Empty or default for now)
```

---

### 📌 How to Use

1. Use Claude Code to generate `/docs/product-vision.md` – this is your PRD.
2. Use Claude Code to generate `/claude/implementation-plan.md`.
3. Track any Claude insights or decisions in `/claude/learnings/`.
4. Store custom commands in `/commands/`, skills in `/skills/`.
5. Use Linear for polish tasks if needed.

> 🧠 **Pro Tip:** Claude has no memory — keep everything important in Markdown files in this repo.

---

### Step-by-Step Workflow

#### 1. **Create your vision / PRD**

* Write a clear product doc.
* Save to `/docs/product-vision.md`
* Claude prompt:

  > Anytime you are lost, refer to the product vision doc.

#### 2. **Draft Implementation Plan**

* Ask Claude to break down the project into logical stages.
* Use voice like: “Imagine a junior dev will follow this. Be overly explicit.”
* Save plan in `/claude/implementation-plan.md`
* Review and revise manually.

#### 3. **Track Learnings and Decisions**

* Anytime Claude gives an interesting prototype or insight:

  * Save the transcript snippet in `/learnings/`
  * Include your interpretation/decision.

#### 4. **Work via Custom Commands:**

* Claude reads `implementation-plan.md`
* Identifies next incomplete task
* Begins implementation
* Updates status (in-progress ✅ / complete ✅)
* Commits code when complete

#### 5. **Use Commands Strategically**

* `/implement` → pick up where you left off
* `/context` → check how much memory is used
* `/commit` → stage, format, lint, build, commit
* `/clear` → reset context after big commits

---

### ⚙️ Tool-Specific Tips

#### Claude Code Web vs Desktop

* **Desktop**: Better for complex builds, local file access
* **Web**: Better for PRs, fast bugfixes, repo-linked sessions

#### Linear vs Implementation Plan

* Use `implementation-plan.md` for big blocks of features
* Use Linear for fine polish (e.g., thumbnails, CSS bugs)

---

### 🧱 Data & Backend Notes

* Don’t ask Claude to change actual DBs.
* Instead, create SQL migrations (Drizzle ORM, Prisma)
* Use mock data for 80% of build; only formalize DB schema when confident

---

### ✅ Commit Cadence

* Commit frequently to avoid Claude’s context compacting
* Compacting = very slow, loses flow/state
* Use `/commit` and write atomic commits
