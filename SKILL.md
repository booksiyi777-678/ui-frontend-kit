---
name: ui-frontend-kit
description: UI前端交互神器：做网页/落地页/组件动效/去AI感/审交互时优先加载。路由到嵌套 design skills、组件库与审美参考站，并给出何时用、怎么用与可直接粘贴的提示词。
---

# UI前端交互神器（ui-frontend-kit）

可执行 playbook：路由嵌套 skills、参考站与截图复刻。**不要把本文件当成博客**；按决策树选路，优先安装/加载上游 skill，而不是复述其全文。

## 何时触发

出现以下任一意图时，**优先加载本 skill**：

- 做 / 改 **网页、落地页、营销站、产品站**
- 做 / 审 **组件动效、微交互、页面转场**
- **去 AI 感**（排版、配色、文案 slop、紫渐变 Inter 味）
- **审交互质量**、对标优秀产品流程
- 需要 **Logo / IP 形象**、组件库片段、动效或 UI 流程参考
- 用户说「UI前端交互神器」「前端审美」「别那么 AI」

## 决策树

```
用户任务
├─ 明确是 Logo / IP 形象？
│   ├─ 可爱 IP 角色 Logo → ip-as-logo-skill
│   └─ 通用 SVG Logo + 展示墙 → logo-generator-skill
├─ 中文文案去 AI 味、保留事实？ → Humanizer-zh
├─ 整页反 AI-slop、审美与前端落地？ → taste-skill (design-taste-frontend) 和/或 impeccable
├─ 落地页信息架构 / 区块设计专项？ → AI Design Skills (landing-page-design 等)
├─ 动效品味、动画审查、选 UI 库？ → emilkowalski/skills
├─ 只要组件片段 / 动效灵感 / 竞品流程？
│   └─ 打开下方「网站 / 组件库 / 参考」，按管什么选站
├─ 用户贴了截图或录屏要「做成那样」？ → 截图复刻
└─ 要审计交互质量？ → Vercel Web Design Guidelines + impeccable critique/audit
```

**冲突时的优先级（默认）：**

1. 用户明确点名的嵌套 skill / 站点
2. 有官方嵌套 skill → **安装并按其规则跑**（禁止用本摘要代替）
3. 参考站只提供灵感与可复用模式，落地时统一到当前项目的视觉语言
4. 截图复刻：保功能与信息层级，视觉语言可统一到既定参考，勿逐像素盲抄版权素材

---

## 嵌套 Skills

对每一个：先看「何时用」，再用官方命令安装/唤起，提示词可直接粘贴。

### 1. Ip as logo

- **一句话用途：** 生成可爱 IP 角色型 Logo（偏吉祥物/角色向）。
- **何时用：** 品牌需要「有性格的角色 Logo」、周边延展，而不是纯文字标。
- **怎么装 / 怎么唤起：**
  - 仓库：https://github.com/s1dashu/ip-as-logo-skill
  - 按该仓库 README 安装到 Codex/Cursor skills；对话中说明要做 IP Logo 并加载该 skill。
- **推荐提示词：**
  1. `按 ip-as-logo 流程：先基于品牌「{品牌名/一句话定位}」提出 3 个角色方向，我确认后再出图。`
  2. `确认方向「{方向}」后，生成 6 个候选 IP Logo；构图偏左下；限制 3 色；透明或简洁底。`
  3. `从 6 个候选里选 #{n}，输出可用于网站 header 的方形与横向两种裁切说明。`
- **官方链接：** https://github.com/s1dashu/ip-as-logo-skill

### 2. logo generator

- **一句话用途：** 收集品牌信息后批量产出 SVG Logo，并做展示墙对比。
- **何时用：** 需要矢量 Logo、多方案对比、偏标识系统而非角色 IP。
- **怎么装 / 怎么唤起：**
  - 仓库：https://github.com/op7418/logo-generator-skill
  - 按仓库说明安装；先让 Agent 收集品牌信息再生成，目标 **≥6 个变体**。
- **推荐提示词：**
  1. `用 logo-generator：先问我品牌名、行业、关键词、喜欢/讨厌的风格，信息齐后再生成。`
  2. `基于已收集信息输出至少 6 个 SVG Logo 变体，并做一页 showcase 方便对比。`
  3. `把选定方案整理为：主标、单色版、favicon 裁切建议（仍保持 SVG 源可编辑）。`
