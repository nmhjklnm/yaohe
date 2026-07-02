---
id: githubdaily
name: GitHubDaily（自荐）
lang: cn
automatable: full
submission_method: github-issue
target: https://github.com/GitHubDaily/GitHubDaily/issues/new
audience: 公众号/微博/知乎/X 多平台分发的开发者流量
threshold: none
verified: 2026-07-02
---

# GitHubDaily 自荐

README 原话："欢迎到本仓库的 issues 推荐或自荐项目"。无 issue 模板，人工从 issue 筛选后分发到公众号/微博/知乎/X，无固定审核周期。

## format_spec

- 标题 = 项目名
- 正文 = GitHub 链接 + 一句话简述（核心功能点 + 适用场景），风格参照其年度复盘表格条目：`项目名 | 一句话简述`
- 简洁为王，不需要长文

## rules

无 star / 字数门槛明文规定。被选中无通知，靠人工筛选。

## submit

```bash
gh issue create -R GitHubDaily/GitHubDaily \
  --title "<项目名>" \
  --body-file promo-drafts/githubdaily.md
```
