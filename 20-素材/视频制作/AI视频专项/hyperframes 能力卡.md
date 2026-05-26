# hyperframes 能力卡

> HeyGen 开源的 HTML 视频渲染框架。"写 HTML，渲染视频"，专为 AI agent 协作。
> 仓库源码 `~/research/hyperframes/` · skill 全局安装 `~/.agents/skills/`（symlink → `~/.claude/skills/`）
> 灵感参考：[[动效呈现]] · 第一个 demo：`~/research/hyperframes-demos/01-what-is-skill/`

## 一句话

让 Claude 用 HTML + GSAP/Lottie/CSS/Three.js 描述时间轴，无头浏览器渲染输出 MP4。同输入同输出（确定性），适合工业化模板复用。

## 实战手感（2026-05-08 首次跑通）

- 一段 ~270 行 HTML（含 CSS + GSAP timeline）= 一段 10 秒 3B1B 风讲解动画
- 想法 → MP4 全程 5-10 分钟（含装依赖 / 写代码 / 一次返工）；模板复用后可压到 1-2 分钟
- 3B1B 风格能完全落地：黑底、衬线、几何抽象、点+线层次
- `lint` / `validate` / `inspect` 三道闸把布局 / 对比度 / 动画问题都拦在 render 之前 —— **这是 GUI 工具完全没有的工程化优势**

## 它能做什么（按 skill 入口）

| 想做什么 | 调谁 |
|---|---|
| 写 composition / 字幕 / 转场 / 音频反应 | `/hyperframes` |
| 项目命令 / dev loop（init / preview / render） | `/hyperframes-cli` |
| TTS（Kokoro）/ 转录（Whisper）/ 背景去除（u2net） | `/hyperframes-media` |
| 装第三方 block / 模板 | `/hyperframes-registry` |
| 加动画（任选） | `/gsap` `/lottie` `/three` `/animejs` `/css-animations` `/waapi` |
| 写样式 | `/tailwind` |
| 网站 → 视频 | `/website-to-hyperframes` |
| Remotion 项目迁移 | `/remotion-to-hyperframes` |

## 边界

- 不是非线性剪辑器（不替代 Premiere / 剪映）
- 不做实时直播
- 不含数字人 avatar（HeyGen 主业是数字人，但这套是纯渲染框架）
- 渲染重度依赖本地 FFmpeg + Puppeteer，首次跑要装
- TTS / 转录 / 抠图首次运行各下载自己的模型（Kokoro / Whisper / u2net）

## 已知坑

**中文字体没有 deterministic mapping**（PingFang SC / Source Han Serif SC / STSong / Songti SC 都不在内置列表）。本机渲染靠系统 fallback 能用，但**跨机器（CI / Docker）会渲染失败或字形不一致**。生产视频要用 Google Fonts 的 Noto Serif SC + 显式 `@font-face` 引入。

## 触发场景（OPC）

- 公众号 / 视频号 / 小红书的**讲解动画**（数据飞入、概念图示、流程展开）
- **片头 / 片尾模板**（Logo 飘入、标题动画、订阅引导）
- **金句卡片视频**（文字+背景动效，3-15s 短片段）
- **网页转视频**（产品介绍、报告可视化）

## 依赖（已就绪）

- ✓ Node.js v22.21.1（要求 >= 22）
- ✓ FFmpeg 8.1.1（`brew install ffmpeg`）
- ✓ Puppeteer 自动装 Chromium

## 入口命令速查

```bash
npx hyperframes init <name>     # 脚手架
cd <name>
npm run dev                      # 浏览器实时预览
npm run check                    # lint + validate + inspect
npm run render                   # 渲染 MP4
```

## 后续待探索（不固化）

- 用 InDesign / Imagen / Midjourney 等工具**先出静态设计稿打样**，再喂给 hyperframes 做动画 —— 解决"审美和设计深度受制于直接 prompt"的问题
- `variables` 机制做参数化模板（同模板批量生成 N 条视频）
- 加 TTS 旁白做完整讲解视频
- 解决中文字体 deterministic 问题
