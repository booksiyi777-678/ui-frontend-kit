# 提示词速查（Prompt Cheatsheet）

配合元技能 `ui-frontend-kit` 使用。复制后把 `{占位符}` 换成真实信息。完整路由见根目录 `SKILL.md`。

## 元路由

- `加载 ui-frontend-kit：我要做 {落地页/去AI感/动效/Logo/审交互}，按决策树选嵌套 skill 或参考站，先告诉我你的路径再执行。`
- `不要复述嵌套 skill 全文；该安装的用官方命令安装后按其 SKILL 执行。`

## Logo / 品牌

**Ip as logo**

- `按 ip-as-logo：品牌「{名}」，定位「{一句话}」。先给 3 个角色方向，我确认后再出图。`
- `方向定为「{方向}」。生成 6 个候选；左下构图；限 3 色；适合网站 header。`

**logo generator**

- `用 logo-generator：先收集品牌名/行业/关键词/忌讳，齐了再出至少 6 个 SVG 变体 + showcase。`
- `选定 #{n}：导出主标、单色版、favicon 裁切建议，源文件保持可编辑 SVG。`

## 去 AI 感 / 品味

**taste / design-taste-frontend**

- `加载 design-taste-frontend，审计本页 AI-slop（字体/色/间距/卡片套路），输出可执行修改清单。`
- `重做视觉方向：禁止无理由的紫渐变 + Inter；先提 2 个有意识的艺术方向。`

**impeccable**

- `/impeccable init 后对当前项目 audit，问题按优先级排序。`
- `$impeccable critique 首页：层级、对比、节奏、CTA。`
- `对 {区块} 做 polish；另出一版 bolder 仅作对比。`

**Humanizer-zh**

- `用 Humanizer-zh 改写下文：去套话，保留全部事实与数字：\n{文案}`
- `功能说明 humanize：保持专业，禁止夸张营销腔。`

**slopscan 视角**

- `以 slopscan 去 slop 视角列 Top 5 AI 味问题，并映射到具体组件/CSS 改动。`

## 落地页结构

**AI Design Skills / landing-page-design**

- `加载 landing-page-design：受众 {谁}，产品 {一句话}。先信息架构，再分区文案与布局。`
- `重构叙事为：问题 → 方案 → 证据 → CTA；视觉稍后用 taste/impeccable 统一。`

## 动效 / 组件库

**emilkowalski/skills**

- `审查本页动效：过度/缺失/时机；给改法。`
- `项目栈 {栈}：按 pick-ui-library 推荐方案并说明取舍。`

**Aceternity UI** — https://ui.aceternity.com

- `从 Aceternity 选适合 {SaaS hero/Bento/...} 的区块，接入 {框架}，替换为我们的色板与文案。`

**React Bits** — https://reactbits.dev

- `从 React Bits 选轻量 {背景/按钮} 动效，接入首页且不影响 LCP。`

**Uiverse** — https://uiverse.io

- `选一个 button/loader，改成我们的 design token，并补全 focus/禁用态。`

**Motion Sites** — motionsites.ai

- `找 2 个气质接近「{气质}」的滚动叙事，提炼时间轴，实现克制版。`

## 流程 / 竞品模式

**Page Flows** — https://pageflows.com

- `对照「{onboarding/checkout/...}」常见步骤，优化我们的流程并标出可删步骤。`

**Mobbin** — https://mobbin.com

- `调研「{空状态/定价页/...}」模式，总结 3 种做法并推荐一种。`

## 审计方法

**Vercel Guidelines** — https://vercel.com/design/guidelines

- `对照 Vercel Web Design Guidelines 审计交互，按严重度列出违规与改法。`

**截图复刻**

- `复刻截图的布局与交互；功能一致；视觉统一到 {token/参考}；不抄受版权素材。`
- `按录屏 {时间段} 实现等价转场，给出时长与缓动参数。`

## 组合工作流（短指令）

- `新落地页标准流：landing-page-design → taste/impeccable → Aceternity/React Bits → Motion Sites → Vercel guidelines/impeccable critique → Humanizer-zh → 如需 Logo 再挂 logo skill。`
- `去 AI 味快修：taste 列问题 → 换掉紫渐变 Inter 默认组合 → impeccable polish → Humanizer-zh 文案。`
- `只升动效：Motion Sites/React Bits 找参考 → emilkowalski 审查 → guidelines 查可读与性能。`

## Orla 备注

- 无已确认官网；来源笔记：https://v.douyin.com/HIYoYfjSUe4/  
- 不要提示「打开 Orla 官网」；改用本表其他参考站。
