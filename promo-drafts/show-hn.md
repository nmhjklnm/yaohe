# Show HN submission

**Title** (must start with "Show HN", en-dash separator):

Show HN: oss-promote – a Claude Code plugin that submits your OSS repo to promo channels per their own rules

**URL**: https://github.com/nmhjklnm/oss-promote

**First comment** (post immediately after submitting, in the top-level comment):

I built this after spending an evening reformatting the same project pitch five different ways for five different places (Ruanyf's weekly, GitHubDaily, HelloGitHub, Show HN, V2EX) — each one wants a different title style, length, and tone, and getting it wrong reads as spam.

oss-promote is a Claude Code plugin: point it at a repo, it profiles the project (positioning, audience, differentiators) and drafts a channel-specific writeup for each place you pick, following each channel's actual submission rules — not a generic press release copy-pasted everywhere.

It also splits channels by how automatable submission is:
- issue/PR channels (like Ruanyf's weekly) — confirm once, it submits via `gh`
- form-based channels (like HelloGitHub) — it gives you the exact fields to paste in
- community-post channels (Show HN itself, V2EX, Reddit) — it only drafts the copy; you post it yourself. No auto-posting to forums, ever — that's how projects get banned for vote/comment rings.

It logs every submission to a PROMO-LOG.md in the target repo so you don't accidentally spam the same channel twice.

Stack: it's just a Claude Code skill + a folder of per-channel rule files (markdown with frontmatter), MIT licensed. Feedback on the channel rule files especially welcome — each one is supposed to be field-verified, and I'd rather find out now if I got a rule wrong than after someone's submission gets silently rejected.
