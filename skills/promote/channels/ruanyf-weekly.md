---
id: ruanyf-weekly
name: 阮一峰科技爱好者周刊（自荐）
lang: cn
automatable: full
submission_method: github-issue
target: https://github.com/ruanyf/weekly/issues/new
audience: 中文开发者/科技爱好者，周刊读者量大，上刊即显著曝光
threshold: none（但纯营销/无代码的商业站几乎必被无声淘汰，见 rules）
verified: 2026-07-02
---

# 阮一峰周刊自荐

提交方式 = **开新 issue**（不是评论到固定 issue）。无 issue template，自由格式。注意：置顶的《谁在招人》issue 是招聘专用，与项目自荐无关。

## format_spec

**标题**：`【开源自荐】项目名：一句话卖点（品类）`。类型词可用 开源自荐/工具自荐/网站自荐；括号符号不强求统一。

**正文结构**（高命中样本共性）：

1. 开头 1-2 句说清"这是什么 + 解决什么具体痛点"，直给项目地址（GitHub repo 优先）
2. 一张截图或 GIF demo（**强烈建议**，可视化越直观命中率越高）
3. 核心特性 bullet 3-8 条（允许 emoji 前缀）
4. 安装命令代码块（brew/npm/cargo 一键安装是加分项）
5. 技术栈一行 + 开源协议（MIT 等，明示协议是加分项）

长度弹性大：简单项目 3-5 句纯文字也能中；复杂项目可带 `## 简介/## 核心特性/## 安装` 完整章节。篇幅要配得上项目复杂度。

**语气**：平实客观陈述功能。禁"先进的/一站式/高颜值"式自我推销词。

真实命中样例（第 401 期收录，issue #10233 标题）：

> 【开源自荐】smctl：给 Apple Silicon Mac 补上官方没有的风扇控制和电池限充（命令行工具）

正文开头范式：

> smctl 是一个开源（MIT）命令行工具，给 Apple Silicon Mac 提供风扇曲线控制和电池充电限制——这两件事 macOS 官方都不开放……

## rules

- 高命中特征：真实开源 repo + 明确协议 + 解决**具体**技术痛点（尤其"官方没做/官方限制"类刚需）+ 命令行/TUI/效率工具/自托管品类 + 有 demo 图
- 几乎必被淘汰：AI 生成器/检测器套壳站、纯营销话术商业 SaaS、玩具级一次性小站、内容聚合日报站
- 处理流程是**静默 close**：close ≠ 采用。判断是否真上刊，查最近几期 `docs/issue-XXX.md` 是否引用了你的 issue 号（格式「[@用户名](issue链接) 投稿」）
- 无发现频率限制，但同一项目重复投是浪费

## submit

```bash
gh issue create -R ruanyf/weekly \
  --title "【开源自荐】<项目名>：<一句话卖点>（<品类>）" \
  --body-file promo-drafts/ruanyf-weekly.md
```

提交后 7-14 天检查是否上刊：

```bash
gh api -X GET search/issues -f q='repo:ruanyf/weekly <项目名> in:title' --jq '.items[] | {number, state}'
# 再在最近 2-3 期 docs/issue-*.md 里搜项目名确认
```
