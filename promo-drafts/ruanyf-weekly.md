oss-promote 是一个开源（MIT）Claude Code 插件，把"写完开源项目投哪儿、怎么投"这件事变成一条命令——https://github.com/nmhjklnm/oss-promote

阮一峰周刊自荐、GitHubDaily、HelloGitHub、Show HN、V2EX……每个渠道格式不同、规则不同，手动投一圈很花时间，还容易因为格式不对被判 spam。这个插件按渠道规则分级处理：能自动提交的（issue/PR 型）确认后用 `gh` 直接发，表单型给字段清单，社区发帖型（HN、V2EX）**只出稿不代发**——避免机器发帖触发社区反感或连坐风险。

## 核心特性

- 读目标 repo 提炼项目定位、亮点、demo 素材，生成项目画像
- 每个渠道单独定制文案，不是一稿多投（阮一峰自荐 ≠ Show HN 标题 ≠ V2EX 分享帖）
- 分三级自动化：full（issue/PR 直接提交）/ assisted（表单给字段清单）/ manual-only（只出稿，人工发）
- 投递记录写入 `PROMO-LOG.md`，同渠道 30 天内不重复投
- 渠道规则文件可读可 PR 扩展，每条规则都标注实证日期

## 安装

```
claude plugin marketplace add nmhjklnm/oss-promote
claude plugin install oss-promote
```

技术栈：Claude Code plugin（Markdown skill + channel 规则文件），协议 MIT。
