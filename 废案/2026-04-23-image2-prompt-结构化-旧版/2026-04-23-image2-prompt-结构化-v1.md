---
状态: 打磨中
平台: 小红书
预计发布: 2026-04-24 晚 20:00-22:00（§12.8 黄金窗口）
用到的素材:
  - "[[素材库/image2-生图比赛-高赞-prompt-结构化]]"
上版本: "[[草稿/小红书/2026-04-23-image2-prompt-结构化-v0]]"
创建: 2026-04-23
---

# 写 prompt 不是许愿（image 2 高赞 prompt 拆解 v1）

## 发布文案

<!-- 最终复制到小红书的版本。目标字数 500-700。干货向，立场"我最近试了一批"。 -->

同样一句"帮我画一张国潮海报"，有人跑出封神级作品，有人只能得到一张图库通货。**差别不在模型，在 prompt 写法。**

我最近试了一批能稳定跑出 90 分图的 prompt，骨架全是同一套——不像写文案，像写 TODO list。国潮海报、博物馆图鉴、电影 storyboard、老黄历梗图、kawaii 贴纸、iOS UI 卡片、摄影构图、手绘地图、概念艺术全通用。

五个槽位，一个不能少：

**① 主体**：画什么——对象 + 场景 + 动作。不是"一个漂亮的女孩"，是"身穿中国传统服饰的微缩人物，正挥舞一条红色丝绸舞带"。名词带修饰，动词有画面。

**② 构图**：怎么排——视角 / 分区 / 留白比例。最狠的一条是"上大下小的层级结构：上半部分是巨大剪影主体，中下部是完整人物"。画面还没画，分镜已经定好了。

**③ 风格**：像谁——先说"像什么"，再说"不像什么"。"国家博物馆展板、历史服饰图鉴、文博专题信息图，**而不是**普通海报、古风写真、电商详情页"。那个"而不是"比正例还管用，直接把模型往通货方向的偏差掐死。

**④ 光影材质**：质地——"米白、绢纸白、浅茶色纸张质感"、"水墨晕染和虚化破碎"、"云雾环绕，仙气缥缈"。**材质词给越多，图越不塑料感。**

**⑤ 输出规格**：规格——尺寸（9:16）、文字清晰度要求、整体审美收束（"克制、高级、可收藏"）。

最极端一条我跑的博物馆图鉴 prompt——直接 key-value 格式分区："顶部：主标题 + 副标题 / 左侧：结构拆解区 / 右上：材质区 / 右中：纹样区 / 底部：流程图"。**到这一步已经不是 prompt，是一份产品 spec。** 跑出来的图像真的博物馆展板。

反过来看我过去一年写的东西："帮我生成一个海报""帮我写个登录页""帮我优化这段代码"——全是许愿。把 why 糊在脑子里，让模型猜 what 和 how。然后每次结果不对就怪模型蠢。

**MJ 这样，Claude Code 也这样**。你写给 AI 的那段话本质是一份任务说明书，不是一条心愿。槽位缺得越多，它越自由发挥，你就越容易骂街。

我跑出来的 9 张作品 + 对应 9 条 prompt 模板都整理在一个文件里，小红书贴不下——想要的评论区冒个泡我私发。

#Prompt工程 #ChatGPT #AI编程 #vibecoding #AI画图

---

## 相对 v0 的改动

1. **开头换掉叙事钩子**：删除"蹲 278 楼 / yue 了"，改为痛点 Problem Statement ——"同样一句话，跑出的图天差地别，差别在 prompt 写法"。读者 3 秒就知道价值在哪。
2. **立场升档"我最近试了一批"**：全文"我翻到 / 我看到"改为"我试了 / 我跑的"。前提：你今晚真去跑 9 张图。写作上避免暗示"prompt 是我发明的"，但保留"我试过"立场。
3. **删掉"来源 linux.do"的任何显式/隐式引用**：无"蹲帖 / 论坛 / 比赛"字眼
4. **结尾私信钩变成"9 张作品 + 9 条 prompt 模板"**：对应下方 9 图满版
5. **干掉秦始皇主题**（linux 社群标记太强）
6. **补位 4 个新主题**：UI 天气卡片（开发者共鸣）/ 超长焦地标（摄影）/ 美食地图（小红书典型）/ kawaii 贴纸（周边 IP）——让 9 个主题无重叠

