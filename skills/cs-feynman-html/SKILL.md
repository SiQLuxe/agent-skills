---
name: cs-feynman-html
description: "费曼学习法教练 v3.2。用『你教 AI』的角色反转，通过初讲→被追问→重新讲明白三轮暴露并补齐知识盲点，最后把整段过程沉淀为一份生动、单文件、离线可用的交互式 HTML 学习报告：滚动叙事 + 拉幕对比 + 计算阶梯 + 闯关自测；通俗部分用比喻，专业部分用数学公式并配逐步演算。HTML 的版式、模块与配色是默认建议，可按题材调整。触发词：费曼学习、用费曼法帮我理解 XX、检验我对 XX 的理解、假装我在教、费曼卡片、学习报告。"
version: 3.2.0
---

# 费曼学习法 HTML 报告 v3.2

把「教别人」这个核心动作，变成一套**固定、可执行**的协作流程；产出不是聊天记录，而是一份**能反复回看的交互式 HTML 学习资产**。

三轮迭代下来的重点只有两处：
1. **专业部分有公式**，并尽量让公式与图形联动（拖滑块 → 曲线/点阵、读数、公式代入值一起变）。
2. **交付前至少验一次正确性**：公式算出来的数，要和正文写的数一致。

版式、模块、配色属于**默认配方**，不是验收表。题材不合适就换、就砍，说明一句即可。

---

## 0. 这个技能交付什么

一份 `.html` 文件，双击即开，默认不联网、不依赖 CDN。常见配置如下（「核心」= 建议保留，「可选」= 按题材取舍）：

| 区块 | 作用 | 默认 |
| :-- | :-- | :-- |
| 一句话总结（大标题条） | 学完能复述的最小内核 | 核心 |
| 🎚️ 讲解深度滑块 | 同一概念在 6 岁版 / 本质版 / 同行版之间切换 | 核心 |
| 渐进卡片（3–6 张） | 比喻 → 公式 → 本质 → 知识坐标 | 核心 |
| 🧮 计算阶梯 | 有公式时配一份 3–7 步代入演算 | 有公式就配 |
| 🎨 主题与目录 | 几套配色可切并记忆；目录宽屏在右、窄屏在顶 | 默认带上 |
| 🧪 滚动叙事舞台 | 左图随右侧叙事换状态，最后一步交给读者自己拖 | 核心 |
| 🎭 直觉 vs 计算 | 拖中间手柄，对比「多数人会答」和「算出来的」 | 可选 |
| 🔗 可点击因果链 | 逻辑拆成节点，每点给公式 + 「因为…」 | 推荐 |
| 📊 雷达 + 🗺️ 概念地图 | 自评强弱 / 结构化关联 | 可选 |
| 🃏 闪卡 + ✅ 闯关自测 | 一次一题、答错当场解释 | 推荐 |
| 🎬 学习过程回放 + 盲点清单 | 保留认知迭代与复习进度（localStorage） | 推荐 |

砍掉某个模块时，在交付说明里写一句「未启用 X，因为题材没有可模拟的因果」，比硬凑一个假模块好。

---

## 1. 触发与边界

**用**：用户想真正搞懂某个概念、检验自己是否真懂、想要一份学习报告/费曼卡片时。

**不用**：
- 用户只是问事实、要结论、要一段解释 → 直接回答，不要套流程。
- 用户明确说「别问了，直接讲」→ 尊重，但要在报告里说明「本轮跳过追问，盲点清单为空」。

---

## 2. 五条铁律（违反任何一条，报告即失效）

1. **角色反转**：永远让用户先用自己的话讲。AI 抢答 = 费曼法作废。
2. **一次一轮**：Step 1→2→3 之间必须停下等用户回应，禁止自问自答跑完全程。
3. **信源约束**：补知识时优先用用户给的材料；AI 自行补充必须显式标注「**AI 补充，建议核实**」并给来源线索（官方文档 / 教科书章节）。政策、法律、医疗、金融类内容，坚持基于用户提供的原文，不凭空生成解释。
4. **诚实盲点**：盲点清单只能来自对话中真实卡壳的地方，不得为了凑数编造，也不得粉饰。
5. **正确性优先于好看**：公式必须能被数值验算；图形表达的趋势必须与文案一致。**一旦发现"图在说 A、文字在说 B"，必须改，不许交付**。宁可删掉一个花哨模块，也不许留一个错的教学点。

---

## 3. 四步工作流

### Step 1 · 确立概念 & 初次讲解
- 未指定概念就先问：「你想搞懂哪个概念？」
- 明确听众设定：**一个聪明但零基础的高中生**。
- 要求用户用 **3–5 句自己的话**讲一遍。
- 用户只丢来概念名不肯讲 → 礼貌坚持：「先别急，你按自己的理解讲一遍，我来当学生。」
- **完成标准**：收到用户的初次解释文本。

### Step 2 · 新手追问（定位盲点）
- 扮演「较真的新手」，基于用户的解释提 **2–3 个追问**，只从这四类里选：
  - 定义澄清：「你说的 X 具体指什么？」
  - 动机/原因：「为什么会这样？不这样会怎样？」
  - 类比/举例：「能举个生活里的例子吗？」
  - 边界/反例：「什么情况下就不成立了？」
- 专挑**术语复读**和**跳步**的地方下刀（用户说得最顺的那句，往往最没懂）。
- **完成标准**：用户回应，或明确说「不知道」。把这些卡壳点记为**盲点**（后面要进 JSON 的 `gaps`）。

### Step 3 · 补充与简化（二次讲解）
- 对每个卡壳点：先引导用户自己补；确实不会，才按铁律 3 提供信息。
- 要求用户用**一个生活化类比**或**一句话**重新解释核心概念。
- 对比「初讲 vs 修正后」——这个差异就是报告里最值钱的部分。
- **完成标准**：用户给出简化后的解释或类比。

### Step 4 · 生成 HTML 报告
顺序不能颠倒：
1. **先定教学骨架**：这个概念里「哪一条因果链最容易反直觉」？把它定成模拟器要演示的东西。
2. **再定公式**：专业卡要出现哪 2–4 个式子？模拟器里的参数必须是公式里的符号（η、P(H)、r…），不能各说各话。
3. **再选模块**（见 §5）：比例类 → M-A；曲线/迭代类 → M-B。
4. **填数据对象**（§6）。
5. **跑质检**（§8），全部通过才算完成。
6. 保存到工作区 `outputs/`，用文件呈现工具交付。

---

## 4. 内容基线（默认做法 + 常见坑）

| 维度 | 默认做法 | 踩过的坑 |
| :-- | :-- | :-- |
| 依赖 | 单文件，能不联网就不联网（不引 CDN、webfont、外链图） | 断网或内网打开是白屏 |
| 公式 | 有公式就手排 `.math` / `.frac`，别写成 `a/b` 一行 | 一行斜杠当成「有公式」，读者算不出来 |
| 联动 | 滑块最好同时带动图形、读数、公式代入值 | 只有图动、数字死着，等于看动画 |
| 因果 | 因果链点得开，点开给「公式 + 因为…」 | 只有箭头，没有解释 |
| 记忆 | 闪卡能翻、自测给解析、盲点能勾 | 只有静态列表 |
| 主题 | 颜色走 CSS 变量，深浅都看得清 | 写死颜色，深色下白底刺眼或字消失 |
| 窄屏 | 两栏在手机上堆成一栏 | 手机上横向溢出 |
| 语气 | 通俗卡不用术语；专业卡用术语就给符号定义 | 给 6 岁小孩的卡里出现「归一化」 |

纯流程、纯制度、没有可模拟因果的题材：砍掉模拟器与对比区，保留深度卡 + 阶梯 + 自测即可。

---

## 4.5 写作取向（参考值，不必逐条对表）

读者说「看不懂」，通常不是内容错，是下面几件事没做。数字只是参照系，不是及格线。

| 常见问题 | 大致参考 | 为什么 |
| :-- | :-- | :-- |
| 句子太长 | 一句 20–30 字读着舒服 | 中文长句读到后半句，主语已经丢了 |
| 一屏塞太多 | 一屏讲一件事 | 新概念堆一起，等于都没讲 |
| 卡片没重点 | 一句结论 + 一个例子，推导折叠 | 结论埋在推导里，读者抓不到 |
| 术语不解释 | 首次出现顺手加一句白话 | 卡在一个词上，后面全断 |
| 首屏没结论 | 不滚动就能看到「这是什么」 | 前三秒决定读不读 |

**公式三段式（教学场景建议用）**
1. 人话：这条式子在算「什么除以什么」
2. 符号：`P(H|E) = P(E|H)·P(H) / P(E)`
3. 代数字：`= 99%×1% ÷ (99%×1% + 5%×99%) = 16.7%`

只给符号像天书，只给数字记不住；三段都在，读者既懂又记得住。

**有公式时，配一份「计算阶梯」**：3–7 步代入演算，每步写清「先算什么」和「这个结果在推理里充当什么（分子 / 分母 / 结论）」。末步数字跟正文、模拟器读数对得上就行。

**交互块前面写清怎么用**（这块最容易被跳过）：
`现在做：把患病率拖到 0.1% → 盯住 后验 → 它应该掉到 2% 以下`
操作后顺手回一句「变了什么、为什么变」。只改数字不解释，读者不知道自己看的是什么。
控件带范围和单位；重置按钮写明回到哪个初始值，别只写「重置」。

**动线**：结论 → 动手 → 原理 → 记忆 → 复盘，是默认顺序。题材不合适可以重排，但别让读者一进来就撞上公式。

---

## 4.6 默认皮肤（用户没另指定时用这套）

这几轮调出来的默认值，觉得不合适直接改，不用回来对表。

- **字体**：中文优先系统无衬线（`Microsoft YaHei`、`PingFang SC` 等）。避免只写 `serif` 或 `Songti SC`——Windows 上没有后者，会回退到宋体，屏显发灰。
- **版心**：内容宽一点（1000–1100px）比窄栏耐看；但正文段落单独限宽（约 45em），否则一行太长读着串。
- **首屏**：标题 + 一句钩子 + 一个够大的结论数字。先给答案，再讲过程。
- **主题**：备 3–4 套（纸白 / 墨夜 / 冷蓝 / 暖砂），CSS 变量驱动，右上角色点切换，选择记在 localStorage。切主题时 Canvas 颜色要跟着重绘。
- **目录**：宽屏放右侧竖排、窄屏收成顶部标签，都吸顶；两套 DOM 一起渲染，高亮同步。
- **别横向滚动**：公式块不加 `overflow-x:auto`；grid / flex 子项加 `min-width:0`；窄屏把对比区和表格堆成单列。

**两个踩过的坑（供参考）**
- 祖先容器加 `overflow-x:clip` 会打断 `sticky`——吸顶目录和画布跟着页面滚走，看起来像「目录没了」。
- 用很窄判定带的 `IntersectionObserver` 做章节高亮，经常一个都不亮；改成取「最后一个 `top ≤ 150` 的章节」更稳。

---

## 5. 可视化模块（二选一，按概念性质定）

### M-A `proportion` · 比例/概率/筛查类
适合：贝叶斯、准确率与患病率、转化率、留存、A/B 测试、混淆矩阵。
**它擅长演的因果**：*分母陷阱*——分子看着大，被更大的分母稀释。

做法：把总体拆成 N 个点（默认 1000），按四类着色（真阳/假阴/假阳/真阴），滑块改比例，点阵、读数、公式代入值同时刷新。

```js
{"kind":"proportion","total":1000,
 "intro":"一句话告诉用户该动哪个滑块、会看到什么",
 "calc":{"prior":"prev","tp":"sens","tn":"spec"},   // 三个滑块 id 的语义映射（先验 / 命中 / 正确排除）
 "sliders":[{"id":"prev","label":"患病率 P(病)","min":0.0001,"max":0.2,"step":0.0001,"value":0.01,"fmt":"pct2"},
            {"id":"sens","label":"灵敏度 P(阳|病)","min":0.5,"max":0.999,"step":0.001,"value":0.99,"fmt":"pct1"},
            {"id":"spec","label":"特异度 P(阴|健康)","min":0.5,"max":0.999,"step":0.001,"value":0.95,"fmt":"pct1"}],
 "presets":[{"name":"🏥 常规体检","v":{"prev":0.01,"sens":0.99,"spec":0.95}}],
 "readout":{"main":"后验 P(病|阳)","a":"真阳人数","b":"假阳人数","c":"阳性总数"},
 "barA":"直觉以为","barB":"贝叶斯算",
 "zoomOn":"🔍 只看阳性结果","zoomOff":"显示全部人群",
 "highlight":4,                                    // 滑块变动时联动高亮因果链第几个节点（0 起）
 "formulaHTML":function(c,S,pct){ return '…代入实际数字的公式…'; },
 "teach":function(c,S,pct){ return c.post<0.1?'…危险区…':'…'; }}
```
`c` 里可直接用 `tp/fn/fp/tn/pos/post`；`S` 是当前滑块值对象。`fmt` 取 `pct2` / `pct1` / 原样。
> `formulaHTML` 与 `teach` 是**函数**（`D` 是 JS 对象，不是纯 JSON），因为它们必须跟着滑块实时算。

### M-B `step` · 曲线/迭代/优化/增长类
适合：梯度下降、牛顿法、复利、指数衰减、不动点迭代、收敛与发散。
**它擅长演的因果**：*步长/参数越过临界值后行为突变*。