- **官方链接：** https://github.com/op7418/logo-generator-skill

### 3. emilkowalski/skills

- **一句话用途：** 动效品味、动画审查、选型 UI 库等前端交互向 skills 合集。
- **何时用：** 动画「味道不对」、不知选哪套 UI 库、需要 review animations / pick-ui-library 等专项。
- **怎么装 / 怎么唤起：**
  ```bash
  npx skills@latest add emilkowalski/skills
  ```
  安装后按合集内具体 skill 名唤起（如 animation taste、review-animations、pick-ui-library 等，以仓库当前列表为准）。
- **推荐提示词：**
  1. `加载 emilkowalski 的动画相关 skill，审查本页动效：指出过度/缺失/时机问题，并给改法。`
  2. `按 pick-ui-library 思路：项目是 {栈/约束}，在可维护性与动效能力之间推荐库并说明理由。`
  3. `把首页 hero 到 CTA 的动效节奏按 animation taste 收紧一版，避免炫技。`
- **官方链接：** https://github.com/emilkowalski/skills

### 4. Humanizer-zh

- **一句话用途：** 中文文案去 AI 套话（de-slop），**保留事实与信息**。
- **何时用：** 落地页/关于我们/功能说明读起来像模型腔；需要人味但不改事实。
- **怎么装 / 怎么唤起：**
  - 仓库：https://github.com/op7418/humanizer-zh
  - 按仓库 README 安装；对选定中文段落运行，强调「不增删关键事实」。
- **推荐提示词：**
  1. `用 Humanizer-zh 改写以下中文，去掉 AI 套话，保留全部事实与数字：\n{文案}`
  2. `这段是产品功能说明，humanize 时保持专业，不要变成过度口语或营销夸张。`
  3. `对比改写前后，列出你删掉的套话类型（空洞形容词/假排比/万能结尾等）。`
- **官方链接：** https://github.com/op7418/humanizer-zh

### 5. taste-skill / design-taste-frontend

- **一句话用途：** 反 AI-slop 的页面审美与前端落地指导；可配合浏览器检查。
- **何时用：** 整页「一眼假」、排版配色组件都像模板；需要抬升设计品味。
- **怎么装 / 怎么唤起：**
  ```bash
  npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"
  ```
  仓库要求 **Node 22+**；需要浏览器 inspect 时按该 skill 说明操作。
- **推荐提示词：**
  1. `加载 design-taste-frontend：审计当前页面的 AI-slop 特征（字体/配色/间距/卡片套路），给可执行修改清单。`
  2. `按 taste-skill 重做首页视觉方向：禁止默认紫渐变 + Inter；先给 2 个有意识的艺术方向再动手。`
  3. `在 Node 22+ 环境下按 skill 要求打开页面做 browser inspect，对照问题逐项改。`
- **官方链接：** https://github.com/Leonxlnx/taste-skill

### 6. impeccable

- **一句话用途：** 设计 critique / polish / audit / bolder 等命令式打磨流程。
- **何时用：** 已有一版 UI，需要系统性质询、抛光、更大胆，或初始化设计规范。
- **怎么装 / 怎么唤起：**
  ```bash
  npx impeccable install
  ```
  之后在 Codex 中可用 `/impeccable init`、`$impeccable` 以及 critique、polish、audit、bolder 等（以官方文档为准）。
- **推荐提示词：**
  1. `/impeccable init 然后基于当前项目做一次 audit，输出优先级排序的问题列表。`
  2. `$impeccable critique 首页：信息层级、对比度、节奏、CTA 清晰度。`
  3. `对定价区执行 polish，再可选 bolder 一版作对比，不要 simultaneous 瞎叠特效。`
- **官方链接：** https://github.com/pbakaus/impeccable  
- **文档：** https://impeccable.style

### 7. AI Design Skills

- **一句话用途：** 含 landing-page-design 等 AI 设计向 skills，补落地页结构与设计步骤。
- **何时用：** 从 0 搭落地页、需要区块结构/叙事节奏专项，而不是只调样式。
- **怎么装 / 怎么唤起：**
  ```bash
  npx skills add elayadesign/ai-design-skills
  ```
  按仓库内 skill 列表加载（如 `landing-page-design` 等）。
