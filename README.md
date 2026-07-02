# 吆喝 yaohe

一条命令帮开源项目零成本自动宣发的 skill。它知道有哪些渠道，也知道每个渠道怎么投。

![yaohe](docs/assets/banner.png)

写完项目没人知道，卡住你的往往不是投递本身，是两件事：一是宣传渠道有很多（阮一峰周刊自荐、HelloGitHub、Show HN、V2EX、少数派、dev.to…），你根本不知道有哪些；二是就算知道了，每个渠道怎么投、要什么格式、什么会被拒，规则各不相同，得自己一个个踩坑摸清。

吆喝把这两件事都替你做了：收集了 20 个中英文渠道，并把每个渠道的投递规则实证调研成规格文件。剩下的就是一条命令，发新版本时顺手全网吆喝一嗓子：

```
/promote <repo 路径或 owner/repo>
```

它会：

1. **读你的 repo**，提炼项目定位和亮点
2. **挑渠道**：从 20 个渠道里按项目语言、类型、门槛匹配出该投哪些
3. **按每个渠道的规则定制文案** —— 阮一峰自荐格式、HelloGitHub 字数限制、Show HN 标题惯例，各写各的，不是一稿群发
4. **按渠道类型投递**：
   - issue/PR 型渠道（阮一峰周刊等）→ `gh` CLI 确认后直接提交
   - 表单型（HelloGitHub、Product Hunt 等）→ 填好稿件 + 逐字段指引，或浏览器辅助填写
   - 社区发帖型（Show HN、V2EX、Reddit）→ 只出稿不代发，附最佳发帖时间和社区红线
5. **记录投递日志**（`PROMO-LOG.md`），防止重复骚扰渠道

## 为什么"合规"是核心设计

社区发帖型渠道反感机器发帖：HN 封 voting ring 连坐域名，Reddit 有 self-promotion 比例规则。所以吆喝的边界是：**自动化提交只用于渠道方明确开放的自荐入口（issue/PR/表单），社区帖永远人工发**。这不是功能缺失，是产品原则。

## 安装

```
claude plugin marketplace add nmhjklnm/yaohe
claude plugin install yaohe
```

## 已收集的 20 个渠道

这是这个项目的核心资产。每个渠道一个 [规格文件](skills/promote/channels/)，实证调研过它的提交方式、格式要求、门槛、真实命中样例和会被拒的红线。

**中文**：阮一峰科技爱好者周刊、GitHubDaily、HelloGitHub、开源中国 OSCHINA、Gitee GVP、V2EX 分享创造、少数派 Matrix、小众软件、电鸭、即刻

**英文**：Show HN、awesome-claude-code、dev.to、Reddit、Lobsters、Indie Hackers、Product Hunt、Uneed/Microlaunch/Fazier 等 Launch 平台、awesome-list 收录、开发者 Newsletter

不知道这些渠道存在、或不知道每个怎么投，正是吆喝要解决的信息差。欢迎 PR 补充新渠道（按 [channels/_template.md](skills/promote/channels/_template.md)）。

## License

MIT
