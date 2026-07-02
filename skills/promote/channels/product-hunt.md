---
id: product-hunt
name: Product Hunt
lang: en
automatable: assisted
submission_method: web-form
target: https://www.producthunt.com/launch
audience: 早期采用者/SaaS 用户；dev tools 也有专区
threshold: none，但需要完整素材包（图/tagline/描述）
verified: 2026-07-02（素材规格为搜索汇总，发布前用官方 preparing-for-launch 页二次确认）
---

# Product Hunt

GraphQL API v2 存在（api.producthunt.com/v2/docs）但**默认只读且不可商用**，创建 launch 的写权限需邮件申请——所以走 assisted：生成全套素材，用户网页提交。

## format_spec（素材包清单）

| 素材 | 规格 |
|---|---|
| Tagline | ≤60 字符，简短不夸张 |
| Description | ≤500 字符 |
| Thumbnail | 正方形 240x240 |
| Gallery | ≥2 张，建议 1270x760，单文件 <3MB（GIF 可） |
| First comment | maker 自述：动机 + 差异化 + 求反馈 |

## rules

- 红线：未授权不得用 API 批量创建 launch（官方明示 API 默认非商用）
- 拉票同样有反作弊，只做"通知已有用户"级别的宣传

## submit

assisted：素材包全部生成落盘（含图片尺寸检查清单）→ 给出 launch 页 URL + 逐字段填写指引。