## 配图 / 视觉思路（v1 终版：9 张作品图 9 条 prompt 满版干货）

**小红书 9 图上限全打满**。封面用图 1 叠大字（不另做封面图）；结构总览图和可填空模板图挪到私信资料包。

所有模板**至少改 20-30% 关键词**变成你自己的变种。建议变形写在每条下。

---

### 图 1｜城市新春海报（封面位）
**原型**：双重曝光 + S 型构图（结构化典范，视觉最抢眼，做封面合适）
**建议变形**：主体换成你熟悉的城市（杭州 / 成都 / 重庆 / 南京）
```
一张充满新春喜庆氛围但不失高雅格调的 2026 城市宣传海报。双重曝光，
构图延续 S 型流动感；在纯白的纹理背景右下角，身穿中国传统服饰的微缩
人物正挥舞一条长长的红色丝绸舞带，红绸在空中舞动展现柔顺质感，向左
上方飘动过程中奇幻变形成壮丽的山脉河流。在这条"河流"中叠加一个有山
有海河的【你的城市】手绘图，国潮风，壮阔雄伟。画面融入【该城市地标
建筑，列 4-6 个】。云雾环绕，仙气缥缈，色彩丰富，结构复杂，细节丰
富，大面积留白保持清新脱俗。左下角排版"SPRING 2026"和竖排宣传语，
整体寓意"【该城市的两句 slogan】"。文字排版优美清晰，尺寸 9:16。
```

---

### 图 2｜博物馆图鉴信息图（最像 TODO list 的那条）
**原型**：key-value 分区版式
**建议变形**：主题从故宫 → 换成汝窑 / 唐三彩 / 明清家具 / 苏绣 / 景泰蓝 / 宋代点茶 / 唐代乐器
```
请根据【你选的主题】自动生成一张"博物馆图鉴式中文拆解信息图"。要
求整张图兼具真实写实主视觉、结构拆解、中文标注、材质说明、纹样寓
意、色彩含义和核心特征总结。

整体风格应为：国家博物馆展板、历史服饰图鉴、文博专题信息图，而不
是普通海报、古风写真、电商详情页或动漫插画。背景采用米白、绢纸
白、浅茶色等纸张质感，整体高级、克制、专业、可收藏。

版式固定为：
- 顶部：中文主标题 + 副标题 + 导语
- 左侧：结构拆解区，中文引线标注关键部件，并配局部特写
- 右上：材质 / 工艺 / 质感区，展示真实纹理小样并附说明
- 右中：纹样 / 色彩 / 寓意区，展示主色板、纹样样本和文化解释
- 底部：穿着顺序 / 构成流程图 + 核心特征总结

所有文字必须为简体中文，清晰、规整、可读。重点突出真实结构、材质
差异、文化说明与图鉴气质。避免：海报感、电商感、动漫感、cosplay
感、乱标注、错结构、糊字、假材质、过度装饰。
```

---

### 图 3｜电影设定板 storyboard
**原型**：分镜工业规范分区
**建议变形**：场景换成——武侠片山顶对决 / 赛博朋克街头追逐 / 民国上海咖啡馆 / 王家卫风格重庆街头
```
【你选的场景】的影视前期设定板，横版 16:9，黑色标题栏【语言】标
题，左侧为主角服装设定六视图，右侧为【场景类型】场景美术设定与俯
视平面图，中间为 3-4 个电影感分镜镜头：【列 3-4 个具体镜头，如
"侧面中景对话、手部特写、情绪近景、运镜流程图"】，底部加入灯光参
考、导演说明、镜头参数模块，整体像专业导演提案页与 storyboard 文
档，真实摄影拼贴风，排版工整，细节清晰，印刷级质感。
```