- **推荐提示词：**
  1. `加载 landing-page-design：受众是 {谁}，产品是 {一句话}，先出信息架构再写分区文案与布局。`
  2. `按 AI Design Skills 把现有落地页重构为清晰叙事：问题→方案→证据→CTA。`
  3. `只改结构与文案层级，视觉风格稍后用 taste/impeccable 统一。`
- **官方链接：** https://github.com/elayadesign/ai-design-skills

---

## 方法

### Vercel Web Design Guidelines

- **管什么：** 交互与网页设计质量准则，适合做审计清单。
- **怎么用：**
  1. 打开 https://vercel.com/design/guidelines
  2. 对照当前页：导航、反馈、加载、可访问性、动效克制等条款逐项打勾/打叉
  3. 只修「高影响」项，避免一次性大爆改
- **示例提示词：**
  - `对照 Vercel Web Design Guidelines 审计本站交互，列出违规点与具体改法（按严重度排序）。`

### 截图复刻

- **管什么：** 用户提供截图/录屏时，复刻**功能与层级**，并统一到项目视觉语言。
- **怎么用：**
  1. 让用户粘贴截图或说明录屏关键帧
  2. 拆解：布局骨架 → 组件类型 → 动效节奏 → 文案层级
  3. **保留功能与信息**；颜色/字体/圆角对齐项目或指定参考站，不逐像素盗用受版权素材
  4. 输出可运行的前端实现 + 与参考的差异说明
- **示例提示词：**
  - `复刻这张截图的布局与交互结构；功能保持一致；视觉语言统一到我们现有的 {设计 token/参考}，不要原样抄素材图。`
  - `根据录屏 0:05–0:12 的转场，实现等价动效，时长与缓动可按产品调优并说明参数。`

---

## 网站 / 组件库 / 参考

对每一个：管什么 → 怎么用（步骤）→ 示例提示词。**不要编造未列出的站点能力。**

### allan.xin

- **管什么：** 设计/前端灵感向参考（合集收录站）。
- **怎么用：** 打开站点浏览相关案例 → 记下布局/动效模式 → 在自己项目里用自有组件复现模式（非抄代码许可未明则只学结构）。
- **示例提示词：** `参考 allan.xin 上与「{产品类型}」相近的案例，总结 3 条可迁移的布局/动效模式并应用到当前页。`

### elaya.design

- **管什么：** 与 Elaya 设计体系/落地相关的参考（亦与 AI Design Skills 同源生态可对照）。
- **怎么用：** 浏览落地与设计示例 → 抽取区块叙事 → 回到 `landing-page-design` 或本项目结构落地。
- **示例提示词：** `对照 elaya.design 的表达方式，给当前落地页一版更清晰的区块叙事，不改产品事实。`

### slopscan.co

- **管什么：** 识别 / 扫描 AI slop 审美问题的参考向工具站。
- **怎么用：** 用其视角检查页面「模板感」→ 结合 taste-skill / impeccable 出修改清单。
- **示例提示词：** `以 slopscan 的去 slop 视角列出本页 Top 5 AI 味问题，并映射到具体 CSS/组件改动。`

### motionsites.ai（Motion Sites）

- **管什么：** 动效网站参考，找运动节奏与转场灵感。
- **怎么用：** 按行业/风格筛选 → 记录入场、滚动、hover 模式 → 用项目技术栈（CSS/Framer Motion 等）实现简化版。
- **示例提示词：** `在 Motion Sites 找 2 个与「{气质}」相近的滚动叙事，提炼时间轴，在本站实现克制版。`

### Aceternity UI

- **管什么：** 高质量 React 组件/动效区块库。
- **怎么用：**
  1. 打开 https://ui.aceternity.com
  2. 按需选 Bento、Hero、Testimonials 等区块
  3. 按官方用法接入项目，替换文案/色 token，去掉用不到的特效
- **示例提示词：** `从 Aceternity UI 选一个适合 SaaS hero 的区块，接入 Next.js，并改成我们的色板与文案。`

### React Bits

- **管什么：** React 动效/交互小品与组件灵感。
- **怎么用：** 打开 https://reactbits.dev → 选合适 pattern → 接入或用等价实现，注意包体与可访问性。
- **示例提示词：** `在 React Bits 找一个轻量背景/按钮动效，实现到首页且不影响 LCP。`

### aura.build

