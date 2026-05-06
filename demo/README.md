# /demo/ — the live workshop version

This folder is the **clean, install-ready** version of the digging agent used in the live workshop demo.

It contains the same `SKILL.md` and `DAILY_PROMPT.md` as the root of the repo, plus *cleaned* versions of the three context files — no editing guidance, no italic notes, no scaffolding for the journalist setting it up. Just the example content, ready for the agent to read.

## Why two versions?

The root files are the **teaching version** — they include inline guidance to help you understand what each section of the context files is for. The agent will see those notes too, which can muddy its output.

This `/demo/` folder is the **deployment version** — clean of all setup commentary. It's what you'd want to install if you just want to run the agent immediately.

## How to use this folder

1. Zip the contents of this folder (`SKILL.md` + the three context files).
2. Upload the zip as a Claude Skill (`Customize > Skills > Create skill > Upload a skill`).
3. Edit the three context files to reflect *your* beat (replace the UK health policy reporter example).
4. Re-zip and re-upload, or edit the skill in place.

For full instructions, see the main `README.md` at the root of the repo.
