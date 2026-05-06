# Digging Agent

A starter for the patient information work you didn't sign up for, but have to do.

Captures your beat, your trusted sources, and your preferred output format — then uses them to produce a daily digest of monitoring, gathering, and triage tasks. The agent does the digging. You do the journalism.

Built for the Women in Journalism workshop on AI agents — May 2026.

---

## Two ways to use it

| | Skill (Claude or Codex) | Standalone system prompt |
|---|---|---|
| **Works with** | Claude (claude.ai or Desktop) — Free, Pro, Max, Team, Enterprise. Codex CLI, IDE, app. | Any AI tool with a system prompt / custom instructions field (ChatGPT, Gemini, Claude, Cursor) |
| **Setup** | Fork repo, edit on GitHub, download zip, upload to Skills (Claude) or drop into `.agents/skills/` (Codex) | Copy one file, paste as system prompt |
| **Best for** | Claude or Codex users who want it to feel native | Anyone using a tool other than Claude or Codex |
| **File** | `SKILL.md` + 3 context files | `SYSTEM_PROMPT.md` + 3 context files |

Both paths share the same three context files (`beat-notes.md`, `source-list.md`, `output-format.md`). You edit those once for your beat. They become your editorial layer — portable across both paths.

> **Want to install it right now?** The repo also contains a `/demo/` folder with **install-ready** versions of the context files — same agent, but stripped of the editing guidance you see in the root files. If you just want to grab something that runs in 60 seconds, zip the contents of `/demo/` and upload it as a Claude Skill.
>
> The root files are the **teaching version** — they include inline guidance to help you understand what each section is for. Use those when you're ready to adapt the agent for your own beat.

---

## Option 1: Skill (Claude or Codex)

For journalists using Claude or Codex. Both follow the same [open skill standard](https://agentskills.io) — the same `SKILL.md` works in either.

Skills are available on Claude Free, Pro, Max, Team, and Enterprise plans, and in Codex CLI / IDE / app.

### Install (Claude)

1. **Fork this repo** (top-right of the GitHub page). This makes a copy you own and can edit.
2. **Edit the three context files in your fork** — `beat-notes.md`, `source-list.md`, `output-format.md`. Click any file → pencil icon → edit in the browser → commit. Replace the example content (a UK health policy reporter) with your own. *This is the work that makes the agent yours.*
3. **Download your fork as a ZIP** (green Code button → Download ZIP). Unzip.
4. **In Claude:** go to *Customize > Skills* → click `+` → *Create skill* → *Upload a skill* → upload your ZIP.
5. **Toggle the skill on.**

> **Prerequisite:** Code execution must be enabled in *Settings > Capabilities*. (Free, Pro, Max users can enable this themselves.)

### Install (Codex)

1. **Clone or download this repo.** Edit the three context files for your beat.
2. **Drop the folder into `.agents/skills/`** at the root of your project (or in `~/.agents/skills/` for a user-level skill).
3. **Restart Codex.** The skill is auto-detected.
4. **Invoke explicitly** with `$digging-agent`, or describe a digging task and let Codex match it implicitly.

### Use it

Once the skill is installed, in any Claude conversation:

> *Run today's digest.*

Or with more guidance:

> *Run today's digest. Focus on the GP contract negotiations. Sources: HSJ, Pulse, BMA press releases. Time window: last 48 hours.*

Or for a one-off task:

> *Use my digging agent to compare how the Guardian, Times, and BBC covered yesterday's NHS workforce announcement.*

The skill takes care of the rest. You don't need to paste a long template each morning — the recipe lives inside the skill.

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

Same prompts as above. Just talk to the model normally; the system prompt handles the rest.

---

## How to edit your context files

The agent's quality depends entirely on the three context files. You don't need to install a code editor to edit them — markdown is just plain text. Two journalist-friendly ways:

**Option A — Edit on GitHub directly.** Fork this repo, then click any `.md` file → pencil icon (top right) → edit in your browser → commit. No download, no local tools. The cleanest workflow if you want your editorial standards version-controlled and portable.

**Option B — Let Claude help you write them.** If you're staring at an empty template, paste the file into a Claude conversation and say:

> *"This is a context file for an AI agent that does research for me. Help me adapt it — I cover [your beat]. Ask me questions to fill it in properly."*

Claude will interview you, generate a properly-formatted file, and you copy the result back. You'll have used AI to set up your AI.

If you prefer a local editor: any plain-text editor works (VS Code, Sublime, BBEdit, even TextEdit on Mac with *Format → Make Plain Text*). Avoid Word — it'll add formatting that breaks the markdown.

---

## Running multiple beats

If you cover more than one patch — or you want a separate digging agent for a specific project — you need a separate skill per beat. The cleanest way is to make a separate copy of the files for each one.

Two ways to do this:

**On GitHub** — Fork this repo a second time (or third). Rename your second fork to something specific (`digging-agent-climate`, `digging-agent-courts`). Edit the context files in that fork for the new beat. Download as a zip. Upload to Claude Skills.

**Locally** — After forking once and downloading, duplicate the folder on your machine. Rename to `digging-agent-climate/`. Edit the context files in the copy. Zip and upload as a new skill.

Either way, **edit the `SKILL.md` frontmatter** in the new copy:

- `name:` should be unique — e.g., `digging-agent-climate`
- `description:` should mention the new beat — e.g., *"A digging agent for a climate reporter — produces daily digests on energy policy, COP negotiations, and emissions data."*

You can have as many digging agents installed as you want. To invoke one specifically, say *"run my climate digging agent"* — Claude matches the name. Or describe the task — *"give me a digest of yesterday's COP coverage"* — and Claude picks the right skill from the descriptions.

**Why one skill per beat, rather than one giant skill with everything?** The skill's `description` is what triggers it. A single skill with five beats stuffed in would trigger on anything vaguely beat-shaped, and you'd lose the precision. One skill, one beat — that boundary is itself an editorial decision.

---

## What's in this repo

```
README.md                ← This file. Read first.

SKILL.md                 ← The agent, packaged as a Claude / Codex Skill.
SYSTEM_PROMPT.md         ← The agent, as a standalone system prompt.

beat-notes.md            ← Your editorial position on what matters in your patch.
source-list.md           ← Your editorial position on whose work to trust.
output-format.md         ← Your editorial position on how output is shaped.

demo/                    ← Clean install-ready version (no editing guidance).
                           Used in the live workshop demo.
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

Mirrors the structure of [Script Wizard](https://github.com/tristanwerkmeister/scriptwizard) by Tristan Werkmeister (Reuters), who walked the same community through AI-assisted social video scripts earlier in this series.

Questions, suggestions, or you've built something interesting with this? [contact details to be added]