---

### 图 4｜程序员老黄历（结构化 ≠ 长 的反证）
**原型**：槽位精简版本
**建议变形**：日期改 4/24 当天 + 你真实语境的「宜/忌/幸运词」
```
高仿真纸质老黄历单页设计，日期 2026 年 4 月 24 日，农历【查一下当
天农历】，宜「【你想要的两个，如"合并代码"/"发第一条小红书"】」，
忌「【你想避开的两个，如"周五上线"/"回复产品经理"】」，今日幸运
词「【自编 1 个，如"AI 不降智"】」，呈现程序员与 AI 协作元素，老
式排版加木刻字体。
```

---

### 图 5｜kawaii 表情包 IP 贴纸（可做账号 mascot / 周边）
**原型**：3D chibi mascot sticker
**建议变形**：形象从 blue whale → 柴犬 / 三花猫 / 仓鼠 / 小熊猫 / 水豚
```
cute 3D anthropomorphic chibi 【你选的动物】 mascot sticker,
rounded chubby body, oversized head, tiny limbs, 【颜色主色
调】 gradient skin, big expressive eyes, pink blush, plush
toy texture, adorable kawaii style, consistent mascot design,
exaggerated facial expression, simple human-like gesture,
single character centered, transparent background, sticker
style, clean composition, not realistic, no background.
```

---

### 图 6｜iOS 26 天气 UI 卡片（★ 开发者共鸣核心）
**原型**：Liquid Glass UI dashboard——把"prompt = 产品 spec"最直观可视化的一条
**建议变形**：4 张卡片可自选——Sunny/Rain/Snow/Fog 或 Spring/Summer/Autumn/Winter
```
A high-fidelity Apple iOS 26 weather dashboard in a landscape
layout, designed in a premium Liquid Glass style. The
interface shows four weather cards arranged horizontally,
each representing: 【你选的 4 种天气】.

Overall design: translucent frosted glass panels, soft
reflections, subtle refraction, glowing edges, background
blur, layered depth, ultra-refined minimalist aesthetics.
Looks like an Apple keynote UI render or a premium iOS
weather app concept, not a generic dashboard.

Each card follows the same design system but distinct
atmosphere:
- 【天气1】: 【对应主色 + 氛围修饰】
- 【天气2】: 【对应主色 + 氛围修饰】
- 【天气3】: 【对应主色 + 氛围修饰】
- 【天气4】: 【对应主色 + 氛围修饰】

Each card contains: weather title, large temperature number,
elegant weather icon, small supporting data (humidity, wind
speed, feels like temp).

Visual style: Apple iOS 26 Liquid Glass aesthetic,
ultra-detailed, premium UI render, crystal-clear hierarchy,
large rounded corners, polished translucent materials,
realistic soft highlights, clean typography, spacious layout,
refined micro-contrast, depth and atmosphere. Minimal elegant
background without clutter.
```

---

### 图 7｜超长焦地标压缩叠图（摄影向）
**原型**：800-1200mm 长焦视觉压缩
**建议变形**：地标链全国风（上海塔 + 黄山 + 布达拉 + 天安门 + 长城）或全世界（自选 4-6 个）
```
A surreal yet photorealistic ultra-telephoto geographic
photograph with extreme spatial compression, vertical
composition, stacked landmarks aligned along a single line of
sight from bottom to top.
- Bottom: 【地标 1，如 Shanghai skyline】
- Middle foreground: 【地标 2，如 layered hills, temples】
- Center: 【地标 3，如 Potala Palace】
- Above it: 【地标 4，如 Great Wall watchtower】
- Top: 【地标 5，如 Everest peak】

Warm sunrise or sunset light, cinematic haze, atmospheric
perspective, natural colors, documentary realism, national
geographic style, ultra detailed architecture, realistic
terrain transitions, compressed depth, 800mm–1200mm
telephoto lens look, no collage seams, no fantasy floating
objects, no illustration, no text, no watermark.
```

---

