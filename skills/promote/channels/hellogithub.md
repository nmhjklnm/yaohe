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

1. 生成三字段稿件（严格卡字符数）写入 `promo-drafts/hellogithub.md`，首行 `Title:` 存标题
2. 登录：点「提交项目」唤起弹窗，两个 OAuth 选项（微信扫码 / GitHub 授权），**登录归用户**；首次授权即注册
3. 浏览器辅助填写（`references/browser-assist.md`）时，表单三字段的确切 placeholder（实证 2026-07-03）：
   - `项目地址`
   - `标题：请用一句话介绍项目`
   - `描述：请从它是什么、解决了什么痛点等方面介绍项目…`
   - **按 placeholder 前缀精确匹配填入**（`startswith`），别用「介绍」等子串匹配——「标题」框 placeholder 也含「介绍项目」，子串匹配会把描述灌进标题框
4. **提交按钮由用户确认后自己点**；提交成功=弹窗关闭回到主页，去「审核进度」看状态
5. 硬编码填表脚本时，字段值必须与本文件稿件保持同源，改文案要一起改脚本常量（踩过：稿件改了脚本没改，投出旧文案）
