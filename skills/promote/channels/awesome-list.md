---
id: awesome-list
name: Awesome List 收录（PR 到相关 awesome-* 仓库）
lang: en
automatable: full
submission_method: github-pr
target: 动态发现：`gh api -X GET search/repositories -f q='awesome <领域关键词> in:name' --jq '.items[:5][] | {full_name, stargazers_count}'`
audience: 长尾持续流量（awesome list 是开发者选型入口，SEO 价值高）
threshold: 项目需真实可用、维护中；各列表另有自己的 contributing 规则
verified: 2026-07-02
---

# Awesome List 收录

注意区分两件事：**向某个领域 awesome-\* 列表添加你的项目**（本渠道的主用途，门槛低）vs **向 sindresorhus/awesome 主仓提交一个新列表**（门槛高：列表满 30 天、CC0、awesome-lint、先评审 4 个他人 PR 等，一般用不到）。

## format_spec（条目 PR）

- 先读目标列表的 `contributing.md`（有就必须遵守）
- 条目格式（awesome 生态通例）：`[Name](url) - Description.`——描述首字母大写、句号结尾、描述项目本身、禁营销话术
- 插入位置遵守列表的现有排序（字母序/分类）
- PR 标题：`Add <Name>`；PR 描述说明项目为什么属于这个列表
- **红线：禁止全 AI 生成的 PR**（sindresorhus 生态明文拒绝）——稿件须经用户过目确认后再提

## submit

```bash
# 1. 找目标列表（按项目领域关键词），人工确认相关性
# 2. fork + 单行改动 + PR
gh repo fork <owner>/<awesome-repo> --clone
# 编辑对应分类下插入条目
gh pr create -R <owner>/<awesome-repo> --title "Add <Name>" --body-file promo-drafts/awesome-list.md
```

一次只投最相关的 1-2 个列表，广撒网式 PR 会被生态圈拉黑。
