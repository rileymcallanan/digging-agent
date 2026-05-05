# Source list

> This file is your editorial position on whose work to trust, whose to read sceptically, and whose to treat as noise. The agent uses it to weight what it surfaces and to flag confidence levels.
>
> The richer this file, the better the agent's triage. Add to it as you build your beat.

---

## Tier 1 — Trusted

*Sources you treat as reliable on first read. The agent can cite them without strong caveats. Specialist publications, peer-reviewed journals, named beat reporters whose work you respect, primary sources (government data, official reports).*

**Example:**

**Specialist publications**
- Health Service Journal (HSJ) — reliable on NHS operations, workforce, finance
- Pulse — reliable on GP-side stories
- Pharmaceutical Journal — reliable on community pharmacy and dispensing

**Beat reporters (any outlet)**
- Denis Campbell (Guardian) — health policy
- Eleanor Hayward (Times) — NHS, social care
- Hugh Pym (BBC) — health editor
- Andrew Gregory (Guardian) — health, science

**Primary sources**
- NHS England operational stats and workforce data
- ONS health surveys
- NICE consultation pages and committee minutes
- DHSC published guidance and policy papers
- Peer-reviewed journals: Lancet, BMJ, NEJM, JAMA

**Think tanks I trust on health policy**
- Nuffield Trust
- The King's Fund
- Health Foundation
- IFS (on health spending)

---

## Tier 2 — Read with care

*Sources worth reading but where you check claims independently. Could be partisan, agenda-driven, or just inconsistent. Useful for tip-offs, not for direct citation.*

**Example:**
- Industry trade press (PMLive, Pharmaphorum) — useful for pharma signals, but read for industry framing
- Royal College press releases — reliable but always advocating
- Patient advocacy groups — useful for case studies, but check funding sources
- Politico's London Influence health section — well-sourced but rumour-heavy
- Most national-paper health coverage outside the named reporters above

---

## Tier 3 — Noise / sceptical

*Sources to discount or ignore. The agent should not surface stories from these unless multiple Tier 1 sources have picked them up.*

**Example:**
- Tabloid health "miracle cure" stories
- Press releases from supplement companies, private clinics, and consumer health brands
- Wellness influencers on social media
- Partisan think tanks running campaigns rather than analysis
- AI-generated content farms
- [Any specific sites you want explicitly filtered]

---

## Sources I want monitored daily

*A short list of URLs, RSS feeds, or named writers the agent should always check, in priority order. The daily prompt will use this.*

**Example:**
1. https://www.hsj.co.uk/news (Tier 1)
2. https://www.england.nhs.uk/news/ (primary)
3. https://www.gov.uk/government/organisations/department-of-health-and-social-care (primary)
4. https://www.nice.org.uk/news (primary)
5. The latest Denis Campbell columns (Guardian)
6. The latest HSJ workforce coverage

---

## How I want sources flagged in output

*A note for the agent on attribution style. The agent will follow this.*

**Example:**
- Tier 1 sources: cite by name without caveat. *"HSJ reports..."*, *"NHS England's latest workforce data shows..."*
- Tier 2 sources: cite with attribution context. *"According to a Politico London Influence item (which is well-sourced but typically rumour-heavy)..."*
- Tier 3 sources: do not cite. If a Tier 3 source is the only one carrying a story, flag it as: *"Currently only reported by [source], not yet picked up by trusted outlets — monitor."*