- **管什么：** 构建/生成向的 UI 灵感或站点参考（合集收录）。
- **怎么用：** 浏览获取版式与组件组合思路 → 回到自有设计系统实现。
- **示例提示词：** `参考 aura.build 上接近的产品站结构，列出我们落地页应有的模块清单。`

### Page Flows

- **管什么：** 真实产品用户流程截图流（注册、结账、设置等）。
- **怎么用：** 打开 https://pageflows.com → 按任务类型找流程 → 对齐步骤数量与关键决策点（需注意其订阅/访问限制以站点为准）。
- **示例提示词：** `按 Page Flows 里「{任务：如 onboarding}」的常见步骤，优化我们当前流程，标出可删的多余步。`

### Mobbin

- **管什么：** 移动/网页产品 UI 模式库，竞品界面调研。
- **怎么用：** 打开 https://mobbin.com → 按 app/模式搜索 → 抽取模式而非抄像素；输出 pattern 说明再实现。
- **示例提示词：** `用 Mobbin 调研「{模式：如空状态/定价页}」，总结 3 种常见做法并推荐最适合我们的一种。`

### Uiverse

- **管什么：** 社区提交的 HTML/CSS/按钮等小组件。
- **怎么用：** 打开 https://uiverse.io → 选元素 → 拷贝前检查许可与质量 → 纳入设计 token（颜色、圆角、焦点态）。
- **示例提示词：** `在 Uiverse 选一个可访问性尚可的 button/loader，改成我们的 token 并补全 focus 态。`

### Orla（来源备注）

- **管什么：** 合集中提及的参考向名称。
- **怎么用：** **官网未在原视频/合集中确认**；仅作来源笔记，勿伪造官网。
- **来源备注（非官网）：** 抖音 https://v.douyin.com/HIYoYfjSUe4/
- **示例提示词：** （无官方站则不做「打开 Orla 官网」类指示；若用户坚持，先说明未确认官网并改用已列参考站。）

---

## 推荐工作流

### 新落地页（从 0 到 1）

1. `AI Design Skills` / `landing-page-design` → 信息架构与分区文案骨架  
2. `taste-skill`（design-taste-frontend）与/或 `impeccable init` → 艺术方向与反 slop  
3. `Aceternity UI` / `React Bits` / `Uiverse` → 按需接入组件与微交互  
4. `Motion Sites` → 滚动/转场参考（克制实现）  
5. `Vercel Web Design Guidelines` + `impeccable` critique/audit → 交互与视觉质检  
6. `Humanizer-zh` → 中文文案去套话  
7. 若需品牌标识 → `logo-generator` 或 `ip-as-logo`

### 已有页面「去 AI 味」

1. taste / slopscan 视角列出问题 → impeccable polish  
2. 换掉默认紫渐变 + Inter 无理由组合  
3. Humanizer-zh 处理可见文案  
4. emilkowalski 动画审查（若动效廉价或过度）

### 只做动效升级

1. Motion Sites / React Bits / Aceternity 找参考  
2. emilkowalski animation skills 定品味与审查  
3. Vercel guidelines 检查是否妨碍可读与性能

### 只要 Logo

- 角色向 → ip-as-logo（3 方向 → 6 候选 → 左下构图 → 3 色）  
- 标识系统 / SVG 墙 → logo-generator（先收集品牌信息，≥6 变体）

---

## 硬规则

1. **不发明**未在本 skill 列出的工具、站点或安装命令；不确定就说不确定并只用官方链接。  
2. **优先官方链接**；嵌套 skill 以各 GitHub / impeccable.style 为准。  
3. **嵌套 skill 存在时：安装/加载它**，按其 SKILL 全文执行；禁止用本包摘要冒充完整规则。  
4. **禁止无艺术方向地交付**「紫渐变 + Inter + 万能卡片」式 AI slop；若沿用需书面说明是有意识的方向。  
5. **Orla** 不编造官网 URL；仅保留抖音来源备注。  
6. 参考站用于模式学习；注意许可、版权与性能，不默认可商用抄走全部代码/素材。  
7. 提示词中的 `{占位符}` 必须换成用户真实信息后再执行。

## 附属文件

- 提示词速查：`references/prompt-cheatsheet.md`  
- 安装与归因：仓库根目录 `README.md`  
- 许可：`LICENSE`（MIT，Copyright 2026 booksiyi777-678）