```js
{"kind":"step","eta0":0.15,"etaMax":3,"etaLabel":"步长 η","x0Label":"起点","noiseLabel":"随机扰动 σ",
 "kA":"当前位置","kB":"目标函数","kC":"当前斜率","kD":"状态",
 "curves":[{"id":"convex","name":"凸函数","f":"0.5*(x-1)*(x-1)+0.5","df":"(x-1)","domain":[-2,4],"start":-1.6,"minima":[1]},
           {"id":"nonconvex","name":"非凸函数","f":"0.06*x*x*x*x-0.36*x*x+0.3*x+3.5","df":"0.24*x*x*x-0.72*x+0.3","domain":[-3.2,3.8],"start":3.0,"minima":[-1.9,1.47]}],
 "teach":[{"lt":0.25,"text":"步长太小，走得很慢…"},
          {"lt":2,"text":"处在会震荡但最终收敛的区间…"},
          {"text":"越过临界值，会越跳越高直到发散…"}]}
```
`f`/`df` 是**表达式字符串**，运行时用 `new Function` 求值——只写纯数学表达式，不要写语句。
`teach` 按顺序取第一个满足 `η < lt` 的条目（最后一条不写 `lt` 作兜底）。

> 选择口诀：**能数人头 → M-A；能画一条曲线 → M-B。**
> 两个都不合适（如纯流程/制度类），才退回「无模拟器」模式，并在报告里说明原因。

---

## 6. 数据对象（Step 4 填充的唯一数据源）

```json
{
  "concept": "概念名",
  "subtitle": "一句钩子，最好是反直觉的问句",
  "heroNum": "16.7%",
  "heroCap": "阳性者中真患病比例",
  "date": "YYYY-MM-DD",
  "oneLiner": "一句话内核",
  "depth": [
    {"label":"🧒 6 岁版","html":"0 术语，只用具体数字/比喻"},
    {"label":"💡 本质版","html":"讲清它解决什么问题"},
    {"label":"🎓 同行版","html":"必须含公式，可含推导"}
  ],
  "ladder": {
    "setup": "给定：1000 人、患病率 1%、灵敏度 99%、特异度 95%",
    "steps": [
      {"eq": "1000 × 1%", "res": "10 人", "why": "先数清场子里有几个病人，后面才有对象可数"},
      {"eq": "10 × 99%", "res": "9.9 人", "why": "病人里 99% 会被查出，这是分子：真阳性"},
      {"eq": "990 × 5%", "res": "49.5 人", "why": "健康人也有 5% 被误报，这是分母里最容易被忘掉的一块"},
      {"eq": "9.9 + 49.5", "res": "59.4 人", "why": "所有亮红灯的人。分母不是病人数，是它"},
      {"eq": "9.9 ÷ 59.4", "res": "16.7%", "why": "亮红灯的人里，真病人占多大份额——这就是后验"}
    ]
  },
  "terms": [
    {"t":"先验","d":"还没看证据时，你原本认为的可能性有多大"}
  ],
  "cards": [
    {"icon":"🧒","title":"给 6 岁小孩讲","tag":"0 术语","content":"<p>…≤120 字…</p>"},
    {"icon":"🎓","title":"给同行讲","tag":"公式 · 可推导","lead":"<p>…一句结论…</p>","more":"<p>…推导/术语细节，默认折叠…</p>"},
    {"icon":"💡","title":"核心本质","tag":"提炼","content":"<p>…</p>"},
    {"icon":"📍","title":"知识坐标","tag":"关联 · 防混淆","lead":"<p>…一句…</p>","more":"<p>…对比表…</p>"},
    {"icon":"⚠️","title":"我的盲点清单","tag":"知道自己不知道","content":"<p>见下方…</p>"},
    {"icon":"🗺️","title":"概念地图","tag":"结构化","content":"<p>见下方…</p>"}
  ],
  "sim": { "kind": "proportion …或 step…",
           "look": {"do":"把患病率拖到 0.1%","watch":"右上方『后验』那个数","expect":"它会从 16.7% 掉到 2% 以下","why":"健康人基数变大，假阳人数压过真阳"} },
  "scenes": [
    {"t":"先看这 1000 人","p":"只有 10 个红点。","v":{"prev":0.01,"sens":0.99,"spec":0.95},"zoom":false},
    {"t":"报警器响了 59 次","p":"9.9 个真病人 + 49.5 个误报。","v":{"prev":0.01,"sens":0.99,"spec":0.95},"zoom":true}
  ],
  "compare": {
    "leftLabel":"直觉 · 多数人会答","leftNum":"99%","leftText":"…只用了灵敏度…",
    "rightLabel":"计算 · 贝叶斯给的值","rightNum":"16.7%","rightText":"…真病人只占 9.9/59.4…",
    "note":"差额全部来自分母里那 49.5 个假阳性。"
  },
  "chain": [{"t":"节点名","f":"该步公式","r":"为什么会有这一步"}],
  "gaps": [{"question":"卡壳的问题","why":"为什么这是盲点","answer":"补齐后的答案","resolved":false}],
  "quiz": [{"q":"题干","opts":["A","B","C","D"],"a":2,"why":"解析"}],
  "scores": {"完整性":3,"准确性":4,"深度":2,"关联性":3,"表达力":4},
  "map": {"label":"根","children":[
    {"label":"分支一","children":[{"label":"叶子"}]},
    {"label":"易混","children":[{"label":"A vs B"}]}
  ]},
  "rounds": [{"label":"① 初讲 · 我试着教","userText":"…","aiText":"…"}]
}
```

**填写纪律**
- 写文案时参考 §4.5 的取向：句子别太长、单卡别贪多、术语顺手解释一句。
- 长推导放 `more`（默认折叠），`lead` 只写一句结论。
- `terms` 给 3–6 条，专收**读者会卡住的词**，每条一句话，别写成教科书定义。
- `sim.look` 尽量具体到「拖到哪个值、盯哪个数字、变成多少」；写「观察变化」等于没写。
- `a` 是**正确项下标**（0 起），必须与 `opts` 对得上。
- `gaps` 3 条左右，必须是真实卡壳点；`answer` 要能独立读懂。
- `rounds` 3 轮：初讲 → 被问住 → 重新讲明白；AI 自行补充的话术里必须出现「AI 补充，建议核实」。
- `chain` 5–7 个节点，最后两个一般是「结果」和「决策阈值」。
- `scores` 五维 0–5 整数，`深度` 通常最低（这正是要补的）。

---

## 7. HTML 模板

把下面整段复制成 `.html`，然后把 `{{DATA_JSON}}` 替换成你的数据对象（保留外层 `const D=` 与结尾 `;`）。
模板自包含：雷达图用内联 SVG 算，点阵用 Canvas 画，进度用 localStorage 存，深/浅色用 CSS 变量切。