### 图 8｜城市手绘美食地图（★ 小红书强相关）
**原型**：鸟瞰手绘 + N 地点 key-value 描述
**建议变形**：换成你熟悉的城市 + 5-8 家真吃过的店
```
一幅手绘风格的城市美食地图，以【你的城市】为主题。画面以鸟瞰视角的
手绘简化城市地图为底，标注主要道路（【列 2-3 条城市主干道】）和地
标（【列 3-5 个城市地标】）但不追求精确比例，追求可爱的手绘感。
地图上分布着【5-8 个】美食地点的精致手绘小插画：

- 【店名 1】的【招牌菜】（【外观描述】，推荐语"【一句 8 字口号】"）
- 【店名 2】的【招牌菜】（【外观描述】，推荐语"【口号】"）
- ...

每个插画约占地图的 5% 面积，旁边用手写体标注店名和推荐语。地图边
缘用手绘【本地文化元素，如凤凰花 / 银杏 / 樱花】和波浪纹装饰形成
边框。右下角有手绘指南针和图例说明。左上角标题"【你的城市】寻味
地图"使用胖圆的手绘美术字。整体画风为水彩 + 彩铅混合的手绘质感，
颜色以暖色系为主，横版 16:9。
```

---

### 图 9｜微缩蒸汽朋克灯泡（概念艺术收尾）
**原型**：micro world 概念 + 摄影术语堆叠
**建议变形**：灯泡里换主题——微型蒸汽朋克城市 / 水下珊瑚宫殿 / 月球殖民地 / 深山温泉小镇 / 魔法师书房
```
A hyper-detailed miniature 【你选的场景】 built inside the
glass bulb of a partially shattered vintage incandescent
lightbulb. The lightbulb is resting on a 【底面环境】. 【场
景内部元素 3-5 个】. Surrounded by 【环境氛围】. Magical
cinematic lighting, soft god rays filtering through 【光源
描述】. Macro photography, depth of field, 8k resolution,
Unreal Engine 5 render, surreal fantasy art, masterpiece.
```

---

### 9 图排布（v1 终版 · 满版干货）

| 图位 | 内容 | 亮点 |
|------|------|------|
| 1 | 城市新春海报 | 封面叠大字「写 prompt 不是许愿 / 5 个槽位，9 种跑法」 |
| 2 | 博物馆图鉴 | 最像 TODO list 的案例 |
| 3 | 电影 storyboard | 分镜工业规范 |
| 4 | 程序员老黄历 | 结构化 ≠ 长 |
| 5 | kawaii 贴纸 | 周边 IP 可复用 |
| 6 | iOS UI 卡片 | 开发者共鸣核心 |
| 7 | 超长焦地标 | 摄影压缩构图 |
| 8 | 美食地图 | 小红书生活向 |
| 9 | 微缩灯泡 | 概念艺术 |

**每张图文字叠加**（Figma / Keynote / Canva 加，或让 GPT 出带文字版）：
- 左上角小字：`① 主体｜② 构图｜③ 风格｜④ 光影｜⑤ 输出` 作视觉一致性
- 右下角小字：该案例"关键槽位"高亮（博物馆图鉴高亮 ②，老黄历高亮 ⑤，UI 卡片高亮 ②）

### 私信资料包内容
- 9 条 prompt 完整模板（带占位符）
- 5 层槽位可填空模板（1 页 A4）
- 跑图经验短文（"哪些槽位省了容易出垃圾 / 哪几个关键词是金句"）
- 诚意声明：「这些 prompt 的灵感来自我观察的一个高赞生图话题，我按 5 层槽位重新拆解并用自己场景重写后跑出来」——私信场景诚实度高，**不影响公开帖立场**

---

## 备注 / 思路演化

### 立场档位（v1 诚信边界）
**当前：半实战者档**。
- 你真实跑了 9 张图 ✓（今晚计划，工作量上升到 3-4 小时）
- prompt 骨架是你观察 + 改写 ✓（至少改 20-30% 关键词）
- 不声称"我发明了这套 prompt"✓（文案用"试了""跑的"，不用"我写的 / 我设计的"）

