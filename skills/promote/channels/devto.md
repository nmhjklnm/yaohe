---
id: devto
name: dev.to
lang: en
automatable: full
submission_method: post-article
target: Forem API v1 `POST https://dev.to/api/articles`（文档 https://developers.forem.com/api）
audience: 大型开发者博客社区，开源 showcase 是常见形式
threshold: 需用户在 dev.to 设置页生成 api-key
verified: 2026-07-02
---

# dev.to 发文

唯一有公开可编程发布 API 的社区渠道。

## format_spec

- 文章形态：showcase 长文（做了什么/为什么/怎么用/求反馈），markdown 正文
- tags：逗号分隔，建议 opensource + 领域 tag（如 claudecode/ai/productivity）

## rules

无官方 self-promo 书面限制，依赖社区礼仪：讲干货不发纯广告。

## submit

```bash
curl -s -X POST https://dev.to/api/articles \
  -H "api-key: $DEVTO_API_KEY" -H "content-type: application/json" \
  -H "accept: application/vnd.forem.api-v1+json" \
  -d '{"article":{"title":"...","body_markdown":"...","published":false,"tags":["opensource"]}}'
```

先 `published: false` 存草稿给用户预览，用户确认后再置 true 发布。