```html
<!DOCTYPE html>
<html lang="zh-CN" data-theme="paper">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1">
<title>费曼学习报告 · {{CONCEPT}}</title>
<style>
:root{--bg:#f6f7fb;--fg:#1a1c23;--card:#fff;--muted:#667;--line:#e6e8ef;--accent:#5b6cff;--accent2:#ff7a59;--gap:#fff8e1;--gapline:#ffc107;--ok:#16a34a;--warn:#e0a800;--bad:#e5484d;--shadow:0 8px 24px rgba(20,25,60,.08)}
html[data-theme=dark]{--bg:#0f1220;--fg:#e8eaf2;--card:#191d31;--muted:#9aa;--line:#2a2f49;--accent:#7d8cff;--accent2:#ff9166;--gap:#2b2510;--gapline:#8a6d00;--ok:#34d399;--warn:#fbbf24;--bad:#fb7185;--shadow:0 8px 24px rgba(0,0,0,.4)}
*{box-sizing:border-box}body{margin:0;font-family:system-ui,-apple-system,"Segoe UI",Roboto,"Microsoft YaHei",sans-serif;background:var(--bg);color:var(--fg);line-height:1.75}
.hero{padding:48px 24px 34px;background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff}
.hero .wrap,main{max-width:880px;margin:0 auto}
.hero h1{margin:0;font-size:clamp(24px,4vw,38px);font-weight:800;letter-spacing:-.5px}
.hero p{margin:10px 0 0;opacity:.95;font-size:15px}
.badge{display:inline-block;background:rgba(255,255,255,.2);padding:4px 12px;border-radius:999px;font-size:13px;margin-bottom:14px}
main{margin:-18px auto 60px;padding:0 24px}
.toolbar{display:flex;justify-content:flex-end;margin-bottom:10px}
button.tg{background:var(--card);color:var(--fg);border:1px solid var(--line);border-radius:10px;padding:7px 14px;cursor:pointer;font-size:13px;box-shadow:var(--shadow)}
.card{background:var(--card);border:1px solid var(--line);border-radius:16px;padding:22px 24px;margin-bottom:20px;box-shadow:var(--shadow)}
.card h2{margin:0 0 4px;font-size:20px;display:flex;align-items:center;gap:10px}
.card h2 .ic{font-size:24px}
.tag{display:inline-block;font-size:12px;color:var(--accent);background:color-mix(in srgb,var(--accent) 12%,transparent);padding:2px 10px;border-radius:999px;margin-bottom:12px}
.card p{margin:8px 0}
.oneliner{font-size:18px;font-weight:700;text-align:center;background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff;border-radius:16px;padding:24px;line-height:1.6}
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:18px}
@media(max-width:680px){.grid2{grid-template-columns:1fr}}
.foot{text-align:center;color:var(--muted);font-size:13px;margin:30px}
code{background:color-mix(in srgb,var(--accent) 10%,transparent);padding:1px 6px;border-radius:6px}
.hint{font-size:13px;color:var(--muted)}
.math{font-family:"Cambria Math","Latin Modern Math",Georgia,"Times New Roman",serif;font-size:1.15em;text-align:center;padding:14px 12px;margin:12px 0;background:color-mix(in srgb,var(--accent) 7%,transparent);border-radius:12px;overflow-x:auto}
.math i,.math var{font-style:italic}
.frac{display:inline-flex;flex-direction:column;text-align:center;vertical-align:-.55em;margin:0 4px;line-height:1.25}
.frac>span{padding:0 8px;display:block}
.frac>span:first-child{border-bottom:1.4px solid currentColor}
.frac.small{font-size:.82em}
.depth-head{display:flex;align-items:center;gap:14px;flex-wrap:wrap}
.depth-head input[type=range]{flex:1;min-width:180px;accent-color:var(--accent);cursor:pointer}
.depth-lv{display:flex;justify-content:space-between;font-size:12px;color:var(--muted);margin:2px 0 14px}
#depthText{min-height:86px;padding:16px;border-radius:12px;border-left:4px solid var(--accent);background:color-mix(in srgb,var(--accent) 8%,var(--card));font-size:15px;transition:opacity .2s}
#depthText .m{font-size:.98em}
.zones{display:flex;gap:10px;flex-wrap:wrap;margin:6px 0 14px}
.zones button{flex:1;min-width:150px;background:var(--card);border:1.5px solid var(--line);color:var(--fg);padding:9px 10px;border-radius:12px;cursor:pointer;font-size:13px;font-weight:600;transition:.2s}
.zones button.active{border-color:var(--accent);background:color-mix(in srgb,var(--accent) 12%,var(--card));color:var(--accent)}
#sim{width:100%;height:auto;display:block;border-radius:12px;border:1px solid var(--line);background:color-mix(in srgb,var(--fg) 3%,var(--card))}
.legend{display:flex;gap:16px;flex-wrap:wrap;font-size:13px;color:var(--muted);margin:10px 2px}
.legend i{display:inline-block;width:12px;height:12px;border-radius:3px;margin-right:6px;vertical-align:-1px}
.sim-controls{display:grid;grid-template-columns:1fr 1fr;gap:14px 22px;margin:16px 0 6px}
@media(max-width:680px){.sim-controls{grid-template-columns:1fr}}
.sim-controls label{font-size:13px;font-weight:600;color:var(--muted);display:flex;align-items:center;gap:10px}
.sim-controls input[type=range]{flex:1;accent-color:var(--accent);cursor:pointer}
.sim-controls output{min-width:56px;text-align:right;font-family:"Cambria Math",serif;color:var(--fg);font-weight:700}
.sim-btns{display:flex;gap:10px;flex-wrap:wrap;margin:12px 0 4px}
.sim-btns button{background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff;border:none;padding:9px 16px;border-radius:10px;cursor:pointer;font-size:13px;font-weight:700;box-shadow:var(--shadow)}
.sim-btns button.ghost{background:var(--card);color:var(--fg);border:1px solid var(--line);box-shadow:none}
.readout{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin:14px 0 4px}
@media(max-width:680px){.readout{grid-template-columns:1fr 1fr}}
.kpi{border:1px solid var(--line);border-radius:12px;padding:10px 12px;background:color-mix(in srgb,var(--fg) 3%,var(--card))}
.kpi .k{font-size:12px;color:var(--muted)}
.kpi .v{font-size:20px;font-weight:800;font-family:"Cambria Math",serif}
.kpi.hi{border-color:var(--accent);background:color-mix(in srgb,var(--accent) 10%,var(--card))}
.kpi.hi .v{color:var(--accent)}
.bars{margin:12px 0 2px}
.bar{display:flex;align-items:center;gap:10px;font-size:13px;margin:6px 0}
.bar .nm{width:96px;color:var(--muted);flex:0 0 auto}
.bar .tr{flex:1;height:14px;background:var(--line);border-radius:999px;overflow:hidden}
.bar .fl{height:100%;border-radius:999px;transition:width .35s}
.bar .pc{width:52px;text-align:right;font-weight:700;font-family:"Cambria Math",serif}
.sim-teach{margin-top:14px;padding:14px 16px;border-radius:12px;border-left:4px solid var(--accent2);background:color-mix(in srgb,var(--accent2) 8%,var(--card));font-size:14px;min-height:54px}
.pill{padding:3px 12px;border-radius:999px;font-size:12px;font-weight:700;color:#fff;background:var(--muted)}
.pill.ok{background:var(--ok)}.pill.warn{background:var(--warn)}.pill.bad{background:var(--bad)}.pill.go{background:var(--accent)}
.flow{display:flex;flex-wrap:wrap;align-items:stretch;justify-content:center;margin:14px 0}
.fstep{position:relative;background:var(--card);border:1.5px solid var(--line);border-radius:12px;padding:10px 14px;cursor:pointer;min-width:112px;text-align:center;transition:.2s;margin:8px 4px}
.fstep.active{border-color:var(--accent);background:color-mix(in srgb,var(--accent) 14%,var(--card));transform:translateY(-3px);box-shadow:var(--shadow)}
.fstep .fn{font-size:11px;color:var(--accent);font-weight:800}
.fstep .ft{font-size:14px;font-weight:700;margin-top:2px}
.fstep .ff{font-family:"Cambria Math",serif;font-size:14px;margin-top:6px}
.farrow{align-self:center;color:var(--accent2);font-size:22px;font-weight:800;margin:0 2px;animation:pulse 1.6s infinite}
@keyframes pulse{0%,100%{opacity:.35}50%{opacity:1}}
.flow-detail{border:1px solid var(--line);border-radius:14px;padding:18px;background:color-mix(in srgb,var(--accent) 5%,var(--card))}
.flow-detail .fd-t{font-weight:800;font-size:16px}
.flash-wrap{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px}
@media(max-width:680px){.flash-wrap{grid-template-columns:1fr}}
.flash{perspective:1000px;cursor:pointer;min-height:190px}
.flash-in{position:relative;width:100%;height:100%;transition:transform .6s;transform-style:preserve-3d}
.flash.flip .flash-in{transform:rotateY(180deg)}
.face{position:absolute;inset:0;backface-visibility:hidden;border-radius:14px;padding:16px;display:flex;flex-direction:column;justify-content:center;border:1px solid var(--line);overflow:auto}
.face.front{background:var(--gap);border-left:4px solid var(--gapline)}
.face.back{background:color-mix(in srgb,var(--ok) 12%,var(--card));transform:rotateY(180deg);font-size:13.5px}
.face .lbl{font-size:12px;color:var(--muted);font-weight:700;margin-bottom:8px}
.flash .q{font-weight:600;font-size:15px}
.gaplist{list-style:none;padding:0;margin:0}
.gaplist li{display:flex;gap:12px;align-items:flex-start;padding:12px;border:1px solid var(--line);border-left:4px solid var(--gapline);background:var(--gap);border-radius:10px;margin-bottom:10px}
.gaplist input{margin-top:6px;width:18px;height:18px;flex:0 0 auto;cursor:pointer}
.gaplist .q{font-weight:600}.gaplist .w{font-size:13px;color:var(--muted)}
.gaplist li.done{opacity:.55}.gaplist li.done .q{text-decoration:line-through;text-decoration-color:var(--ok)}
.prog{height:8px;background:var(--line);border-radius:999px;overflow:hidden;margin:12px 0}
.prog>i{display:block;height:100%;background:linear-gradient(90deg,var(--accent),var(--accent2));width:0;transition:width .4s}
details{border:1px solid var(--line);border-radius:12px;padding:4px 16px;margin-bottom:12px;background:var(--card)}
summary{cursor:pointer;font-weight:700;padding:12px 0;list-style:none;display:flex;align-items:center}
summary:before{content:"▸";color:var(--accent);margin-right:8px;transition:.2s;display:inline-block}details[open] summary:before{transform:rotate(90deg)}
.turn{padding:12px 14px;border-radius:12px;margin:8px 0}
.turn.user{background:color-mix(in srgb,var(--accent) 10%,transparent);border-left:3px solid var(--accent)}
.turn.ai{background:color-mix(in srgb,var(--accent2) 10%,transparent);border-left:3px solid var(--accent2)}
.turn .who{font-size:12px;color:var(--muted);font-weight:700;letter-spacing:.04em}
.map{display:flex;flex-direction:column;align-items:center;padding:10px 0}
.node{background:var(--card);border:1px solid var(--line);border-radius:10px;padding:6px 14px;font-weight:600;margin:4px 0;box-shadow:var(--shadow);text-align:center}
.root{background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff;border:none}
.branch{display:flex;gap:14px;flex-wrap:wrap;justify-content:center;border-top:2px solid var(--line);padding-top:10px;margin-top:6px;width:100%}
.sub{display:flex;flex-direction:column;align-items:center}
.sub .node{font-weight:500;font-size:13px}
.qopt{display:block;width:100%;text-align:left;margin:6px 0;padding:9px 14px;border:1px solid var(--line);background:var(--card);color:var(--fg);border-radius:10px;cursor:pointer;font-size:14px}
.qopt:hover{border-color:var(--accent)}
/* ---- 阅读动线导航 ---- */
.steps{position:sticky;top:0;z-index:9;display:flex;gap:8px;overflow-x:auto;padding:10px 2px;margin:0 0 14px;background:color-mix(in srgb,var(--bg) 88%,transparent);backdrop-filter:blur(8px);border-bottom:1px solid var(--line)}
.steps a{flex:0 0 auto;text-decoration:none;font-size:13px;font-weight:700;color:var(--muted);border:1px solid var(--line);background:var(--card);padding:5px 12px;border-radius:999px;white-space:nowrap}
.steps a:hover{color:var(--accent);border-color:var(--accent)}
#sec-sim,#cards,#sec-terms,#sec-memory,#sec-rounds{scroll-margin-top:64px}
/* ---- 交互四段式 ---- */
.look{display:grid;gap:8px;margin:14px 0 16px}
.look .row{display:flex;gap:10px;align-items:flex-start;padding:10px 14px;border-radius:12px;background:color-mix(in srgb,var(--accent) 6%,var(--card));border:1px solid var(--line);font-size:14px}
.look .row b{flex:0 0 4.2em;color:var(--accent);font-size:13px}
.look .row.watch{background:color-mix(in srgb,var(--accent2) 9%,var(--card));border-color:color-mix(in srgb,var(--accent2) 35%,var(--line))}
.look .row.watch b{color:var(--accent2)}
/* ---- 术语速查 ---- */
.terms{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:680px){.terms{grid-template-columns:1fr}}
.terms details{border:1px solid var(--line);border-radius:10px;padding:2px 14px;margin:0;background:color-mix(in srgb,var(--fg) 2%,var(--card))}
.terms summary{font-weight:700;font-size:14px;padding:10px 0}
.terms .td{font-size:13.5px;color:var(--muted);padding-bottom:10px;line-height:1.7}
details.fold{border:none;padding:0;margin:10px 0 0;background:transparent}
details.fold summary{display:inline-flex;font-size:13px;color:var(--accent);border:1px dashed var(--line);border-radius:999px;padding:4px 12px}
details.fold summary:before{content:"＋";margin-right:6px}
details.fold[open] summary:before{content:"－"}
/* ===== EDITORIAL SKIN v2.2（覆写以上全部视觉，只换皮不动结构） ===== */
:root{--bg:#f4f1ea;--fg:#15120d;--card:#fbf9f4;--muted:#8b8070;--line:#d6cdbd;--accent:#a33420;--accent2:#8a6d3b;--ok:#3f6b3f;--warn:#a9761b;--bad:#a33420;--gap:#f7f1df;--gapline:#c9a227;--shadow:none}
html[data-theme=dark]{--bg:#14120f;--fg:#ece5d8;--card:#1b1813;--muted:#8f8574;--line:#332d25;--accent:#e0734f;--accent2:#c9a227;--ok:#7fae7f;--warn:#d8a13f;--bad:#e0734f;--gap:#221d15;--gapline:#8a6d00;--shadow:none}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--fg);font:400 17px/1.9 Georgia,"Songti SC","Times New Roman",serif}
.paper{max-width:760px;margin:0 auto;padding:54px 28px 72px}
main.paper{margin:0 auto}
.masthead{margin-bottom:8px}
.kicker{display:inline-block;font:700 11px/1 ui-sans-serif,system-ui;letter-spacing:.22em;text-transform:uppercase;color:var(--accent);margin-bottom:18px}
.masthead h1{font-size:clamp(38px,6vw,62px);line-height:1.04;letter-spacing:-1.6px;font-weight:400;margin:0 0 10px}
.dek{font-size:22px;color:var(--fg);margin:0 0 22px;font-style:normal;font-weight:600;letter-spacing:-.2px;line-height:1.5;opacity:1}
.rule{height:1px;background:var(--line);margin:24px 0}
.thesis{font-size:20px;line-height:1.8;margin:0;padding:0;background:none;color:var(--fg);text-align:left;font-weight:400;border-radius:0}
.thesis b{font-weight:600;background:linear-gradient(transparent 66%,color-mix(in srgb,var(--accent) 16%,transparent) 66%)}
.toolbar{display:flex;justify-content:flex-end;margin:14px 0 0}
button.tg{background:none;border:1px solid var(--line);border-radius:2px;color:var(--muted);font:600 11px/1 ui-sans-serif;letter-spacing:.1em;padding:7px 11px;cursor:pointer;box-shadow:none}
button.tg:hover{color:var(--accent);border-color:var(--accent)}
/* 章节：自动编号，卡片变条目 */
#sec-sim,#cards,#sec-terms,#sec-memory,#sec-rounds,.card{scroll-margin-top:24px}
.paper{counter-reset:sec}
.card,.subsec{background:none;border:0;border-top:1px solid var(--line);border-radius:0;box-shadow:none;padding:26px 0 6px;margin:0}
main>.card,main>.subsec{counter-increment:sec}
.card h2,.subsec h2{font:700 19px/1.5 ui-sans-serif,system-ui,"Microsoft YaHei";margin:0 0 6px;display:flex;align-items:baseline;gap:12px;letter-spacing:-.2px}
main>.card>h2:before,main>.subsec>h2:before{content:counter(sec,decimal-leading-zero);font:700 11px/1 ui-sans-serif;letter-spacing:.18em;color:var(--accent);flex:0 0 auto}
.card h2 .ic{display:none}
.card .tag{display:block;font:800 13px/1.5 ui-sans-serif;letter-spacing:.06em;text-transform:uppercase;color:var(--accent);background:none;padding:0;margin:0 0 14px 34px;border-radius:0}
#cards .card{border-top:0;padding:18px 0 2px}
#cards .card h2{font-size:17px;margin-bottom:2px}
#cards .card .tag{margin:0 0 10px}
.card p{margin:10px 0;font-size:17px;line-height:1.9}
.card b,strong{font-weight:600}
/* 公式：书页式上下细线 */
.math{background:none;border-top:1px solid var(--line);border-bottom:1px solid var(--line);border-radius:0;padding:18px 4px;margin:20px 0;font-size:1.24em;text-align:center}
.frac>span:first-child{border-bottom:1px solid currentColor}
/* 深度滑块 */
.depth-head input[type=range]{accent-color:var(--accent);height:2px}
.depth-lv{font:700 11.5px/1.5 ui-sans-serif;letter-spacing:.1em;text-transform:uppercase;color:var(--accent2);margin:6px 0 16px}
#depthText{background:none;border:0;border-left:2px solid var(--accent);border-radius:0;padding:2px 0 2px 20px;font-size:17.5px;min-height:80px;opacity:1!important;transition:none}
/* 模拟器 */
#sim{border:1px solid var(--line);border-radius:2px;background:var(--card)}
.zones button{background:none;border:1px solid var(--line);border-radius:2px;font:600 12px/1 ui-sans-serif;letter-spacing:.06em;padding:9px 12px}
.zones button.active{background:none;border-color:var(--accent);color:var(--accent)}
.look{gap:4px;margin:16px 0 18px;border-left:2px solid var(--accent);padding-left:18px}
.look .row{display:grid;grid-template-columns:4.4em 1fr;gap:10px;background:none;border:0;border-radius:0;padding:3px 0;font:400 14.5px/1.7 ui-sans-serif}
.look .row b,.look .row.watch b{color:var(--accent);font:700 10px/1.7 ui-sans-serif;letter-spacing:.14em;text-transform:uppercase}
.look .row.watch{background:none;border:0}
.sim-controls{grid-template-columns:1fr 1fr;gap:12px 26px}
.sim-controls label{font:600 11px/1.4 ui-sans-serif;letter-spacing:.08em;color:var(--muted)}
.sim-controls output{font:600 14px/1 ui-sans-serif;letter-spacing:0}
.sim-btns button{background:none;border:1px solid var(--line);border-radius:2px;color:var(--fg);font:600 12px/1 ui-sans-serif;box-shadow:none;padding:9px 14px}
.sim-btns button:hover{border-color:var(--accent);color:var(--accent)}
.sim-btns button.ghost{background:none}
.readout{display:flex;flex-wrap:wrap;gap:34px;border-top:1px solid var(--line);border-bottom:1px solid var(--line);padding:16px 0;margin:20px 0 6px}
.kpi{background:none;border:0;border-radius:0;padding:0}
.kpi .k{font:600 10px/1.5 ui-sans-serif;letter-spacing:.14em;text-transform:uppercase;color:var(--muted)}
.kpi .v{font:400 32px/1.2 Georgia,serif;letter-spacing:-1px}
.kpi.hi{background:none;border:0}
.kpi.hi .v{color:var(--accent)}
.bar .tr{height:5px;background:var(--line);border-radius:0}
.bar .fl{border-radius:0}
.bar .nm,.bar .pc{font:600 11px/1.6 ui-sans-serif;letter-spacing:.04em}
.sim-teach{background:none;border:0;border-left:2px solid var(--accent2);border-radius:0;padding:4px 0 4px 18px;font-size:16px}
.legend{font:600 10px/1.6 ui-sans-serif;letter-spacing:.1em;text-transform:uppercase;color:var(--muted)}
.legend i{border-radius:50%;width:8px;height:8px}
/* 因果链：竖排书页式 */
.flow{display:block;border-left:1px solid var(--line);padding-left:26px;margin:8px 0}
.fstep{display:block;position:relative;min-width:0;text-align:left;background:none;border:0;border-radius:0;padding:12px 0;margin:0;transform:none!important;box-shadow:none!important}
.fstep:before{content:"";position:absolute;left:-30px;top:20px;width:7px;height:7px;border-radius:50%;background:var(--line)}
.fstep.active{background:none;color:var(--accent)}
.fstep.active:before{background:var(--accent);box-shadow:0 0 0 4px color-mix(in srgb,var(--accent) 14%,transparent)}
.fstep .fn{font:700 10px/1 ui-sans-serif;letter-spacing:.2em;color:var(--muted)}
.fstep.active .fn{color:var(--accent)}
.fstep .ft{font:600 17px/1.5 ui-sans-serif;margin:2px 0}
.fstep .ff{font-size:15px;color:var(--muted);margin-top:2px}
.fstep.active .ff{color:var(--fg)}
.farrow{display:none}
.flow-detail{border:0;border-top:1px solid var(--line);border-radius:0;background:none;padding:18px 0 0;margin-top:4px}
.flow-detail .fd-t{font:700 12px/1.6 ui-sans-serif;letter-spacing:.12em;text-transform:uppercase;color:var(--accent)}
/* 术语 */
.terms{grid-template-columns:1fr 1fr;gap:0 34px}
.terms details{border:0;border-bottom:1px dotted var(--line);border-radius:0;background:none;padding:0}
.terms summary{font:600 15px/1.6 ui-sans-serif;padding:11px 0}
.terms .td{font-size:14.5px;color:var(--muted);padding:0 0 12px;line-height:1.8}
details.fold summary{font:600 11px/1 ui-sans-serif;letter-spacing:.1em;border:1px dashed var(--line);border-radius:2px;padding:6px 12px;color:var(--accent)}
/* 闪卡 / 自测 / 清单 / 回放 */
.flash{min-height:180px}
.face{border:1px solid var(--line);border-radius:2px;background:var(--card);padding:18px}
.face.front{border-left:2px solid var(--gapline);background:var(--gap)}
.face.back{border-left:2px solid var(--ok);background:var(--card)}
.face .lbl{font:700 10px/1.4 ui-sans-serif;letter-spacing:.14em;text-transform:uppercase}
.flash .q,.face.back{font-size:14.5px}
.qopt{border:0;border-bottom:1px solid var(--line);border-radius:0;background:none;padding:11px 0 11px 26px;position:relative;font-size:15.5px}
.qopt:before{content:"—";position:absolute;left:0;color:var(--muted)}
.qopt:hover{border-color:var(--accent);color:var(--accent)}
.gaplist li{background:none;border:0;border-top:1px solid var(--line);border-radius:0;padding:16px 0;margin:0}
.gaplist .w{font-size:14px}
.prog{height:2px;background:var(--line);border-radius:0}
.prog>i{border-radius:0;background:var(--accent)}
details{border:0;border-top:1px solid var(--line);border-radius:0;background:none;padding:2px 0}
summary{font:600 15px/1.6 ui-sans-serif;padding:13px 0}
summary:before{color:var(--accent)}
.turn{border-radius:2px;padding:12px 14px}
.turn.user{background:color-mix(in srgb,var(--accent) 6%,transparent);border-left:2px solid var(--accent)}
.turn.ai{background:color-mix(in srgb,var(--accent2) 8%,transparent);border-left:2px solid var(--accent2)}
.turn .who{font:700 10px/1.6 ui-sans-serif;letter-spacing:.14em}
.node{background:none;border:0;border-bottom:1px solid var(--line);border-radius:0;box-shadow:none;font:600 13px/1.6 ui-sans-serif;padding:6px 0}
.root{background:none;color:var(--accent);border-bottom:2px solid var(--accent)}
.branch{border-top:1px solid var(--line)}
.pill{border-radius:2px;font:700 10px/1 ui-sans-serif;letter-spacing:.1em;padding:6px 10px}
.foot{font:600 10px/1.8 ui-sans-serif;letter-spacing:.18em;text-transform:uppercase;color:var(--muted);border-top:1px solid var(--line);padding-top:22px;margin-top:56px}
/* 侧边目录 */
.toc{display:none}
@media(min-width:1240px){.toc{display:block;position:fixed;top:132px;left:calc(50vw + 420px);width:190px}}
.toc .toc-t{font:700 10px/1 ui-sans-serif;letter-spacing:.22em;text-transform:uppercase;color:var(--muted);padding-bottom:10px;border-bottom:1px solid var(--line);margin-bottom:8px}
.toc a{display:flex;align-items:flex-start;gap:8px;text-decoration:none;color:var(--muted);font:600 12px/1.5 ui-sans-serif;padding:7px 0 7px 12px;border-left:1px solid transparent}
.toc a span{flex:1;min-width:0}
.toc a b{font:700 10px/1.7 ui-monospace,monospace;opacity:.55}
.toc a:hover{color:var(--fg)}
.toc a.on{color:var(--accent);border-left-color:var(--accent)}
/* ===== SKIN D · 现代编辑 v2.3（最终皮肤，覆写以上两版） ===== */
:root{--bg:#faf8f3;--fg:#0f0f0f;--card:#fff;--muted:#6f6a5f;--line:#e4dfd3;--accent:#0f0f0f;--accent2:#1d4ed8;--mark:#d9f26b;--ok:#2f7d4f;--warn:#a9691a;--bad:#c0392b;--gap:#fdfbe8;--gapline:#d9f26b;--shadow:none}
html[data-theme=paper]{--bg:#faf8f3;--fg:#0f0f0f;--card:#fff;--muted:#6f6a5f;--line:#e4dfd3;--accent:#0f0f0f;--accent2:#1d4ed8;--mark:#d9f26b;--ok:#2f7d4f;--warn:#a9691a;--bad:#c0392b;--gap:#fdfbe8;--gapline:#d9f26b}
html[data-theme=ink]{--bg:#12110f;--fg:#f4efe6;--card:#1a1815;--muted:#9d9687;--line:#2c2823;--accent:#f4efe6;--accent2:#7aa2ff;--mark:#d9f26b;--ok:#6fbf8b;--warn:#e0a94a;--bad:#ef7b6a;--gap:#221f18;--gapline:#d9f26b}
html[data-theme=blue]{--bg:#eef3fb;--fg:#0c1a2e;--card:#fff;--muted:#5b6c86;--line:#c9d8ec;--accent:#0c1a2e;--accent2:#1d4ed8;--mark:#bfe2ff;--ok:#2f7d4f;--warn:#a9691a;--bad:#b3261e;--gap:#e8f1fd;--gapline:#7fb2e8}
html[data-theme=sand]{--bg:#fbf4ea;--fg:#231a11;--card:#fffdf8;--muted:#7c6a56;--line:#e9dbc6;--accent:#231a11;--accent2:#b4471f;--mark:#ffd8a6;--ok:#3f6b3f;--warn:#a9761b;--bad:#b23a2c;--gap:#fdf0dc;--gapline:#d8a13f}
body{font-family:"Microsoft YaHei","PingFang SC",system-ui,-apple-system,sans-serif;background:var(--bg);color:var(--fg);line-height:1.8;-webkit-font-smoothing:antialiased}
.kicker{background:none;border:1.5px solid var(--fg);color:var(--fg);padding:5px 10px;font:800 11px/1.4 ui-sans-serif;letter-spacing:.18em}
.masthead h1{font-family:inherit;font-weight:800;font-size:clamp(40px,6vw,66px);letter-spacing:-2.4px;line-height:1.03;margin:16px 0 8px}
.dek{font-style:normal;color:color-mix(in srgb,var(--fg) 78%,var(--bg));font-size:19px;font-weight:400;margin:0}
.hero{display:grid;grid-template-columns:1fr 228px;gap:34px;align-items:end;background:none;padding:0;color:inherit;margin:14px 0 0;padding-bottom:24px;border-bottom:2.5px solid var(--fg)}
@media(max-width:720px){.hero{grid-template-columns:1fr;align-items:start}}
.hero-r{text-align:right}
@media(max-width:720px){.hero-r{text-align:left}}
.bignum{font:800 82px/.86 ui-sans-serif;letter-spacing:-6px;font-variant-numeric:tabular-nums;color:var(--fg)}
.bigcap{font:800 11px/1.5 ui-sans-serif;letter-spacing:.14em;color:color-mix(in srgb,var(--fg) 70%,var(--bg));margin-top:10px}
@media(max-width:720px){.bignum{font-size:58px}}
.thesis{font-size:19px;line-height:1.8;margin:22px 0 0}
.thesis b,.thesis strong{background:var(--mark);padding:0 3px;font-weight:800;color:#0f0f0f}
main>.card>h2{display:block;font:800 22px/1.35 ui-sans-serif;letter-spacing:-.5px;margin:0 0 16px;color:var(--fg)}
main>.card>h2:before{display:block;font:800 11px/1 ui-sans-serif;letter-spacing:.2em;color:var(--muted);margin-bottom:9px;content:counter(sec,decimal-leading-zero)}
.card{border-top:1px solid var(--line)}
.card .tag{font:800 11px/1.5 ui-sans-serif;letter-spacing:.12em;color:color-mix(in srgb,var(--fg) 76%,var(--bg));margin:0 0 14px}
#cards .card h2{font-size:17px;font-weight:800}
.subsec .card{border-top:0;padding-top:8px}
.subsec .card h2{font-size:15px;font-weight:800}
.subsec .card>h2:before{content:none}
.math{border-top:1.5px solid var(--fg);border-bottom:1.5px solid var(--fg);font-family:Consolas,ui-monospace,monospace;font-size:1.05em;padding:16px 6px;letter-spacing:-.2px}
.math .frac{font-family:inherit}
.calc{border:1.5px solid var(--fg);margin:4px 0 6px;background:var(--card)}
.calc .setup{padding:12px 16px;font:700 12.5px/1.7 ui-sans-serif;background:color-mix(in srgb,var(--fg) 6%,var(--card));border-bottom:1px solid var(--line);color:var(--muted)}
.calc .hd{display:grid;grid-template-columns:34px 1fr 210px;gap:14px;background:var(--fg);color:var(--bg);padding:9px 16px;font:800 10.5px/1.4 ui-sans-serif;letter-spacing:.16em}
.calc .r{display:grid;grid-template-columns:34px 1fr 210px;gap:14px;padding:13px 16px;border-top:1px solid var(--line);align-items:baseline}
.calc .r .i{font:800 12px/1.6 ui-sans-serif;color:var(--muted);font-variant-numeric:tabular-nums}
.calc .r .eq{font-family:Consolas,ui-monospace,monospace;font-size:14px}
.calc .r .eq u{text-decoration:none;background:var(--mark);color:#0f0f0f;padding:1px 6px;font-weight:700}
.calc .r .why{font:400 12.5px/1.65 ui-sans-serif;color:var(--muted)}
@media(max-width:680px){.calc .hd{display:none}.calc .r{grid-template-columns:26px 1fr;gap:10px}.calc .r .why{grid-column:2}}
.readout{border-top:2px solid var(--fg);border-bottom:1px solid var(--line)}
.kpi .v{font:800 30px/1.15 ui-sans-serif;letter-spacing:-1.5px;font-variant-numeric:tabular-nums}
.kpi .k{font:800 10px/1.5 ui-sans-serif;letter-spacing:.14em}
.kpi.hi .v{background:var(--mark);color:#0f0f0f;display:inline-block;padding:0 6px;margin-left:-6px}
.zones button,.sim-btns button{border:1.5px solid var(--fg);border-radius:0;font-weight:800;letter-spacing:.06em}
.zones button.active{background:var(--fg);color:var(--bg);border-color:var(--fg)}
.look{border-left:2.5px solid var(--fg)}
.look .row b,.look .row.watch b{color:#0f0f0f;background:var(--mark);padding:1px 5px;font-weight:800}
.flow{border-left:1.5px solid var(--line)}
.fstep.active .ft{background:var(--mark);display:inline-block;padding:0 6px;color:#0f0f0f}
.qopt{border-bottom:1px solid var(--line)}
.prog>i{background:var(--fg)}
.pill{background:var(--fg);color:var(--bg)}
/* ===== v3.0 滚动叙事 / 拉幕 / 闯关 ===== */
.stage{display:grid;grid-template-columns:1.04fr .96fr;gap:36px;align-items:start;margin-top:8px}
@media(max-width:860px){.stage{grid-template-columns:1fr;gap:18px}.stage-fig{position:static}}
.stage-fig{position:sticky;top:18px;max-height:calc(100vh - 30px);overflow:auto;scrollbar-width:thin}
.stage-steps{padding-top:4px}
.scene{border-left:2px solid var(--line);padding:2px 0 26px 20px;position:relative;opacity:.4;transition:opacity .25s}
.stage-foot{display:grid;gap:10px;margin-top:18px}
.stage-foot .zones{margin:0}
.stage-foot .bars{margin:0}
.stage-fig .readout{grid-template-columns:1fr 1fr;gap:10px 20px;padding:12px 0;margin:10px 0 0}
.stage-fig .readout .kpi .v{font-size:24px}
.cmd span{flex:1;min-width:0}
.cmd span i{font-style:normal;display:inline-block;margin:0 8px;opacity:.55}
@media(max-width:860px){.scene{opacity:1}}
.scene:before{content:"";position:absolute;left:-7px;top:12px;width:10px;height:10px;border-radius:50%;background:var(--line);transition:.25s}
.scene.on{opacity:1;border-color:var(--fg);border-left-width:3px;margin-left:-1px;background:color-mix(in srgb,var(--mark) 20%,transparent)}
.scene.on:before{background:var(--fg);box-shadow:0 0 0 5px var(--mark)}
.scene .k{font:800 10px/1 ui-sans-serif;letter-spacing:.2em;color:var(--muted)}
.scene h3{font-size:18px;font-weight:800;margin:7px 0 5px;letter-spacing:-.3px}
.scene p{margin:0;font-size:14.5px;line-height:1.75;color:var(--muted)}
.cmd{display:flex;gap:10px;align-items:center;background:var(--mark);border:1.5px solid var(--fg);padding:10px 13px;font:700 12.5px/1.6 ui-sans-serif;color:#0f0f0f;margin-bottom:12px}
.cmd b{flex:0 0 auto;background:var(--fg);color:var(--bg);font:800 10px/1 ui-sans-serif;letter-spacing:.12em;padding:5px 7px}
.receipt{display:grid;grid-template-columns:1fr 1fr 1fr;border:1px solid var(--line);border-top:1.5px solid var(--fg);margin-top:12px;font:600 11.5px/1.6 ui-sans-serif}
.receipt div{padding:8px 10px;border-left:1px solid var(--line);color:var(--muted)}
.receipt div:first-child{border-left:0;background:color-mix(in srgb,var(--mark) 40%,transparent);color:var(--fg)}
.receipt b{color:var(--fg);font-variant-numeric:tabular-nums}
@media(max-width:680px){.receipt{grid-template-columns:1fr}.receipt div{border-left:0;border-top:1px solid var(--line)}.receipt div:first-child{border-top:0}}
.compare{position:relative;border:1.5px solid var(--fg);display:grid;grid-template-columns:var(--split,50%) 1fr;min-height:270px;overflow:hidden;user-select:none}
.cmp-side{padding:26px 28px;min-width:0}
.cmp-left{background:color-mix(in srgb,var(--fg) 5%,var(--card))}
.cmp-side .lab{font:800 10px/1 ui-sans-serif;letter-spacing:.16em;color:var(--muted)}
.cmp-num{font:800 54px/.95 ui-sans-serif;letter-spacing:-4px;margin:10px 0 8px;font-variant-numeric:tabular-nums}
.cmp-left .cmp-num{color:color-mix(in srgb,var(--fg) 55%,transparent)}
.cmp-right .cmp-num{background:var(--mark);color:#0f0f0f;display:inline-block;padding:0 8px;margin-left:-8px}
.cmp-side p{margin:0;font-size:14px;line-height:1.75;color:var(--muted);max-width:24em}
.cmp-div{position:absolute;top:-8px;bottom:-8px;left:var(--split,50%);width:2px;background:var(--fg);cursor:ew-resize;touch-action:none}
.cmp-div b{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);width:44px;height:44px;border-radius:50%;background:var(--fg);color:var(--bg);display:grid;place-items:center;font:800 14px/1 ui-sans-serif}
.wz-prog{display:flex;gap:6px;margin-bottom:20px}
.wz-prog i{flex:1;height:6px;background:var(--line)}
.wz-prog i.on{background:var(--fg)}
.wz-prog i.done{background:var(--mark)}
.wz-qn{font:800 10px/1 ui-sans-serif;letter-spacing:.2em;color:var(--muted);margin-bottom:10px}
.wz-q{font:800 19px/1.6 ui-sans-serif;margin:0 0 16px;letter-spacing:-.3px}
.wz-opt{display:flex;gap:12px;align-items:flex-start;width:100%;text-align:left;border:1.5px solid var(--line);background:var(--card);padding:12px 15px;margin:8px 0;font:400 14.5px/1.65 inherit;color:inherit;cursor:pointer}
.wz-opt b{font:800 11px/1.8 ui-sans-serif;color:var(--muted)}
.wz-opt:hover{border-color:var(--fg)}
.wz-opt.sel{border-color:var(--fg);background:var(--mark);color:#0f0f0f}
.wz-opt.wrong{border-color:var(--bad);background:color-mix(in srgb,var(--bad) 12%,var(--card))}
.wz-fb{margin-top:14px;border-top:1.5px solid var(--fg);padding-top:12px;font-size:14px;line-height:1.75}
.wz-fb b{color:var(--accent2)}
.wz-bar{display:flex;justify-content:space-between;align-items:center;margin-top:18px;gap:12px}
.wz-bar .sc{font:800 11px/1.6 ui-sans-serif;letter-spacing:.1em;color:var(--muted)}
.wz-next{background:var(--fg);color:var(--bg);border:1.5px solid var(--fg);font:800 12.5px/1 ui-sans-serif;letter-spacing:.08em;padding:11px 20px;cursor:pointer}
.wz-next:disabled{opacity:.35;cursor:not-allowed}
/* ===== v3.1 宽版布局 · 无横拉 · 四主题 ===== */
*{min-width:0}
.shell{display:flex;justify-content:center;align-items:flex-start;gap:34px;max-width:1520px;margin:0 auto;padding:0 24px}
.paper{flex:1 1 auto;min-width:0;max-width:1040px;padding:46px 6px 72px;overflow:visible}
@media(max-width:760px){.paper{padding:30px 18px 56px}}
.card p,.card li,.scene p,.wz-q,.depth p{max-width:46em}
.dek{max-width:34em}
.thesis{max-width:42em}
.topbar{display:flex;justify-content:space-between;align-items:center;gap:18px;flex-wrap:wrap;margin-bottom:6px}
.themes{display:flex;gap:9px;align-items:center}
.themes button{width:24px;height:24px;padding:0;border-radius:50%;border:1.5px solid var(--line);cursor:pointer;transition:.15s}
.themes button:hover{transform:scale(1.12)}
.themes button.on{border-color:var(--fg);box-shadow:0 0 0 3px color-mix(in srgb,var(--mark) 65%,transparent)}
.toc-top{display:flex;flex-wrap:wrap;gap:5px;align-items:center;position:sticky;top:0;z-index:9;padding:9px 0;margin:20px 0 0;background:var(--bg);box-shadow:0 1px 0 var(--line)}
.toc-top .toc-t{display:none}
.toc-side{display:none}
.toc a{display:inline-flex;gap:5px;align-items:center;font:700 11.5px/1 ui-sans-serif;letter-spacing:.03em;color:color-mix(in srgb,var(--fg) 86%,var(--bg));border:1px solid color-mix(in srgb,var(--fg) 26%,var(--bg));padding:5px 9px;text-decoration:none;white-space:nowrap}
.toc a b{font:700 10px/1 ui-monospace,monospace;color:inherit;opacity:.75}
.toc a:hover{color:var(--fg);border-color:var(--fg)}
.toc a.on{background:var(--mark);color:#0f0f0f;border-color:var(--fg)}
.toc a.on b{opacity:1;color:#0f0f0f}
@media(min-width:1400px){
 .toc-top{display:none}
 .toc-side{display:block;position:sticky;top:34px;flex:0 0 178px;width:178px;padding-top:6px}
 .toc-side .toc-t{display:block;font:800 10px/1 ui-sans-serif;letter-spacing:.2em;color:var(--muted);margin-bottom:10px;text-transform:uppercase}
 .toc-side a{display:flex;width:100%;border:0;border-left:1px solid var(--line);padding:6px 0 6px 12px;background:none;white-space:normal;font-size:12.5px;line-height:1.5;justify-content:flex-start}
 .toc-side a:hover{color:var(--fg);border-left-color:var(--fg)}
 .toc-side a.on{background:none;color:var(--accent);border-left:2px solid var(--accent);padding-left:13px}
 .toc-side a.on b{color:var(--accent)}
}
.math{overflow:visible;white-space:normal}
.math .frac{max-width:100%}
.frac>span{word-break:break-word}
.calc .r .eq{overflow-wrap:anywhere}
@media(max-width:700px){.compare{grid-template-columns:1fr!important}.cmp-div{display:none}.cmp-left{border-bottom:1.5px solid var(--fg)}.cmp-num{font-size:42px}.stage{grid-template-columns:1fr;gap:16px}}
@media(max-width:520px){.readout{gap:16px}.kpi .v{font-size:23px}.bignum{font-size:48px}}
</style>
</head>
<body>
<div class="shell">
<main id="top" class="paper">
<header class="masthead">
<div class="topbar"><span class="kicker">费曼学习报告</span><div class="themes" id="themes"></div></div>
<div class="hero">
<div>
<h1 id="title">{{CONCEPT}}</h1>
<p class="dek" id="subtitle"></p>
</div>
<div class="hero-r">
<div class="bignum" id="bigNum"></div>
<div class="bigcap" id="bigCap"></div>
</div>
</div>
<p class="thesis" id="oneLiner"></p>
</header>
<nav class="toc toc-top" id="tocTop"></nav>

<div class="card">
<h2><span class="ic">🎚️</span>讲解深度滑块 · 同一个概念，三种讲法</h2>
<span class="tag">左右拖动，看同一件事怎样从"给孩子讲"逐层还原成"给同行讲"</span>
<div class="depth-head"><input type="range" id="depth" min="0" max="2" step="1" value="0" aria-label="讲解深度"></div>
<div class="depth-lv"><span>🧒 6 岁版</span><span>💡 本质版</span><span>🎓 同行版</span></div>
<div id="depthText"></div>
</div>

<section class="subsec" id="sec-cards">
<h2>渐进卡片</h2>
<div id="cards"></div>
</section>

<section class="card" id="sec-ladder">
<h2>把公式算一遍</h2>
<span class="tag">每一步回答两件事：先算什么、它在整条推理里充当什么</span>
<div class="calc" id="ladder"></div>
</section>

<div class="card" id="sec-terms">
<h2><span class="ic">📖</span>术语速查 · 卡住就点开</h2>
<span class="tag">每个词一句话人话解释，不用回头翻</span>
<div class="terms" id="terms"></div>
</div>

<section class="card" id="sec-sim">
<h2>跟着走一遍</h2>
<span class="tag">滚动右侧四步，左边人群图会跟着换状态；最后一步你自己拖</span>
<div class="stage">
<div class="stage-fig">
<div class="cmd" id="look"></div>
<canvas id="sim" width="800" height="270"></canvas>
<div class="legend" id="legend"></div>
<div class="sim-controls" id="sliders"></div>
<div class="sim-btns" id="simBtns">
<button id="zoomBtn" class="ghost">🔍 只看关键结果</button>
<button id="resetBtn" class="ghost">重置 ↺</button>
</div>
<div class="readout" id="readout"></div>
<div class="receipt" id="receipt"></div>
</div>
<div class="stage-steps" id="scenes"></div>
</div>
<div class="stage-foot">
<div class="zones" id="presets"></div>
<div class="bars" id="bars"></div>
<div class="math" id="subst"></div>
<div class="sim-teach" id="teach"></div>
</div>
<p class="hint" id="simIntro"></p>
</section>

<section class="card" id="sec-compare">
<h2>直觉 vs 计算</h2>
<span class="tag">拖中间的手柄，左右比一比</span>
<div class="compare" id="compare"></div>
<p class="hint" id="compareNote"></p>
</section>

<div class="card">
<h2><span class="ic">🔗</span>因果链 · 点每个节点看"为什么"</h2>
<span class="tag">逻辑与因果用流程图 + 公式，而不是大段文字</span>
<div class="flow" id="flow"></div>
<div class="flow-detail" id="flowDetail"></div>
<p class="hint">提示：链条中间那一步最容易被跳过，也正是"反直觉"的来源。改上方滑块时，链条的结果会跟着变。</p>
</div>

<section class="subsec" id="sec-map">
<h2>自评与地图</h2>
<div class="grid2">
<div class="card"><h2><span class="ic">📊</span>五维能力雷达</h2><div id="radar"></div></div>
<div class="card"><h2><span class="ic">🗺️</span>概念地图</h2><div class="map" id="map"></div></div>
</div>
</section>

<div class="card" id="sec-memory">
<h2><span class="ic">🃏</span>盲点闪卡 · 翻转即答案</h2>
<span class="tag">点卡片翻面。能不看答案讲出来，才算真懂</span>
<div class="flash-wrap" id="flash"></div>
</div>

<section class="card" id="sec-quiz">
<h2>三道题，检验是否真懂</h2>
<span class="tag">答错不扣分，当场解释</span>
<div id="quiz"></div>
</section>

<div class="card"><h2><span class="ic">⚠️</span>我的盲点清单 · 复习进度</h2>
<div class="prog"><i id="progbar"></i></div><p id="progtxt" class="hint"></p>
<ul class="gaplist" id="gaps"></ul></div>

<div class="card" id="sec-rounds"><h2><span class="ic">🎬</span>学习过程回放</h2><div id="rounds"></div></div>
<p class="foot" id="foot"></p>
</main>
<aside class="toc toc-side" id="tocSide"></aside>
</div>
<script>
const D={{DATA_JSON}};
/* ===== 工具 ===== */
const $=id=>document.getElementById(id);
const pct=(v,d)=>(v*100).toFixed(d)+'%';
const fmtV=(v,f)=>f==='pct2'?pct(v,2):(f==='pct1'?pct(v,1):v);
/* ===== 主题切换 ===== */
const THEMES=[{id:'paper',name:'纸白',c:'#faf8f3'},{id:'ink',name:'墨夜',c:'#12110f'},{id:'blue',name:'蓝图',c:'#c9d8ec'},{id:'sand',name:'暖砂',c:'#ffd8a6'}];
(function(){
 let cur='paper';try{cur=localStorage.getItem('fh-theme')||'paper';}catch(e){}
 if(!THEMES.some(t=>t.id===cur))cur='paper';
 document.documentElement.dataset.theme=cur;
 const box=$('themes');
 box.innerHTML=THEMES.map(t=>'<button data-t="'+t.id+'" title="'+t.name+'" aria-label="'+t.name+'" style="background:'+t.c+'"'+(t.id===cur?' class="on"':'')+'></button>').join('');
 box.querySelectorAll('button').forEach(b=>b.onclick=()=>{
  const id=b.dataset.t;document.documentElement.dataset.theme=id;
  try{localStorage.setItem('fh-theme',id);}catch(e){}
  box.querySelectorAll('button').forEach(x=>x.classList.toggle('on',x===b));
  if(window.__redraw)window.__redraw();});
})();
$('title').textContent=D.concept;
$('subtitle').textContent=D.subtitle||'';
$('oneLiner').textContent=(D.oneLiner||'');
if(D.heroNum){$('bigNum').innerHTML=D.heroNum;$('bigCap').innerHTML=D.heroCap||'';}
else{$('bigNum').parentNode.style.display='none';}
$('foot').textContent='生成于 '+D.date+' · 由 cs-feynman-html 输出 · 用"教"来"学"';
$('simIntro').innerHTML=D.sim.intro||'';
/* ===== 深度滑块 ===== */
(function(){const el=$('depth'),tx=$('depthText');
 function render(){const it=D.depth[+el.value];if(!it)return;
  tx.innerHTML='<div style="font:700 10px/1.6 ui-sans-serif;letter-spacing:.14em;text-transform:uppercase;color:var(--muted);margin-bottom:8px">'+it.label+'</div>'+it.html;}
 el.oninput=render;render();})();
/* ===== 侧边目录（渲染完所有卡片后再建） ===== */
function buildToc(){
 const cards=[...document.querySelectorAll('main > .card, main > .subsec')];
 const items=cards.map((el,i)=>{if(!el.id)el.id='sec-'+i;
  const h=el.querySelector('h2');let t=h?h.textContent.trim():'';
  t=t.replace(/^[^\u4e00-\u9fa5A-Za-z]+/,'').split(' · ')[0];return {id:el.id,t:t};});
 const html='<div class="toc-t">目录</div>'+items.map((x,i)=>
  '<a href="#'+x.id+'"><b>'+(i+1<10?'0':'')+(i+1)+'</b><span>'+x.t+'</span></a>').join('');
 const boxes=[$('tocTop'),$('tocSide')].filter(Boolean);
 boxes.forEach(b=>b.innerHTML=html);
 const lists=boxes.map(b=>[...b.querySelectorAll('a')]);
 function markActive(){
  let cur=cards[0];
  cards.forEach(c=>{if(c.getBoundingClientRect().top<=150)cur=c;});
  const href='#'+cur.id;
  lists.forEach(ls=>ls.forEach(a=>a.classList.toggle('on',a.getAttribute('href')===href)));
 }
 window.addEventListener('scroll',markActive,{passive:true});
 window.addEventListener('resize',markActive);
 markActive();
}
/* ===== 卡片（lead 显正文 / more 折叠） ===== */
(function(){const box=$('cards');
 D.cards.forEach(c=>{const d=document.createElement('div');d.className='card';
  const body=c.lead||c.content||'';
  d.innerHTML='<h2><span class="ic">'+c.icon+'</span>'+c.title+'</h2><span class="tag">'+c.tag+'</span>'+body+
   (c.more?'<details class="fold"><summary>展开推导</summary>'+c.more+'</details>':'');
  box.appendChild(d);});})();
/* ===== 计算阶梯 ===== */
(function(){const L=D.ladder;
 if(!L||!L.steps||!L.steps.length){$('sec-ladder').style.display='none';return;}
 let h=L.setup?'<div class="setup">'+L.setup+'</div>':'';
 h+='<div class="hd"><span>#</span><span>算式</span><span>这一步在做什么</span></div>';
 L.steps.forEach((s,i)=>{h+='<div class="r"><span class="i">'+(i+1)+'</span><span class="eq">'+s.eq+' = <u>'+s.res+'</u></span><span class="why">'+(s.why||'')+'</span></div>';});
 $('ladder').innerHTML=h;})();
/* ===== 术语速查 ===== */
(function(){const ts=D.terms||[];if(!ts.length){$('sec-terms').style.display='none';return;}
 $('terms').innerHTML=ts.map(t=>'<details><summary>'+t.t+'</summary><div class="td">'+t.d+'</div></details>').join('');})();
/* ===== 指令条（交互语义·轻） ===== */
(function(){const L=D.sim.look;if(!L)return;
 $('look').innerHTML='<b>现在做</b><span>'+(L.do||'')+'<i>→</i>盯住 '+(L.watch||'')+'<i>→</i>它应该'+(L.expect||'')+'</span>';})();
/* ===== 滚动叙事场景 ===== */
function initScenes(){
 const S=D.scenes||[];
 if(!S.length){$('scenes').innerHTML='';return;}
 $('scenes').innerHTML=S.map((s,i)=>'<div class="scene'+(i===0?' on':'')+'" data-i="'+i+'">'+
  '<div class="k">'+(i+1)+' / '+S.length+'</div><h3>'+s.t+'</h3><p>'+(s.p||'')+'</p></div>').join('');
 const items=[...$('scenes').querySelectorAll('.scene')];
 if(!('IntersectionObserver' in window))return;
 const io=new IntersectionObserver(es=>{es.forEach(e=>{if(!e.isIntersecting)return;
  items.forEach(x=>x.classList.remove('on'));e.target.classList.add('on');
  const sc=S[+e.target.dataset.i];
  if(sc&&sc.v&&window.__apply)window.__apply(sc.v,sc.zoom);});},
  {rootMargin:'-32% 0px -55% 0px'});
 items.forEach(x=>io.observe(x));
}
/* ===== 拉幕对比 ===== */
function initCompare(){
 const C=D.compare;if(!C){$('sec-compare').style.display='none';return;}
 $('compare').innerHTML='<div class="cmp-side cmp-left"><span class="lab">'+C.leftLabel+'</span><div class="cmp-num">'+C.leftNum+'</div><p>'+C.leftText+'</p></div>'+
  '<div class="cmp-side cmp-right"><span class="lab">'+C.rightLabel+'</span><div class="cmp-num">'+C.rightNum+'</div><p>'+C.rightText+'</p></div>'+
  '<div class="cmp-div" id="cmpDiv"><b>↔</b></div>';
 $('compareNote').innerHTML=C.note||'';
 const box=$('compare'),dv=$('cmpDiv');let split=50,on=false;
 const set=p=>{split=Math.max(18,Math.min(82,p));box.style.setProperty('--split',split+'%');};
 const fromX=x=>{const r=box.getBoundingClientRect();set((x-r.left)/r.width*100);};
 dv.addEventListener('pointerdown',e=>{on=true;try{dv.setPointerCapture(e.pointerId);}catch(_){}});
 dv.addEventListener('pointermove',e=>{if(on){e.preventDefault();fromX(e.clientX);}});
 dv.addEventListener('pointerup',()=>{on=false;});
 dv.addEventListener('click',()=>set(split>50?32:68));
}
/* ===== 雷达 ===== */
(function(){const K=['完整性','准确性','深度','关联性','表达力'],cx=150,cy=130,R=92,n=K.length;
 const ang=i=>-Math.PI/2+i*2*Math.PI/n,pt=(i,r)=>[cx+Math.cos(ang(i))*R*r,cy+Math.sin(ang(i))*R*r];
 let g='';[.25,.5,.75,1].forEach(f=>{g+='<polygon points="'+K.map((_,i)=>pt(i,f).join(',')).join(' ')+'" fill="none" stroke="var(--line)"/>';});
 const ax=K.map((_,i)=>'<line x1="'+cx+'" y1="'+cy+'" x2="'+pt(i,1)[0]+'" y2="'+pt(i,1)[1]+'" stroke="var(--line)"/>').join('');
 const poly=K.map((k,i)=>pt(i,((D.scores&&D.scores[k])||0)/5).join(',')).join(' ');
 const dots=K.map((k,i)=>{const p=pt(i,((D.scores&&D.scores[k])||0)/5);return '<circle cx="'+p[0]+'" cy="'+p[1]+'" r="3" fill="var(--accent)"/>';}).join('');
 const lb=K.map((k,i)=>{const p=pt(i,1.2);return '<text x="'+p[0]+'" y="'+p[1]+'" font-size="12" fill="var(--muted)" text-anchor="middle">'+k+' '+((D.scores&&D.scores[k])||0)+'</text>';}).join('');
 $('radar').innerHTML='<svg viewBox="0 0 300 256" width="100%">'+g+ax+'<polygon points="'+poly+'" fill="color-mix(in srgb,var(--accent) 40%,transparent)" stroke="var(--accent)" stroke-width="2"/>'+dots+lb+'</svg>';})();
/* ===== 概念地图 ===== */
(function(){function nd(n,root){let h='<div class="node'+(root?' root':'')+'">'+n.label+'</div>';
 if(n.children&&n.children.length){h+='<div class="branch">'+n.children.map(c=>'<div class="sub">'+nd(c,false)+'</div>').join('')+'</div>';}return h;}
 $('map').innerHTML=nd(D.map,true);})();
/* ===== 盲点清单 ===== */
(function(){const KEY='feynman:'+D.concept;let saved={};try{saved=JSON.parse(localStorage.getItem(KEY)||'{}')}catch(e){}
 const gl=$('gaps');const isDone=i=>saved[i]!==undefined?saved[i]:!!D.gaps[i].resolved;
 D.gaps.forEach((g,i)=>{const li=document.createElement('li');li.className=isDone(i)?'done':'';
  li.innerHTML='<input type="checkbox" '+(isDone(i)?'checked':'')+'><div><div class="q">'+g.question+'</div><div class="w">'+(g.why||'')+'</div></div>';
  li.querySelector('input').onchange=e=>{saved[i]=e.target.checked;li.classList.toggle('done',e.target.checked);try{localStorage.setItem(KEY,JSON.stringify(saved))}catch(err){};prog();};
  gl.appendChild(li);});
 function prog(){const n=D.gaps.length;let c=0;D.gaps.forEach((g,i)=>{if(isDone(i))c++;});
  $('progbar').style.width=(n?c/n*100:0)+'%';$('progtxt').textContent='已补齐 '+c+' / '+n+' 个盲点';}
 prog();})();
/* ===== 闪卡 ===== */
D.gaps.forEach(g=>{const el=document.createElement('div');el.className='flash';
 el.innerHTML='<div class="flash-in"><div class="face front"><div class="lbl">⚠️ 盲点 · 点击翻面</div><div class="q">'+g.question+'</div></div>'+
  '<div class="face back"><div class="lbl">✅ 答案</div><div>'+g.answer+'</div></div></div>';
 el.onclick=()=>el.classList.toggle('flip');$('flash').appendChild(el);});
/* ===== 闯关自测 ===== */
(function(){const box=$('quiz'),Q=D.quiz||[];
 if(!Q.length){$('sec-quiz').style.display='none';return;}
 let i=0,score=0,locked=false;const L='ABCD';
 function render(){
  const q=Q[i];
  box.innerHTML='<div class="wz-prog">'+Q.map((_,k)=>'<i class="'+(k<i?'done':k===i?'on':'')+'"></i>').join('')+'</div>'+
   '<div class="wz-qn">第 '+(i+1)+' 题 / 共 '+Q.length+' 题</div>'+
   '<p class="wz-q">'+q.q+'</p>'+
   q.opts.map((o,oi)=>'<button class="wz-opt" data-o="'+oi+'"><b>'+L[oi]+'</b><span>'+o+'</span></button>').join('')+
   '<div class="wz-fb" id="fb" style="display:none"></div>'+
   '<div class="wz-bar"><span class="sc">已答对 '+score+' / '+Q.length+'</span><button class="wz-next" id="nx" disabled>下一题 →</button></div>';
  locked=false;
  box.querySelectorAll('.wz-opt').forEach(b=>b.onclick=()=>{
   if(locked)return;locked=true;
   const oi=+b.dataset.o,ok=oi===q.a;if(ok)score++;
   box.querySelectorAll('.wz-opt').forEach(x=>{const k=+x.dataset.o;
    if(k===q.a)x.classList.add('sel');else if(k===oi)x.classList.add('wrong');x.disabled=true;});
   const fb=$('fb');fb.style.display='block';
   fb.innerHTML='<b>'+(ok?'答对':'答案是 '+L[q.a])+'</b>　'+(q.why||'');
   const nx=$('nx');nx.disabled=false;nx.textContent=(i<Q.length-1?'下一题 →':'看结果 →');
   box.querySelector('.sc').textContent='已答对 '+score+' / '+Q.length;});
  $('nx').onclick=()=>{if(i<Q.length-1){i++;render();}else{finish();}};
 }
 function finish(){
  const all=score===Q.length;
  box.innerHTML='<div class="wz-prog">'+Q.map(()=>'<i class="done"></i>').join('')+'</div>'+
   '<p class="wz-q">得分 '+score+' / '+Q.length+'</p>'+
   '<div class="wz-fb" style="display:block">'+(all?'全对。可以回到「盲点清单」把这几条勾掉了。':'错了哪题，就回到对应小节再看一遍——错的地方，就是你还没讲通的地方。')+'</div>'+
   '<div class="wz-bar"><span class="sc">'+(all?'已掌握':'继续练')+'</span><button class="wz-next" id="nx2">重来一遍 ↺</button></div>';
  $('nx2').onclick=()=>{i=0;score=0;render();};
 }
 render();
})();
/* ===== 因果链 ===== */
(function(){const fl=$('flow'),fd=$('flowDetail');
 D.chain.forEach((c,i)=>{const s=document.createElement('div');s.className='fstep'+(i===0?' active':'');s.dataset.i=i;
  s.innerHTML='<div class="fn">步骤 '+(i+1)+'</div><div class="ft">'+c.t+'</div><div class="ff">'+c.f+'</div>';
  s.onclick=()=>sel(i);fl.appendChild(s);
  if(i<D.chain.length-1){const a=document.createElement('div');a.className='farrow';a.textContent='→';fl.appendChild(a);}});
 function sel(i){fl.querySelectorAll('.fstep').forEach(e=>e.classList.toggle('active',+e.dataset.i===i));
  const c=D.chain[i];fd.innerHTML='<div class="fd-t">步骤 '+(i+1)+' · '+c.t+'</div><div class="math">'+c.f+'</div><div>'+c.r+'</div>';}
 sel(0);window.__selChain=sel;})();
/* ===== 回放 ===== */
D.rounds.forEach((r,i)=>{const de=document.createElement('details');if(i===0)de.open=true;
 de.innerHTML='<summary>'+r.label+'</summary>'+(r.userText?'<div class="turn user"><div class="who">我</div>'+r.userText+'</div>':'')+(r.aiText?'<div class="turn ai"><div class="who">教练 / 新手</div>'+r.aiText+'</div>':'');
 $('rounds').appendChild(de);});
/* ===================== 模块 M-A：比例 / 点阵 ===================== */
function initProportion(){
 const S={};D.sim.sliders.forEach(s=>S[s.id]=s.value);
 const N=D.sim.total,cv=$('sim'),ctx=cv.getContext('2d');
 let zoom=false,base=null;
 D.sim.sliders.forEach(s=>{const lb=document.createElement('label');
  lb.innerHTML=s.label+'<input type="range" id="sl_'+s.id+'" min="'+s.min+'" max="'+s.max+'" step="'+s.step+'" value="'+s.value+'"><output id="out_'+s.id+'">'+fmtV(s.value,s.fmt)+'</output>';
  $('sliders').appendChild(lb);
  lb.querySelector('input').oninput=e=>{S[s.id]=+e.target.value;$('out_'+s.id).textContent=fmtV(S[s.id],s.fmt);update();};});
 (D.sim.presets||[]).forEach((p,i)=>{const b=document.createElement('button');b.textContent=p.name;
  if(i===(D.sim.activePreset||0))b.classList.add('active');
  b.onclick=()=>{[...$('presets').children].forEach(o=>o.classList.remove('active'));b.classList.add('active');
   Object.keys(p.v).forEach(k=>{S[k]=p.v[k];const sl=$('sl_'+k);if(sl){sl.value=p.v[k];const def=D.sim.sliders.find(x=>x.id===k);if(def)$('out_'+k).textContent=fmtV(S[k],def.fmt);}});update();};
  $('presets').appendChild(b);});
 $('zoomBtn').onclick=function(){zoom=!zoom;this.classList.toggle('ghost');this.textContent=zoom?'🔎 '+((D.sim.zoomOff)||'显示全部'):((D.sim.zoomOn)||'🔍 只看关键结果');update();};
 $('resetBtn').onclick=()=>{D.sim.sliders.forEach(s=>{S[s.id]=s.value;const sl=$('sl_'+s.id);if(sl){sl.value=s.value;$('out_'+s.id).textContent=fmtV(s.value,s.fmt);}});zoom=false;$('zoomBtn').classList.add('ghost');$('zoomBtn').textContent=(D.sim.zoomOn)||'🔍 只看关键结果';update();};
 function calc(){const a=D.sim.calc;const sick=N*S[a.prior],healthy=N-sick;
  const tp=sick*S[a.tp],fn=sick-tp,fp=healthy*(1-S[a.tn]),tn=healthy-fp;
  return {sick,healthy,tp,fn,fp,tn,post:tp/(tp+fp),pos:tp+fp};}
 function drawPop(){const c=calc(),W=cv.width,H=cv.height,pad=18,cols=50,rows=Math.ceil(N/cols);
  const cw=(W-2*pad)/cols,ch=(H-2*pad)/rows,r=Math.min(cw,ch)*.34;
  const cs=getComputedStyle(document.documentElement);
  const C={tp:cs.getPropertyValue('--bad').trim(),fp:cs.getPropertyValue('--warn').trim(),
           fn:cs.getPropertyValue('--accent2').trim(),tn:cs.getPropertyValue('--muted').trim()};
  ctx.clearRect(0,0,W,H);
  const kinds=new Array(N).fill('tn');let idx=0;
  const nTp=Math.round(c.tp),nFn=Math.round(c.fn),nFp=Math.round(c.fp);
  for(let i=0;i<nTp&&idx<N;i++)kinds[idx++]='tp';
  for(let i=0;i<nFn&&idx<N;i++)kinds[idx++]='fn';
  for(let i=0;i<nFp&&idx<N;i++)kinds[idx++]='fp';
  for(let i=N-1;i>0;i--){const j=Math.floor(((i*9301+49297)%233280)/233280*(i+1));const t=kinds[i];kinds[i]=kinds[j];kinds[j]=t;}
  for(let i=0;i<N;i++){const cx=pad+(i%cols)*cw+cw/2,cy=pad+Math.floor(i/cols)*ch+ch/2,k=kinds[i];
   const show=zoom?(k==='tp'||k==='fp'):true;ctx.globalAlpha=show?1:.12;
   ctx.beginPath();
   if(k==='tn'){ctx.globalAlpha=show?.28:.07;ctx.fillStyle=C.tn;ctx.arc(cx,cy,r*.75,0,7);ctx.fill();ctx.globalAlpha=show?1:.12;}
   else{ctx.fillStyle=C[k];ctx.arc(cx,cy,r,0,7);ctx.fill();}}
  ctx.globalAlpha=1;ctx.fillStyle=cs.getPropertyValue('--muted').trim();ctx.font='13px sans-serif';
  ctx.fillText('每格 1 人 · 共 '+N+' 人',pad,H-4);}
 function update(){const c=calc();
  drawPop();
  $('legend').innerHTML='<span><i style="background:var(--bad)"></i>真阳 '+c.tp.toFixed(1)+' 人</span>'+
   '<span><i style="background:var(--accent2)"></i>假阴 '+c.fn.toFixed(1)+' 人</span>'+
   '<span><i style="background:var(--warn)"></i>假阳 '+c.fp.toFixed(1)+' 人</span>'+
   '<span><i style="background:var(--muted);opacity:.4"></i>真阴 '+c.tn.toFixed(0)+' 人</span>';
  const R=D.sim.readout||{main:'关键结果',a:'A',b:'B',c:'C'};
  $('readout').innerHTML='<div class="kpi hi"><div class="k">'+R.main+'</div><div class="v">'+pct(c.post,1)+'</div></div>'+
   '<div class="kpi"><div class="k">'+R.a+'</div><div class="v">'+c.tp.toFixed(1)+'</div></div>'+
   '<div class="kpi"><div class="k">'+R.b+'</div><div class="v">'+c.fp.toFixed(1)+'</div></div>'+
   '<div class="kpi"><div class="k">'+R.c+'</div><div class="v">'+c.pos.toFixed(1)+'</div></div>';
  const na=D.sim.sliders.find(s=>s.id===D.sim.calc.tp).id,nb=D.sim.sliders.find(s=>s.id===D.sim.calc.tn).id;
  const nav=D.sim.sliders.find(s=>s.id===D.sim.calc.prior).id;
  $('bars').innerHTML='<div class="bar"><span class="nm">'+(D.sim.barA||'直觉以为')+'</span><span class="tr"><span class="fl" style="width:'+(S[na]*100)+'%;background:var(--muted)"></span></span><span class="pc">'+pct(S[na],0)+'</span></div>'+
   '<div class="bar"><span class="nm">'+(D.sim.barB||'公式算出')+'</span><span class="tr"><span class="fl" style="width:'+Math.max(c.post*100,1.5)+'%;background:linear-gradient(90deg,var(--accent),var(--accent2))"></span></span><span class="pc">'+pct(c.post,1)+'</span></div>'+
   '<p class="hint">同一条证据，两种算法相差 <b>'+(S[na]/Math.max(c.post,1e-9)).toFixed(1)+' 倍</b>；相对起点提升了 <b>'+(c.post/S[nav]).toFixed(1)+' 倍</b>。</p>';
  $('subst').innerHTML=typeof D.sim.formulaHTML==='function'?D.sim.formulaHTML(c,S,pct):(D.sim.formulaHTML||'');
  $('teach').innerHTML=typeof D.sim.teach==='function'?D.sim.teach(c,S,pct):(D.sim.teach||'');
  const rc=$('receipt');
  if(rc){
   if(!base)base={prev:S.prev,post:c.post,fp:c.fp};
   if(Math.abs(S.prev-base.prev)>1e-9){
    rc.innerHTML='<div>患病率 '+pct(base.prev,2)+' → <b>'+pct(S.prev,2)+'</b></div>'+
     '<div>后验 '+pct(base.post,1)+' → <b>'+pct(c.post,1)+'</b></div>'+
     '<div>假阳 '+base.fp.toFixed(1)+' → <b>'+c.fp.toFixed(1)+'</b> 人</div>';
   }else{
    rc.innerHTML='<div>当前：患病率 '+pct(S.prev,2)+'</div><div>后验 <b>'+pct(c.post,1)+'</b></div><div>假阳 <b>'+c.fp.toFixed(1)+'</b> 人</div>';
   }
  }
  if(window.__selChain)window.__selChain(D.sim.highlight!=null?D.sim.highlight:0);}
 window.__apply=function(v,zoomOn){
  Object.keys(v).forEach(k=>{S[k]=v[k];const sl=$('sl_'+k);
   const def=D.sim.sliders.find(x=>x.id===k);
   if(sl&&def){sl.value=v[k];$('out_'+k).textContent=fmtV(v[k],def.fmt);}});
  if(zoomOn!==undefined&&zoomOn!==zoom){zoom=!!zoomOn;$('zoomBtn').classList.toggle('ghost',!zoom);
   $('zoomBtn').textContent=zoom?'🔎 '+((D.sim.zoomOff)||'显示全部'):((D.sim.zoomOn)||'🔍 只看关键结果');}
  update();};
 window.__redraw=update;update();
}
/* ===================== 模块 M-B：曲线 / 迭代 ===================== */
function initStep(){
 const cv=$('sim'),ctx=cv.getContext('2d');
 $('zoomBtn').style.display='none';$('legend').style.display='none';$('bars').style.display='none';
 const C=D.sim.curves;let cur=C[0],x=cur.start,trail=[],prev=null,play=null;
 const S={eta:D.sim.eta0||.15,noise:0,x0:cur.start};
 const fn=e=>new Function('x','return '+e);
 const f=fn(cur.f),df=fn(cur.df);
 /* 曲线切换 */
 C.forEach((c,i)=>{const b=document.createElement('button');b.textContent=(i+1)+'. '+c.name;
  if(i===0)b.classList.add('active');
  b.onclick=()=>{[...$('presets').children].forEach(o=>o.classList.remove('active'));b.classList.add('active');
   cur=c;f2=fn(c.f);df2=fn(c.df);S.x0=c.start;inputs.x0.min=c.domain[0];inputs.x0.max=c.domain[1];inputs.x0.value=c.start;
   $('so_x0').textContent=(+c.start).toFixed(2);reset();};
  $('presets').appendChild(b);});
 let f2=f,df2=df;
 /* 滑块 */
 const inputs={};
 [{id:'eta',label:D.sim.etaLabel||'步长 η',min:0,max:D.sim.etaMax||3,step:.01,v:S.eta},
  {id:'x0',label:D.sim.x0Label||'起点',min:cur.domain[0],max:cur.domain[1],step:.05,v:cur.start},
  {id:'noise',label:D.sim.noiseLabel||'随机扰动 σ',min:0,max:1.5,step:.05,v:0}].forEach(d=>{
  const lb=document.createElement('label');
  lb.innerHTML=d.label+'<input type="range" id="st_'+d.id+'" min="'+d.min+'" max="'+d.max+'" step="'+d.step+'" value="'+d.v+'"><output id="so_'+d.id+'">'+(+d.v).toFixed(2)+'</output>';
  $('sliders').appendChild(lb);const inp=lb.querySelector('input');inputs[d.id]=inp;
  inp.oninput=()=>{S[d.id]=+inp.value;$('so_'+d.id).textContent=(+inp.value).toFixed(2);
   if(d.id==='x0'){x=S.x0;trail=[];prev=null;}$('teach').innerHTML=teach();update();};});
 $('resetBtn').onclick=()=>reset();
 (function(){const b1=document.createElement('button');b1.textContent='单步 ▸';b1.onclick=()=>step();
  const b2=document.createElement('button');b2.className='ghost';b2.textContent='自动播放 ⏵';
  const stop=()=>{if(play){clearInterval(play);play=null;}b2.textContent='自动播放 ⏵';b2.classList.add('ghost');};
  b2.onclick=()=>{if(play){stop();return;}play=setInterval(()=>{if(!step())stop();},480);b2.textContent='暂停 ⏸';b2.classList.remove('ghost');};
  $('simBtns').insertBefore(b1,$('zoomBtn'));$('simBtns').insertBefore(b2,$('zoomBtn'));})();
 function reset(){if(play){clearInterval(play);play=null;}x=S.x0;trail=[];prev=null;$('teach').innerHTML=teach();update();}
 function step(){
  const g=df2(x)+(S.noise>0?S.noise*(Math.random()*2-1):0);
  const nx=x-S.eta*g;prev=x;trail.push(nx);x=nx;
  if(!isFinite(x)||Math.abs(x)>1e4){update();return false;}
  update();return true;}
 function update(){
  const g=df2(x),J=f2(x),ok=Math.abs(g)<1e-2;
  $('readout').innerHTML='<div class="kpi"><div class="k">'+(D.sim.kA||'当前位置')+'</div><div class="v">'+(+x).toFixed(2)+'</div></div>'+
   '<div class="kpi"><div class="k">'+(D.sim.kB||'目标函数')+'</div><div class="v">'+(isFinite(J)?J.toFixed(2):'∞')+'</div></div>'+
   '<div class="kpi"><div class="k">'+(D.sim.kC||'当前斜率')+'</div><div class="v">'+(isFinite(g)?g.toFixed(2):'∞')+'</div></div>'+
   '<div class="kpi hi"><div class="k">'+(D.sim.kD||'状态')+'</div><div class="v" style="font-size:15px">'+(Math.abs(x)>1e4?'已发散':ok?'已停住':'迭代中')+'</div></div>';
  $('subst').innerHTML='<i>x</i><sub>t+1</sub> = '+(+x).toFixed(2)+' − '+(+S.eta).toFixed(2)+' × ('+(isFinite(g)?g.toFixed(2):'∞')+') = <b>'+(isFinite(x)?(x-S.eta*g).toFixed(2):'∞')+'</b>';
  draw();
 }
 function draw(){
  const W=cv.width,H=cv.height,pad=42,dom=cur.domain,cs=getComputedStyle(document.documentElement);
  const acc=cs.getPropertyValue('--accent').trim(),acc2=cs.getPropertyValue('--accent2').trim(),
   ln=cs.getPropertyValue('--line').trim(),okc=cs.getPropertyValue('--ok').trim(),mut=cs.getPropertyValue('--muted').trim();
  const N=200,pts=[];
  for(let i=0;i<=N;i++){const xx=dom[0]+(dom[1]-dom[0])*i/N;pts.push([xx,f2(xx)]);}
  const vals=pts.map(p=>p[1]).filter(v=>isFinite(v)&&Math.abs(v)<1e5);
  let lo=Math.min(...vals),hi=Math.max(...vals);
  if(isFinite(f2(x))&&Math.abs(f2(x))<1e5){lo=Math.min(lo,f2(x));hi=Math.max(hi,f2(x));}
  if(hi-lo<1e-6)hi=lo+1;
  const rg=hi-lo;lo-=rg*.12;hi+=rg*.12;
  const X=v=>pad+(v-dom[0])/(dom[1]-dom[0])*(W-2*pad);
  const Y=v=>H-pad-(v-lo)/(hi-lo)*(H-2*pad);
  ctx.clearRect(0,0,W,H);
  ctx.strokeStyle=ln;ctx.lineWidth=1;ctx.beginPath();ctx.moveTo(pad,H-pad);ctx.lineTo(W-pad,H-pad);ctx.stroke();
  ctx.fillStyle=mut;ctx.font='12px sans-serif';ctx.fillText('x →',W-46,H-pad+18);ctx.fillText('f(x) ↑',pad-34,pad-10);
  (cur.minima||[]).forEach(mx=>{ctx.beginPath();ctx.arc(X(mx),Y(f2(mx)),5,0,7);
   ctx.fillStyle=cs.getPropertyValue('--card').trim();ctx.fill();ctx.strokeStyle=okc;ctx.lineWidth=2;ctx.stroke();});
  ctx.beginPath();ctx.lineWidth=2.5;ctx.strokeStyle=acc;let st=false;
  pts.forEach(p=>{if(!isFinite(p[1])||Math.abs(p[1])>1e5){st=false;return;}const px=X(p[0]),py=Y(p[1]);
   if(!st){ctx.moveTo(px,py);st=true;}else ctx.lineTo(px,py);});
  ctx.stroke();
  ctx.strokeStyle=acc2;ctx.lineWidth=2;ctx.globalAlpha=.55;ctx.beginPath();st=false;
  trail.forEach(tx=>{if(!isFinite(tx)||Math.abs(tx)>1e5)return;const py=Y(f2(tx));if(py<-1e4||py>1e4)return;
   if(!st){ctx.moveTo(X(tx),py);st=true;}else ctx.lineTo(X(tx),py);});
  ctx.stroke();ctx.globalAlpha=1;
  if(isFinite(x)&&x>=dom[0]-1&&x<=dom[1]+1){
   const yv=f2(x),gv=df2(x);
   ctx.strokeStyle=okc;ctx.lineWidth=1.5;ctx.setLineDash([6,4]);ctx.beginPath();
   ctx.moveTo(X(x-1),Y(yv-gv));ctx.lineTo(X(x+1),Y(yv+gv));ctx.stroke();ctx.setLineDash([]);
   const xn=Math.min(Math.max(x-S.eta*gv,dom[0]),dom[1]);
   ctx.strokeStyle=acc2;ctx.lineWidth=2;ctx.beginPath();ctx.moveTo(X(x),Y(yv));ctx.lineTo(X(xn),Y(f2(xn)));ctx.stroke();
   ctx.beginPath();ctx.arc(X(x),Y(yv),8,0,7);ctx.fillStyle=acc2;ctx.fill();ctx.strokeStyle='#fff';ctx.lineWidth=2;ctx.stroke();}
 }
 function teach(){const t=D.sim.teach||[];for(const z of t){if(z.lt==null||S.eta<z.lt)return z.text;}return '';}
 window.__plays=()=>{if(play){clearInterval(play);play=null;return;}play=setInterval(()=>{if(!step()){clearInterval(play);play=null;}},480);};
 window.__step=step;window.__redraw=update;
 $('teach').innerHTML=teach();update();
}
buildToc();
if(D.sim.kind==='proportion')initProportion();
else if(D.sim.kind==='step')initStep();
initScenes();initCompare();
</script>
</body>
</html>
```

