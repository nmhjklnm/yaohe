Title: 【开源自荐】吆喝（yaohe）：把开源项目宣传变成一条命令，按各渠道规则合规投递（一个 agent skill）

吆喝是一个开源（MIT）的 skill，把「写完开源项目投哪儿、怎么投」这件事变成一条 `/promote` 命令，给你的项目吆喝一嗓子。

项目地址：https://github.com/nmhjklnm/yaohe

![yaohe](https://raw.githubusercontent.com/nmhjklnm/yaohe/main/docs/assets/banner.png)

宣传渠道很多：阮一峰周刊自荐、HelloGitHub、GitHubDaily、Show HN、V2EX……每个渠道格式、规则各不相同，手动投一圈很花时间，还容易因为格式不对被无声淘汰或被判 spam。吆喝的做法：

- 读你的仓库，提炼项目定位、目标人群和亮点
- 每个渠道单独定制文案：内置 20 个渠道的实证规格，提交方式、格式要求、真实命中样例、社区红线都逐渠道核实过
- 分三级自动化：issue/PR 型渠道确认后用 `gh` 直接提交；表单型给稿件和逐字段指引；社区发帖型（HN、V2EX、Reddit）只出稿不代发，机器代发社区帖等于 spam
- 投递日志写入 `PROMO-LOG.md`，同渠道 30 天内不重复投

渠道规格是独立的 markdown 文件，欢迎 PR 添加新渠道。

安装：

```
claude plugin marketplace add nmhjklnm/yaohe
claude plugin install yaohe
```

开源协议：MIT
