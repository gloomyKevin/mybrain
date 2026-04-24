---
仓库: JimLiu/baoyu-skills
URL: https://github.com/JimLiu/baoyu-skills
本地路径: .claude/sources/baoyu-skills/
上次调研: 2026-04-24
激活状态: 0 / 21
---

# 宝玉仓库（JimLiu/baoyu-skills）调研

## 定位

21 个 skill 的**工程化大仓库**，图文生成 + 内容转换 + 多平台发布的**流水线工具集合**。和 khazix（写作流程增强）本质不同。

## 技术依赖

- Node.js + Bun（`npx -y bun` 可跑）
- Chrome（CDP 模式，发布类 skill 和 web scraping 用）
- 多家图像生成 API keys（按需配）：OpenAI / Azure / Google / OpenRouter / DashScope（通义）/ Z.AI / MiniMax / 即梦（火山）/ 豆包（Seedream）/ Replicate
- 发布类 skill 需要平台账号：公众号 AppID / 微博登录态 / X cookies

## 21 个 skill 清单

### A 组 · 小红书 / 图文生成

| skill | 干嘛 | 依赖 | 匹配度 |
|---|---|---|---|
| baoyu-xhs-images | 小红书图片卡片（12 风格 × 6 布局） | 图像 API | 🔥🔥🔥 |
| baoyu-image-cards | 图片卡片（xhs-images 的升级版） | 图像 API | 🔥🔥🔥 |
| baoyu-cover-image | 文章封面图（11 配色 × 7 渲染 = 77 种） | 图像 API | 🔥🔥🔥 |
| baoyu-infographic | 信息图（20 布局 × 17 风格） | 图像 API | 🔥🔥 |
| baoyu-article-illustrator | 文章插图（6 类型 × 8 风格） | 图像 API | 🔥🔥 |
| baoyu-comic | 知识漫画（5 画风 × 7 基调 + 预设） | 图像 API | 🔥 |
| baoyu-slide-deck | 幻灯片生成（16 预设 + 自动 pptx/pdf） | 图像 API | 🔥 |
| baoyu-diagram | SVG 流程图 / 架构图（Claude 手算坐标） | **无** | 🔥 |

### B 组 · 多平台发布

| skill | 干嘛 | 依赖 | 匹配度 |
|---|---|---|---|
| baoyu-post-to-wechat | 发公众号（API 或 Chrome，支持多账号） | 公众号 AppID 或 Chrome 登录 | 🔥🔥 |
| baoyu-post-to-weibo | 发微博（文字 + 图 + 视频 + 头条长文） | Chrome 登录 | 🔥 |
| baoyu-post-to-x | 发 X（推文 + 长文章） | Chrome 登录 | 🔥 |

### C 组 · 通用工具

| skill | 干嘛 | 依赖 |
|---|---|---|
| baoyu-format-markdown | 格式化 md（加 frontmatter / 标题 / 排版 / 中英文空格） | 无 |
| baoyu-markdown-to-html | md 转 HTML（支持公众号主题） | 无 |
| baoyu-url-to-markdown | 网页抓取转 md（Chrome CDP） | Chrome |
| baoyu-youtube-transcript | YouTube 字幕下载 + 章节 + 说话人识别 | 无 |
| baoyu-translate | 三模式翻译（快速 / 标准 / 精翻） | LLM API |
| baoyu-compress-image | 图片压缩 | 无 |

### D 组 · AI 后端 / 高风险

| skill | 说明 |
|---|---|
| baoyu-imagine | 图像生成后端（9 家 API 适配）。A 组 skill 的底层调用方 |
| baoyu-image-gen | 作者标为 deprecated，被 baoyu-imagine 取代 |
| baoyu-danger-gemini-web | 非官方 API（逆向 Gemini Web）。ToS 风险，账号可能被限 |
| baoyu-danger-x-to-markdown | 非官方 API（逆向 X 抓取）。同上风险 |

## 功能重叠 / 冲突点（与已有资产对比）

- `baoyu-url-to-markdown` 与已激活的 `defuddle` 功能重叠（网页转 md）
- `baoyu-translate` 与 Claude 本身能力重叠（Claude 原生可翻译）

## 作者推荐的两种安装方式

**方式 1 · plugin marketplace（整仓激活）**：
```bash
/plugin marketplace add JimLiu/baoyu-skills
/plugin install baoyu-skills@baoyu-skills
```
一次注册 21 个 skill 全进技能列表。

**方式 2 · ClawHub 单装**：
```bash
clawhub install baoyu-<name>
```

**方式 3 · 手动复制**（本 vault 其他 skill 也用这个方式）：  
从 `.claude/sources/baoyu-skills/skills/<name>/` 复制到 `.claude/skills/<name>/`，按需配 `.env`。

## 更新仓库

```bash
git -C /Users/admin/mybrain/.claude/sources/baoyu-skills pull
```

拉完后对照 CHANGELOG.md 看是否新增 skill；新 skill 回到本文档补一行。
