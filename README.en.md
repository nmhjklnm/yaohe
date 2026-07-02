# Yaohe (吆喝)

[中文](README.md) | English

A Claude Code skill that lets your agent promote your open-source project across the internet.

![yaohe](docs/assets/banner.png)

You wrote something and nobody knows it exists. There are plenty of channels to submit to (Hacker News, dev.to, awesome lists, newsletters...), but each one has its own format and rules, and submitting to all of them by hand is tedious. Yaohe ships with field-verified specs for 20 channels and turns the whole thing into one command you can run every time you cut a release:

```
/promote <repo path or owner/repo>
```

It will:

1. **Read your repo** and extract the positioning and highlights
2. **Write channel-specific copy** — ruanyf/weekly's self-recommendation format, HelloGitHub's standard, Show HN's title conventions, each one written on its own terms, not one draft blasted everywhere
3. **Submit at three levels of automation**:
   - issue/PR-based channels (ruanyf/weekly, etc.) → submitted via `gh` CLI after your confirmation
   - form-based channels (Product Hunt, etc.) → drafted copy + field-by-field instructions
   - community-post channels (Show HN, Reddit, V2EX) → drafts only, never auto-posts; includes best time to post and community rules to respect
4. **Logs every submission** (`PROMO-LOG.md`) to avoid spamming the same channel twice

## Why "rule-abiding" is the core design

Community channels punish bot-posted content. HN bans voting rings and can nuke your whole domain for it. Reddit has explicit self-promotion ratio rules. So yaohe draws a hard line: **automated submission only happens where the channel explicitly opens a self-serve door (issue, PR, or form). Community posts are always drafted, never auto-posted by the agent.** This isn't a missing feature — it's a product decision.

## Install

```
claude plugin marketplace add nmhjklnm/yaohe
claude plugin install yaohe
```

## Channel coverage

See [skills/promote/channels/](skills/promote/channels/). Each channel gets its own file with a verified submission method, format spec, and real examples. PRs adding new channels are welcome (follow [channels/_template.md](skills/promote/channels/_template.md)).

## License

MIT
