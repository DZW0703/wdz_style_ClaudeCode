# wdz_style_ClaudeCode

[English](README.md) | [简体中文](README_ZH.md)

`wdz_style_ClaudeCode` 是 WDZ 的 Claude Code / CC-DS 研究风格 skill 的维护仓库。

它封装了 WDZ 偏好的科研、编码、实验和论文写作流程，适用于 LLM、VLM、Agent、VLN、CV、RL、数据挖掘、ML/DL、医学 AI 等快速变化的 CS 研究方向。

该 skill 与 Codex 版本保持同一套 WDZ 高层风格，但更强调 Claude Code 作为 worker 的执行定位和 token 效率。

## 技能路由

执行前应先选择最强的专门工作流：

- PPT、presentation、slides，或任意文档转演示文稿 -> 使用 **ppt-master**。
- Word / `.docx` 创建、编辑、检查、润色或转换 -> 使用 **docx**。
- 调研、深度调研、文献综述、论文检索、来源筛选或 benchmark 梳理 -> 使用 **Academic Research** 的 deep-research，并结合相关 **nature-skills**。
- 如果任务来自 Codex 委派，默认遵循 Codex 指定的技能路线；若明显不匹配，简洁指出并返回。

## TaskPorter / Reasonix

WDZ 的电脑上有 Reasonix 和 Claude Code，二者都可使用 DeepSeek V4 Pro。对于低风险、耗 token 的委派任务，Codex 应优先使用 TaskPorter -> Reasonix/DS Pro。

如果看不到 `worker_*` 工具，先检查 `C:\Users\Administrator\.codex\config.toml` 是否注册了 `taskporter-mcp`；如果当前会话仍没有 MCP 工具，则兜底调用：

```powershell
node C:\Users\Administrator\.codex\tools\TaskPorter\reasonixctl.js doctor
node C:\Users\Administrator\.codex\tools\TaskPorter\reasonixctl.js ask "TASK" --dir "PROJECT_PATH" --model pro
```

Reasonix 通过 `reasonix acp` / stdio JSON-RPC 接入，不是 dashboard HTTP 地址。

## 安装

将仓库内容复制到 Claude skills 目录：

```powershell
Copy-Item -Recurse -Force .\* C:\Users\Administrator\.claude\skills\wdz_style_cc
```

如果以后需要复制隐藏文件：

```powershell
Get-ChildItem -Force | Copy-Item -Recurse -Force -Destination C:\Users\Administrator\.claude\skills\wdz_style_cc
```

## 结构

```text
SKILL.md
references/
  WDZ_RESEARCH_STYLE.md
  WDZ_RESEARCH_STYLE_ZH.md
```

## 维护

- 编辑 `SKILL.md` 来维护 Claude Code 的精简行为策略。
- 编辑 `references/WDZ_RESEARCH_STYLE.md` 作为英文权威参考。
- 编辑 `references/WDZ_RESEARCH_STYLE_ZH.md` 作为简体中文参考。
- 保持 `README.md` 与 `README_ZH.md` 同步。
- 更新后同步已安装副本：`C:\Users\Administrator\.claude\skills\wdz_style_cc`。