## 8. 交付前自查

按重要性排：前三条建议都做，后三条看时间。

**① 语法**（最便宜，必做）：把 `<script>` 内容抽出来 `new Function(src)`，跑一次确认没有语法错。
```bash
node -e 'const s=require("fs").readFileSync("报告.html","utf8");const j=s.slice(s.indexOf("<script>")+8,s.lastIndexOf("</script>"));try{new Function(j);console.log("SYNTAX OK")}catch(e){console.log("FAIL",e.message)}'
```

**② 数据可解析 + 结构完整**：eval 出 `D`，打印各数组长度，确认无 `undefined`。
> 常见坑：JSON 字符串里出现**未转义的英文双引号**（如 `"反直觉"`）会直接让整段脚本报 `Unexpected identifier`。中文里一律用「」或 『』。

**③ 数值验算**：把模拟器的核心公式用 node 独立实现一遍，至少测 4 组：默认值、边界（0 / 1 / 极端小）、临界值（让行为翻转的那个点）、不对称点。确认算出来的数和**文案里写的数**一致。
> 这条是铁律 5 的落地。教学报告里最致命的不是样式丑，是「图在演示 A，文字写着 B」。

**④ 真浏览器渲染**：
```bash
chrome --headless=new --disable-gpu --no-sandbox --virtual-time-budget=4000 --dump-dom "file:///<绝对路径>" > _dom.html
```
在 dump 里 grep 关键读数（后验值、KPI、公式代入），确认是**算出来的数字**而不是空标签。

