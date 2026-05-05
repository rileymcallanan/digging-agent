# Digging Agent

A starter for the patient information work you didn't sign up for, but have to do.

Captures your beat, your trusted sources, and your preferred output format — then uses them to produce a daily digest of monitoring, gathering, and triage tasks. The agent does the digging. You do the journalism.

Built for the Women in Journalism workshop on AI agents — May 2026.

---

## Three ways to use it

| | Skill (Claude or Codex) | Standalone system prompt | Claude Project (one-click) |
|---|---|---|---|
| **Works with** | Claude (claude.ai or Desktop) — Free, Pro, Max, Team, Enterprise. Codex CLI, IDE, app. | Any AI tool with a system prompt / custom instructions field (ChatGPT, Gemini, Claude, Cursor) | Claude (claude.ai or Desktop) |
| **Setup** | Download zip, upload to Skills (Claude) or drop into `.agents/skills/` (Codex) | Copy one file, paste as system prompt | Click link, clone Project |
| **Best for** | Claude or Codex users who want it to feel native | Anyone using a tool other than Claude or Codex | Fastest start — pre-loaded and ready |
| **File** | `SKILL.md` + 3 context files | `SYSTEM_PROMPT.md` + 3 context files | _(no files — Project link below)_ |

All three paths share the same three context files (`beat-notes.md`, `source-list.md`, `output-format.md`). You edit those once for your beat. They become your editorial layer — portable across all three paths.

---

## Option 1: Skill (Claude or Codex)

For journalists using Claude or Codex. Both follow the same [open skill standard](https://agentskills.io) — the same `SKILL.md` works in either.

Skills are available on Claude Free, Pro, Max, Team, and Enterprise plans, and in Codex CLI / IDE / app.

### Install (Claude)

1. **Download this repo as a ZIP** (green Code button → Download ZIP). Unzip.
2. **Edit the three context files** — `beat-notes.md`, `source-list.md`, `output-format.md`. Replace the example content (a UK health policy reporter) with your own. _This is the work that makes the agent yours._
3. **Re-zip the folder** (the one containing `SKILL.md` and your edited context files).
4. **In Claude:** go to *Customize > Skills* → click `+` → *Create skill* → *Upload a skill* → upload your ZIP.
5. **Toggle the skill on.**

> **Prerequisite:** Code execution must be enabled in *Settings > Capabilities*. (Free, Pro, Max users can enable this themselves.)

### Install (Codex)

1. **Clone or download this repo.** Edit the three context files for your beat.
2. **Drop the folder into `.agents/skills/`** at the root of your project (or in `~/.agents/skills/` for a user-level skill).
3. **Restart Codex.** The skill is auto-detected.
4. **Invoke explicitly** with `$digging-agent`, or describe a digging task and let Codex match it implicitly.

### Use it

In any Claude conversation, say:

> *Run today's digest. Focus on [topic]. Sources: [URLs]. Time window: last 24 hours.*

Or use the daily prompt template in `DAILY_PROMPT.md`.

---

## Option 2: Standalone system prompt

For journalists using ChatGPT, Gemini, Cursor, or any other AI tool with a system prompt or custom instructions field. Also works with Claude if you prefer not to use Skills.

### Install

1. **Download this repo as a ZIP** (or clone). Unzip.
2. **Open `SYSTEM_PROMPT.md`** and copy everything between `=== BEGIN SYSTEM PROMPT ===` and `=== END SYSTEM PROMPT ===`.
3. **Paste it into your AI tool's instruction field:**
   - **ChatGPT:** Create a Custom GPT, or open a Project → *Customize* → instructions field.
   - **Gemini:** *Settings > System instructions*.
   - **Claude (Project):** Project settings → *Project instructions*.
   - **Cursor:** `.cursorrules` file at the project root.
4. **Edit the three context files** — `beat-notes.md`, `source-list.md`, `output-format.md` — for your beat.
5. **Attach or paste the three edited context files** into your tool's knowledge / project files / context window at the start of each session.

### Use it

In your conversation, say:

> *Run today's digest. Focus on [topic]. Sources: [URLs]. Time window: last 24 hours.*

Or use the daily prompt template in `DAILY_PROMPT.md`.

---

## Option 3: Claude Project (one-click clone)

The fastest start. A pre-configured Claude Project with the system prompt loaded and the three context-file templates ready to edit.

### Install

1. **Click here:** [Claude Project share link — to be added after the workshop]
2. **Clone the Project** into your account.
3. **Open the three context files** in the Project's knowledge and edit them for your beat.
4. **Run the daily prompt** in any conversation in the Project.

That's it. No upload, no zip, no copy-paste.

---

## What's in this repo

```
README.md                ← This file. Read first.

SKILL.md                 ← The agent, packaged as a Claude Skill.
SYSTEM_PROMPT.md         ← The agent, as a standalone system prompt.

beat-notes.md            ← Your editorial position on what matters in your patch.
source-list.md           ← Your editorial position on whose work to trust.
output-format.md         ← Your editorial position on how output is shaped.

DAILY_PROMPT.md          ← The short prompt you paste each morning.
```

---

## Four starter recipes (same skeleton, different jobs)

The same agent works for several common journalism patterns. Detailed recipes will be added to this repo after the workshop:

1. **Beat Monitor** — watch a regulator, court, company, or council. Flag when something changes.
2. **Source Triage** — compare how multiple outlets covered the same story.
3. **Document Scanner** — run over a folder of PDFs, transcripts, or FOI responses to surface anomalies and patterns.
4. **Trend Tracker** — track a topic across many sources over weeks or months. Flag what's shifting.

Each recipe uses the same three context files; what changes is what you put in them.

---

## Want it to run on its own?

What this repo gives you is a *configured agent* you trigger manually. If you want it to run automatically, three options:

- **Run it yourself, every morning.** What this take-home gives you. Free. ~30 seconds.
- **Claude Cowork** (paid: Pro/Max). Paste your daily prompt into Cowork, type `/schedule`, and it'll run on a cadence — *as long as your laptop is awake and Claude Desktop is open*.
- **Python + GitHub Actions cron** (free, requires a small amount of code). Runs in the cloud without your machine. Recipe coming to this repo after the workshop.

---

## A note on privacy

The context files are plain markdown. Nothing is encrypted, nothing is sent anywhere beyond your normal AI tool usage. Don't put anything sensitive in them — source contact details, embargoed material, anything you wouldn't paste into a chat. Treat them as configuration, not as a secure store.

---

## Disclaimer

This is a prompt-engineering framework, not a journalist. The AI does the gathering and triage; you do the journalism. Standard cautions apply:

- **AI hallucinates.** Verify every fact, name, statistic, and link before publication.
- **AI cannot verify.** It works only with what you give it and what it can fetch. It has no access to your reporting.
- **AI mangles attributions.** Quotes and source attributions can be subtly wrong even when the underlying facts are right. Check both.
- **AI cannot judge sensitivity.** Legal exposure, source safety, embargo discipline, ethical calls — those remain yours.

The agent surfaces material. You decide what's a story.

---

## Credit

Built by Parvathi (Ale) Subbiah · AI Lab, The Economist
For Women in Journalism · May 2026

Mirrors the structure of [Script Wizard](https://github.com/tristanwerkmeister/scriptwizard) by Tristan Werkmeister (Reuters), who walked the same community through AI-assisted social video scripts the previous week.

Questions, suggestions, or you've built something interesting with this? [contact details to be added]
