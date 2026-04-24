---
仓库: JimLiu/baoyu-skills
URL: https://github.com/JimLiu/baoyu-skills
本地路径: .claude/sources/baoyu-skills/
上次调研: 2026-04-24
激活状态: 0 / 21（按需激活池）
调研结论: 全留 sources，不立即激活；按"做什么事就装什么 skill"的节奏触发
---

# 宝玉仓库（JimLiu/baoyu-skills）调研

## 定位

21 个 skill 的**工程化大仓库**，图文生成 + 内容转换 + 多平台发布的**流水线工具集合**。

**和 khazix 本质不同**：khazix 是写作流程增强（单一职责的写作方法论），宝玉是图文生产与发布的工程系统。

## 技术依赖

- Node.js + Bun（`npx -y bun` 可跑）
- Chrome（CDP 模式，用于发布类 skill 和 web scraping）
- 多家图像生成 API keys（按需配）：OpenAI / Azure / Google / OpenRouter / DashScope（通义）/ Z.AI / MiniMax / 即梦（火山）/ 豆包（Seedream）/ Replicate
- 部分发布类 skill 需要平台账号（公众号 AppID / 微博登录态 / X cookies）

## 21 个 skill 完整清单（按功能分四组）

### A 组 · 小红书 / 图文生成（用户多平台矩阵核心刚需）

| skill | 干嘛 | 依赖 | 匹配度 |
|---|---|---|---|
| baoyu-xhs-images | 小红书图片卡片（12 种风格 × 6 种布局） | 图像 API | 🔥🔥🔥 |
| baoyu-image-cards | 图片卡片（xhs-images 的升级版，已 supersede） | 图像 API | 🔥🔥🔥 |
| baoyu-cover-image | 文章封面图（11 配色 × 7 渲染 = 77 种） | 图像 API | 🔥🔥🔥 |
| baoyu-infographic | 信息图（20 布局 × 17 风格） | 图像 API | 🔥🔥 |
| baoyu-article-illustrator | 文章插图（6 类型 × 8 风格） | 图像 API | 🔥🔥 |
| baoyu-comic | 知识漫画（5 画风 × 7 基调 + 预设） | 图像 API | 🔥 |
| baoyu-slide-deck | 幻灯片生成（16 预设 + 自动 pptx/pdf） | 图像 API | 🔥 |
| baoyu-diagram | SVG 流程图 / 架构图（Claude 手算坐标，**不调 API**） | **无** | 🔥 |

### B 组 · 多平台发布

| skill | 干嘛 | 依赖 | 匹配度 |
|---|---|---|---|
| baoyu-post-to-wechat | 发公众号（API 或 Chrome，支持多账号） | 公众号 AppID 或 Chrome 登录 | 🔥🔥 Month 3+ |
| baoyu-post-to-weibo | 发微博（文字 + 图 + 视频 + 头条长文） | Chrome 登录 | 🔥 未来 |
| baoyu-post-to-x | 发 X（推文 + 长文章） | Chrome 登录 | 🔥 未来 |

### C 组 · 通用工具（轻量、无 / 低成本）

| skill | 干嘛 | 依赖 | 匹配度 |
|---|---|---|---|
| baoyu-format-markdown | 格式化 md（加 frontmatter / 标题 / 排版 / 中英文空格） | 无 | 🔥 高频 |
| baoyu-markdown-to-html | md 转 HTML（支持公众号主题） | 无 | 🔥 Month 3+ |
| baoyu-url-to-markdown | 网页抓取转 md（Chrome CDP，比 defuddle 强） | Chrome | 🔥 和现有 defuddle 重叠，可择一 |
| baoyu-youtube-transcript | YouTube 字幕下载 + 章节 + 说话人识别 | 无 | 🔥 做视频素材必备 |
| baoyu-translate | 三模式翻译（快速 / 标准 / 精翻） | LLM API（Claude 本身能干） | 🔥 重叠度高，价值低 |
| baoyu-compress-image | 图片压缩 | 无 | 🔥 日常用 |

### D 组 · AI 后端 + 高风险（通常被其他 skill 调用或不推荐）

| skill | 干嘛 | 说明 |
|---|---|---|
| baoyu-imagine | 图像生成后端（9 家 API 适配） | A 组 skill 的底层，装 A 组时会一起跑起来 |
| baoyu-image-gen | 旧版 imagine，已 deprecated | 跳过 |
| baoyu-danger-gemini-web | 逆向 Gemini Web（非官方 API） | **跳过**（ToS 风险，账号可能被限） |
| baoyu-danger-x-to-markdown | 逆向 X 抓取（非官方 API） | **跳过**（同上风险） |

## 激活策略（分三节奏）

### 第一节奏 · 现在（4/24 前后）

**不激活任何 skill**。整个仓库留 `.claude/sources/baoyu-skills/` 作"按需激活池"。

理由：
- 今天 4/24 硬约束是发豆老师第一条小红书（文字内容），图文 skill 不在关键路径
- 图像类 skill 要先决定用哪家 API、充多少钱
- 21 个 skill 一次激活 Claude Code 技能列表会爆

### 第二节奏 · 豆老师发 3-5 条后（要开始做图文卡片 / 封面时）

- 挑一家图像生成 API（**推荐国内稳定便宜的三家之一**：豆包 Seedream / 即梦 Jimeng / 通义 DashScope）
- 激活 `baoyu-image-cards` + `baoyu-cover-image`
- 配 `.env` 里 API key（`~/.baoyu-skills/.env`）
- 复制到 `.claude/skills/` 并同步资产索引

### 第三节奏 · Month 3+ 开公众号 / 接入微博时

- 激活对应的 post-to-X
- 配置浏览器登录态 / API 凭证

## 最小激活建议（如果今天坚持要装一点）

按"零依赖 + 通用高频"原则，最多装三个：

| 优先 | skill | 理由 |
|---|---|---|
| 推荐 | baoyu-diagram | 不需要 API，Claude 手算 SVG，架构图 / 流程图立刻能用 |
| 可装 | baoyu-format-markdown | 无依赖，格式化草稿刚需 |
| 可装 | baoyu-youtube-transcript | 未来做视频素材必备，无依赖 |
| 犹豫 | baoyu-url-to-markdown | 和已装的 defuddle 重叠；装了考虑卸 defuddle |
| **不装** | baoyu-translate | 功能被 Claude 本身覆盖 |
| **不装** | A 组图像类 | 等决定 API 家再一次批量装 |
| **不装** | B 组发布类 | 等对应平台真正启动时再装 |

## 作者推荐的另一种安装方式（未采用）

作者推荐通过 Claude Code 的 plugin marketplace 机制整体安装：

```bash
/plugin marketplace add JimLiu/baoyu-skills
/plugin install baoyu-skills@baoyu-skills
```

**为什么没采用**：一次注册会把 21 个 skill 都暴露给 Claude Code 的技能列表，触发描述会相互干扰，且对应配套依赖（API / Chrome 登录）未就绪时 skill 会半废。更符合"按需激活"原则的做法是手动挑需要的复制到 `.claude/skills/`。

未来如果打算大规模启用（比如 Month 3+ 同时做多平台），可以重新评估 plugin marketplace 方式。

## 更新仓库

```bash
git -C /Users/admin/mybrain/.claude/sources/baoyu-skills pull
```

拉完后对照 CHANGELOG.md 看是否新增 skill；新 skill 回到本文档补一行。
