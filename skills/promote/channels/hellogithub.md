---
id: hellogithub
name: HelloGitHub（自荐）
lang: cn
automatable: assisted
submission_method: web-form
target: https://hellogithub.com/periodical （页面内「推荐或自荐开源项目」弹窗表单）
audience: 「有趣、入门级开源项目」定位的月刊 + 网站首页收录
threshold: 仅接受 https://github.com 开头的仓库地址；且不能是已收录项目
verified: 2026-07-02
---

# HelloGitHub 自荐

**没有 GitHub issue/PR 通道**（仓库 README 也指向网站表单）。表单是 SPA 前端弹窗，CLI 不可达 → assisted：生成好三个字段的稿件，用户（或浏览器工具）到页面填写提交。

## format_spec

表单三字段（实证抓取的前端校验规则）：

| 字段 | 要求 |
|---|---|
| 项目地址 | 必须 `https://github.com` 开头，未被收录过 |
| 标题 | 一句话介绍项目，**5-50 字符** |
| 描述 | **10-300 字符**，官方提示：从"它是什么、解决了什么痛点"介绍，包括技术、功能、适用场景；"描述通俗易懂、符合要求可以提高通过率" |

## rules

- 每日提交次数有限（前端有"今天还可以提交 N 次"文案，上限疑为 1 次/天，unverified）
- 月刊偏好"有趣、入门级"项目；网站首页收录与月刊是两套机制，表单进的是首页收录库
- 提交后在「审核进度」查看状态，通过审核才会在首页展示

## submit

1. 生成三字段稿件（严格卡字符数）写入 `promo-drafts/hellogithub.md`
2. 引导用户打开 https://hellogithub.com/periodical → 点「推荐或自荐开源项目」→ 逐字段粘贴
3. 有 Chrome 浏览器工具时可代填表单，**提交按钮由用户确认后再点**