**⑤ 交互点击测试**：复制一份页面，在 `</body>` 前注入脚本，程序化点一遍，把结果写进 `document.title`，再 dump 读标题。
```js
window.addEventListener("load",()=>{const L=[];
 try{
  document.querySelectorAll("#presets button")[2].click();            // 预设切换
  L.push("preset:"+document.querySelector(".kpi.hi .v").textContent); // 读数是否跟着变
  document.querySelectorAll(".fstep")[3].click();                     // 因果链
  document.querySelector(".flash").click();                           // 闪卡翻转
  const o=document.querySelectorAll(".qopt"); o[2].click();           // 自测
  L.push("quiz:"+document.querySelectorAll(".qwhy")[0].style.display);
 }catch(e){L.push("ERR:"+e.message);}
 setTimeout(()=>{document.title="TEST|"+L.join("|")},500);});
```
预期：每个 `ok`/具体数值，**不允许出现 `ERR:`**。

**⑥ 双主题目测**：`data-theme` 切 dark，确认点阵、曲线、公式、卡片都还看得清。

**⑦ 可读性自检**（可选）：想量化的时候，把可见文本抽出来算算平均句长与卡片字数。
```bash
node -e 'const fs=require("fs");const s=fs.readFileSync("报告.html","utf8");
const t=h=>h.replace(/<[^>]+>/g,"").replace(/\s+/g,"").trim();
const a=s.indexOf("const D={"),b=s.indexOf("/* ===== 工具");
const D=eval("("+s.slice(a,b).replace(/^const D=/,"").replace(/;+\s*$/,"").trim()+")");
const all=[D.oneLiner,...D.depth.map(x=>x.html),...D.cards.map(c=>(c.lead||"")+(c.content||"")),...D.gaps.map(g=>g.answer)].map(t).join("");
const sp=all.split(/[。！？；]/).filter(x=>x.length>1);
console.log("平均句长",(all.length/sp.length).toFixed(1),"（≤25 合格）");
console.log("最长句",Math.max(...sp.map(x=>x.length)),"（≤40 合格）");
D.cards.forEach(c=>console.log(c.title,t((c.lead||"")+(c.content||"")).length,"字（≤120 合格）"));
console.log("术语条数",(D.terms||[]).length,"（3–6 合格）");'
```
数字超标只是提示该改文案，不用卡死；读者能顺着读完，比指标漂亮重要。

**⑧ 布局检查**（可选，§4.6 的落地）：
```bash
for w in 1440 1200 900; do   # 三档宽度各跑一次
  chrome --headless=new --window-size=$w,900 --dump-dom "file:///<绝对路径>" >/dev/null
done
```
判据三条，缺一即不合格：
1. 每档 `document.documentElement.scrollWidth === clientWidth`（无横向滚动）
2. 1440：`#tocSide` 可见、滚动 900px 后其 `top ≈ 34`；1200 / 900：`#tocTop` 可见、`top ≈ 0`
3. 逐一输入四个主题，副标题与目录文字对比度 ≥ 4.5:1

---

## 9. 交付

- 文件名：`费曼学习报告-{概念}.html`，存到工作区 `outputs/`。
- 用文件呈现工具交付，并在回复里给绝对路径。
- 回复里必须写清三件事：**这次补了什么盲点、模拟器要用户动手验证哪一条因果、哪些是脚本实测 / 哪些只是静态审读**。
- 用户要「可分享的网页」时，再走 `qw-app` 的 QW Pages 发布流程；否则**不要**擅自发布。