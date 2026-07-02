---
name: promote
description: Promote an open-source project across CN & EN channels — reads the repo, generates per-channel tailored copy, auto-submits issue/PR-type channels via gh, assists the rest. Use when the user wants to 宣传/推广/publicize/launch/submit their open-source project, or asks "帮我把这个项目投到阮一峰周刊/HelloGitHub/Show HN".
---

# promote — 开源项目一键合规宣传

核心原则：**一键 ≠ 一键全发**。渠道分三级自动化，越权发帖 = spam = 毁项目声誉。

## 流程

### 1. 项目画像（必做，一切文案的源头）

**硬性前置闸门，任一不过就停下问用户，不进入后续步骤：**

- `gh repo view <owner>/<repo>` 必须成功（仓库公开可达）。本地路径则检查 `git remote -v` 有 GitHub remote 且已 push——**稿件里的每个链接都必须真实可达，绝不写入死链**
- LICENSE 文件真实存在才可声明协议；README 说 MIT 但没有 LICENSE 文件 → 提醒用户先补

然后读 README 全文、描述、topics、star 数、最近活跃度，提炼：一句话定位（它是什么+替代/优于什么）、目标人群、3 个差异化亮点、演示素材（截图/GIF/demo URL）。

README 薄的判定（缺任一项即问用户补齐，不要编）：① 一句话说清它是什么 ② 安装/使用方法 ③ 至少一个具体使用场景或示例。

### 2. 渠道选择

读 `channels/` 下所有渠道文件的 frontmatter，按项目画像过滤：

- 语言匹配：投 EN 渠道的条件 = 有英文 README（或 README 本身是英文）；不满足时该渠道仍可列出但标注「需先补英文文档」，用户坚持投则明示风险后照办
- 门槛匹配（如渠道要求 star 数 / 入门级 / dev-tool 类目）
- 检查 `PROMO-LOG.md`（项目根目录）：**同一渠道 30 天内有任何记录（含 rejected）即跳过**，冷却期从最新一条记录的日期起算

用 AskUserQuestion 列出推荐渠道（含自动化等级标注）让用户勾选；用户明确说"全投"则投所有合规匹配渠道。

### 3. 逐渠道生成定制稿

对每个选中渠道，读其 `channels/<id>.md` 全文，**严格按其 format_spec 生成**：

- 禁止一稿多投：每渠道的标题风格、篇幅、语气、结构都不同（阮一峰自荐 ≠ Show HN 标题 ≠ V2EX 分享创造帖）
- 文案原则：说人话、给事实（能做什么、和现有方案差在哪），禁营销腔/AI 味（震惊体、emoji 堆砌、buzzword）
- 全部稿件先写入 `promo-drafts/<channel-id>.md` 落盘；**文件首行固定为 `Title: <标题>`**（即使该渠道标题走 `gh --title` 参数不进 body），复盘时才对得上号

### 4. 分级执行

按渠道 frontmatter 的 `automatable` 字段：

- **full**（issue/PR 型）：先 `gh auth status` 确认已登录（未登录 → 让用户 `gh auth login`，停在这里）→ 展示最终稿 → 用户确认一次 → `gh` CLI 提交 → 记录返回 URL。失败就报错停，不换渠道兜底。
- **assisted**（网页表单型）：给出最终稿 + 提交 URL + 逐字段填写指引；有浏览器工具可代填但提交按钮由用户点。
- **manual-only**（社区发帖型）:只交稿件 + 建议发帖时间（见渠道文件）+ 红线提醒。**任何情况下不代发**。

### 5. 记录与复盘

把本次投递写入目标项目根目录 `PROMO-LOG.md`，固定表格 schema（机器可读，下次运行先读它）：

```markdown
| channel | date | draft | url | status |
|---|---|---|---|---|
| ruanyf-weekly | 2026-07-02 | promo-drafts/ruanyf-weekly.md | https://github.com/ruanyf/weekly/issues/NNN | submitted |
```

- `date` 用 ISO（YYYY-MM-DD）；`status` ∈ draft / submitted / published / rejected
- 30 天冷却按该渠道最新一行的 date 计算，任何 status 都算

## 红线（任何渠道通用）

- 不伪造用户身份发言；不注册马甲；不安排互赞互顶（HN voting ring 会连坐封域名）
- 同一渠道 30 天内不重复投同一项目
- 渠道规则与本 skill 冲突时，以渠道最新规则为准（提交前 spot-check 渠道规则页是否变化）
