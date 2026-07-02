# 浏览器辅助提交（assisted 渠道的标准流程）

适用：`automatable: assisted` 的渠道（网页表单型），以及用户主动要求「带我去网页操作」时的任何渠道。前提：Claude in Chrome 扩展已连接（`tabs_context_mcp` 能拿到 tab；连不上就回退为「稿件 + 逐字段指引」模式，并提示用户安装 https://claude.ai/chrome ）。

## 流程

1. `tabs_context_mcp` 确认连接 → `tabs_create_mcp` 开新 tab（不复用用户已有 tab）
2. `navigate` 到渠道文件 `target` 指定的提交入口
3. 登录墙：**停下让用户自己登录**（绝不代输密码/验证码），登录完成后继续
4. `find`/`read_page` 定位表单字段 → `form_input` 逐字段填入 `promo-drafts/<channel-id>.md` 里的对应值
5. 截图给用户核对全部字段
6. **提交按钮由用户确认后才点**（用户明说「你点吧」才代点；默认让用户自己点）
7. 提交成功后截图留证，把结果 URL 和状态写入 `PROMO-LOG.md`

## 红线

- 不代输任何凭据、不碰验证码/人机校验
- 渠道方明文禁止自动化的（如 awesome-claude-code「必须真人填表单否则封禁」），本流程只做到第 2 步（带到页面）+ 在聊天里给字段值，填写由用户完成
- 一次会话只处理用户点名的渠道，不顺手多投
