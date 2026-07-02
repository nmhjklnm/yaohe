---
id: awesome-claude-code
name: Awesome Claude Code（47.8k★，Claude Code 生态最大列表）
lang: en
automatable: manual-only
submission_method: web-form
target: https://github.com/hesreallyhim/awesome-claude-code/issues/new?template=recommend-resource.yml
audience: Claude Code 用户的选型入口；收录后可挂 "Mentioned in Awesome Claude Code" 徽章
threshold: 精选制；机器人自动校验字段/URL/查重/license + 人工审核
verified: 2026-07-02
---

# Awesome Claude Code

**红线：禁止 PR、禁止 gh CLI 提交**。官方原话："ALL RECOMMENDATIONS MUST BE MADE USING THE WEB UI ISSUE FORM TEMPLATE, OR YOU RISK BEING BANNED"。必须真人在网页 issue 表单填写；审核通过后机器人自动开 PR 合并。

## format_spec

表单字段：Display Name / Category（选 Tooling 或 Slash-Commands 等）/ Sub-Category / Primary Link / Author Name / Author Link / License / 1-2 句功能描述。

描述要求**证据导向**：给出可复现验证的具体用法（如实际 prompt/命令），别写「装上见证奇迹」式空话。若插件涉及非 Anthropic 服务器的网络请求 / 修改系统文件 / 遥测 / 需要 bypass-permissions，必须在描述中明确声明。

## rules

- 近期因 spam 有临时封禁先例，措辞谨慎、一次提交、不催审
- 仅 Claude Code 生态资源适用

## submit

manual-only：生成表单各字段的值 → 用户网页填写。

次选（专收 plugin 的列表，865★，标准 PR 制）：`ccplugins/awesome-claude-code-plugins`——在 `plugins/<name>` 加目录 + README 对应分类加一行 `- [name](./plugins/name)`，有 README-zh.md 可同时提中文条目，此列表可走 `gh` PR（automatable: full）。
