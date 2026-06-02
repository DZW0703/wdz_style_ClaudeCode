# wdz_style_ClaudeCode

[English](README.md) | [简体中文](README_ZH.md)

`wdz_style_ClaudeCode` is the maintained source repository for WDZ's Claude Code / CC-DS research style skill.

It packages WDZ's preferred research, coding, experiment, and paper-writing workflow for fast-moving CS topics such as LLM, VLM, Agents, VLN, CV, RL, Data Mining, ML/DL, and Medical AI.

The skill keeps the same high-level WDZ style as the Codex version, while framing the behavior for Claude Code as a worker-oriented, token-efficient execution agent.

## Skill Routing

Before execution, the skill should choose the strongest available specialized workflow:

- PPT, presentation, slides, or document-to-deck tasks -> use **ppt-master**.
- Word / `.docx` creation, editing, inspection, polishing, or conversion -> use **docx**.
- Research, survey, deep research, literature review, paper search, or benchmark mapping -> use **Academic Research** deep-research plus relevant **nature-skills**.
- If Codex delegated the task, follow Codex's route unless it is clearly mismatched; flag mismatches concisely.

## TaskPorter / Reasonix

WDZ's machine has Reasonix and Claude Code, both backed by DeepSeek V4 Pro. For low-risk, token-heavy delegation, Codex should prefer TaskPorter -> Reasonix/DS Pro.

If `worker_*` tools are missing, check `taskporter-mcp` in `C:\Users\Administrator\.codex\config.toml`; if MCP tools are unavailable in the current session, fall back to:

```powershell
node C:\Users\Administrator\.codex\tools\TaskPorter\reasonixctl.js doctor
node C:\Users\Administrator\.codex\tools\TaskPorter\reasonixctl.js ask "TASK" --dir "PROJECT_PATH" --model pro
```

Reasonix is reached through `reasonix acp` / stdio JSON-RPC, not a dashboard HTTP URL.

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
- Edit `references/WDZ_RESEARCH_STYLE_ZH.md` as the Simplified Chinese reference.
- Keep `README.md` and `README_ZH.md` synchronized.
- Keep the installed copy in `C:\Users\Administrator\.claude\skills\wdz_style_cc` synchronized after updates.