### §8 Checklist 自检（v1 重扫）
1. 立场来源 §0：✅ 半实战者档（前提今晚跑 9 张 + 改关键词）
2. 个人底味 Skill：❌ 无（仍硬凑）
3. 类型判定 §2：干货 + 案例 ✓
4. AI 签名扫描 §3.2（26 条）：
   - #1 公式化问句：无 ✓
   - #4 否定式排比：保留 2 处（"不像写文案，像写 TODO list" 开篇反转必要；"不是一条心愿，是任务说明书" 落脚必要）—— 边缘但接受
   - #5 对比表：备注里有一个 9 图排布表，**正文无** ✓
   - #7 三段式强凑：槽位是 5 不是 3 ✓
   - #10 内联标题+冒号列表：① ② ③ ④ ⑤ —— **命中** ⚠️，但 5 槽位天然就是列表结构，强行打散减损干货感。接受
   - #11 粗体散布：正文 9 处加粗——偏多 ⚠️，发布前考虑去掉 2-3 处行内加粗（例如"差别不在模型，在 prompt 写法"/"那个'而不是'"/"材质词给越多..."可留 2 去 1）
   - #18 商业黑话：零 ✓
   - #20 -ing / 着 尾巴：无 ✓
   - #26 协作交流痕迹：无 ✓
5. 同质化自检：10 个 AI 写会不会一样？不会——5 槽位 + 9 种落地的配对是筛选判断 ✓
6. 钩子强度 §6：开头痛点对比具体（"封神级" vs "图库通货"）✓；结尾私信钩 ✓
7. 密度兑现 §4：5 槽位 + 9 个具体案例（图里一一对应）+ 可复用模板 ✓
8. 人味保留：段落长度不均 ✓；"骂街"一处 ✓；软化词 ✓
9. 平台印记 §12：字数 580-600 ✓；禁用词零 ✓；标签 5 个 ✓；"冒个泡" ✓
10. 自评块 ✓

### 我拿得准的
- 5 槽位论点 + 9 张作品的满版干货，收藏率预期高
- 9 个主题无重叠，覆盖工程师 / 摄影 / 生活 / 梗图 多类读者
- #6 UI 卡片是点睛之笔，直接把 vibe coder 定位锚住

### 我拿不准、需要你拍板的（v1 轮）
1. **今晚 9 张图的工作量**：之前估 2-3 小时，现在要 3-4 小时。你时间 OK 吗？要不要砍到 7 张？砍的话建议砍 #7 超长焦地标 + #9 微缩灯泡（纯视觉向、和账号定位联系最弱）
2. **图 6 UI 卡片 prompt 偏英文长**：中文小红书读者会不会觉得英文长 prompt 看着累？要不要我给个中文版变体？
3. **#11 粗体散布偏多**：正文 9 处加粗要不要精简？你 taste 怎么判？
4. **UI 卡片走"iOS 26 Liquid Glass"**：这是原型里的说法。要不要改成"通用风格"避免苹果商标？
5. **标签 #AI画图** 是否保留：留 → 匹配 AIGC 池；删 → 定位纯但曝光窄
6. **文字叠加**（"① 主体｜② 构图..."角标）：要不要做？做的话 9 张图需要统一模板，工作量再 +1 小时
7. **"冒个泡" vs "扣 1"**：冷启算法激活度，你 taste

## 待办（发之前要完成）

- [ ] **今晚关键动作**：9 条模板化 prompt 填关键词后，去 GPT 跑 9 张图。目标 3-4 小时。跑不通的 prompt 调整重跑
- [ ] 你审稿，标红需要改的口吻和词
- [ ] 回答上面 7 个拿不准的问题
- [ ] 图 1（封面作品）上加大字标题——Figma/Keynote/Canva 任选
- [ ] 9 张图统一角标（可选）
- [ ] 准备私信资料包：9 条模板 + 槽位填空模板 + 跑图经验 + 诚意声明
- [ ] 发布前过一次完整 §8 checklist 最终扫描
