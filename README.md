# wdz_style_ClaudeCode

`wdz_style_ClaudeCode` is the maintained source repository for WDZ's Claude Code / CC-DS research style skill.

It packages WDZ's preferred research, coding, experiment, and paper-writing workflow for fast-moving CS topics such as LLM, VLM, Agents, VLN, CV, RL, Data Mining, ML/DL, and Medical AI.

The skill keeps the same high-level WDZ style as the Codex version, while framing the behavior for Claude Code as a worker-oriented, token-efficient execution agent.

## Install

Copy the repository contents into the Claude skills directory:

```powershell
Copy-Item -Recurse -Force .\* C:\Users\Administrator\.claude\skills\wdz_style_cc
```

If hidden files ever need to be copied too:

```powershell
Get-ChildItem -Force | Copy-Item -Recurse -Force -Destination C:\Users\Administrator\.claude\skills\wdz_style_cc
```

## Structure

```text
SKILL.md
references/
  WDZ_RESEARCH_STYLE.md
  WDZ_RESEARCH_STYLE_ZH.md
```

## Maintenance

- Edit `SKILL.md` for the concise Claude Code behavior policy.
- Edit `references/WDZ_RESEARCH_STYLE.md` as the authoritative English reference.
- Edit `references/WDZ_RESEARCH_STYLE_ZH.md` as the Chinese reference.
- Keep the installed copy in `C:\Users\Administrator\.claude\skills\wdz_style_cc` synchronized after updates.
