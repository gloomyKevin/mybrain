# Skill 风格模型横向对比 · 2026-04-26

## 这次想搞清楚什么

同一份 khazix-writer SKILL + 同一段语音原话素材，在不同模型上写出来差距有多大。最初是补一版 Claude 加进已有的 DeepSeek flash/pro 对比，中间结构改了好几次，最后落到 3 个模型横向比：Claude Opus 4.7、DeepSeek v4 Pro、DeepSeek v4 Flash。

（Sonnet/Haiku 中途加进来又被砍，因为用户后来明确只关心这 3 个；它们的中间产物也都在这个目录里。）

## 实验最终形态

- prompt：`2026-04-26-prompt-skill-task-clean-unbound.md`（从 clean 版去掉「小红书短图文，长度合理把握」这一句，让模型走 SKILL 默认的公众号长文场景）
- SKILL：`khazix-writer`（项目 .claude/skills/ 下，本身为公众号长文 4000-8000 字设计）
- harness：全部走 top-level `claude --print` 子进程，用 stdout 捕获（避开 Claude Code 对 .claude/ 路径的 Write 保护）
- DeepSeek 接入：`~/.claude/settings.deepseek.json` + `--model {opus|haiku}` 别名（opus → v4-pro，haiku → v4-flash）

3 篇最终成稿：
- `2026-04-26-final-claude-opus47-raw.md`（3931 字符）
- `2026-04-26-final-deepseek-v4pro-raw.md`（2920 字符）
- `2026-04-26-final-deepseek-v4flash-raw.md`（2473 字符）

## 观察（全部 sample = 1，场景固定为公众号长文 + Claude Code harness）

**风格还原**：
- Opus 4.7 最完整。L1 禁令零违规，SKILL 武器（契诃夫之枪、文化升维、谦逊铺垫等）都用上，自加金句质量高（例：把 AI 文案描述成「AI 味浓得能腌咸菜」）。
- DeepSeek v4 Pro 风格 80% 像。中文反而比 Opus 松弛，有「怎么个砸法呢」这种带语气词的口腔感。SKILL 复杂规则服从弱一档，2 个冒号留在了 SKILL 自带狗尾里没拦。
- DeepSeek v4 Flash 把任务做成了段落式压缩。SKILL 的节奏断裂、独立成段、口语化转场词几乎没用上。**这个观察绑定在「公众号长文 + 复杂 SKILL」场景下，不能直接外推到短图文 + 简化风格模板。**

**工具调用可靠性**：
- Opus subagent 版第一轮被 .claude/ sensitive-path 拦住 Write，这是 Anthropic 安全护栏在主动保护。
- DeepSeek pro 第一轮直接写盘成功——同样的 .claude/ 路径它没拦。**Anthropic 安全护栏不传递到 DeepSeek 后端**。
- DeepSeek flash 第一轮自报「Done. 文件已保存」，但磁盘上没文件——**工具调用幻觉**。改用 stdout 捕获方案才拿到稿，这本身就是个数据点。

**Harness 影响输出长度**：
Opus 4.7 在三种 harness 下长度差异明显：in-context 主会话（带这一整段对话上下文）4328 字符、subagent 2601、top-level print 3931。harness 差异（系统提示长度、上下文背景）对生成长度有可观察影响，这不是模型差异，是包装差异。

## 我的理解

不下「模型分工」的结论。但有几条值得作为下次实验的对照基线：

- 单 sample + 单任务的对比只能立「现象观察」，不能立「模型能力地图」。下次跑 3-5 次取均值才有底。
- DeepSeek 的中文松弛感是实存的，但它和 SKILL 服从度是 trade-off——给它越自由它越像真人，给它越严格反而越容易破规则。这条 trade-off 怎么用，看具体任务对哪一头容忍度更高。
- DeepSeek 后端跑 Claude Code 单次子任务可行（已通），但长期接入主 backend 需要重新评估安全模型——sensitive-path 保护、permission 边界、tool authorization 这些 Anthropic 内置护栏都不一定传递。子进程隔离是当前最稳折中。
- 这次实验跑的不是 `.claude/管线编排.md` 节点 5 设计的场景（短图文 + stdin/stdout 直调 DeepSeek）。**「DeepSeek V4 Flash 写血肉」的假设没有被这次实验证伪，要测它需要换场景重跑**。
- Codex / GPT-5.5 没测，占位等下一次。

## 为什么作废

不是因为结论错。是因为：
- 结论强度不够立成正式参考（sample = 1）
- 单任务 + 单场景覆盖太窄，主稿 vs 短图文 vs 翻译 vs 粗整理 vs 工具链路这些都没分别测
- 摸索期写硬规则会过早固化

留作下一轮实验的起点和对照，不进主笔记浏览。

## 文件清单

- prompt 几个变体：`2026-04-26-prompt*.md`（v1 → v2-clean → truly-clean → unbound）
- DeepSeek 早期手跑：`2026-04-26-deepseek-v1*.md`、`2026-04-26-deepseek-skill-flash-v1/v2-clean*.md`、`2026-04-26-deepseek-skill-pro-v2-clean/v3-truly-clean*.md`
- Claude 中间版本：`2026-04-26-claude-skill-{v2-clean,clean-unbound,opus,sonnet,haiku}-*.md`
- 最终 3 篇横向比：`2026-04-26-final-*.md`
