# UI前端交互神器（ui-frontend-kit）

面向 **Codex / Cursor Agent** 的 UI 前端元技能包：把「嵌套 design skills + 组件库 + 审美/动效参考站 + 可粘贴提示词」收成一条可安装的 skill，专门服务网页、落地页、组件动效、去 AI 感与交互审阅。

- Skill 名（安装 ID）：`ui-frontend-kit`
- 中文称呼：UI前端交互神器
- 维护者 GitHub：[`booksiyi777-678`](https://github.com/booksiyi777-678)
- 许可证：MIT

## 它是什么

加载本 skill 后，Agent 应：

1. 按决策树判断：该装/唤起哪个嵌套 skill，还是该打开参考站，还是该截图复刻。
2. 优先走官方链接与官方安装命令，而不是凭记忆复述嵌套 skill 全文。
3. 用仓库内 `references/prompt-cheatsheet.md` 与 `SKILL.md` 中的推荐提示词直接开干。

本仓库是**路由与工作流编排**，不是把所有上游 skill 内容抄一遍。上游 skill 有更新时，请按各自官方仓库安装/更新。

## 安装（Codex）

任选其一：

```bash
# 推荐：从 GitHub 一键安装
npx skills add booksiyi777-678/ui-frontend-kit
```

或手动复制：

```bash
# 将本仓库的 SKILL.md 放到 Codex skills 目录
mkdir -p .agents/skills/ui-frontend-kit
cp SKILL.md .agents/skills/ui-frontend-kit/SKILL.md
# 可选：一并复制提示词速查
mkdir -p .agents/skills/ui-frontend-kit/references
cp references/prompt-cheatsheet.md .agents/skills/ui-frontend-kit/references/
```

安装后，在对话里提到「做落地页 / 审交互 / 去 AI 感 / 找组件动效」等场景时，Agent 应优先加载本 skill。

## 怎么用

1. **先加载本元技能** `ui-frontend-kit`。
2. 打开 `SKILL.md`，按「决策树」选路径：
   - 有明确专项 skill（Logo、动效品味、去 slop、落地页设计等）→ 安装/唤起对应嵌套 skill。
   - 需要灵感、组件片段、动效/流程参考 → 打开「网站 / 组件库 / 参考」里对应站点。
   - 用户给了截图/录屏 → 走「截图复刻」。
3. 嵌套 skill **存在时**：用官方命令安装并按其自己的规则执行；不要用本仓库的一两句摘要替代全文。
4. 中文文案需要去 AI 味时，再挂 `Humanizer-zh`。
5. 需要品牌 Logo 时，再挂 `ip-as-logo` / `logo-generator`。

完整路由、提示词、硬规则见 [`SKILL.md`](./SKILL.md)；短提示词银行见 [`references/prompt-cheatsheet.md`](./references/prompt-cheatsheet.md)。

## 嵌套 Skills（官方仓库）

| Skill | 仓库 |
| --- | --- |
| Ip as logo | https://github.com/s1dashu/ip-as-logo-skill |
| logo generator | https://github.com/op7418/logo-generator-skill |
| emilkowalski/skills | https://github.com/emilkowalski/skills |
| Humanizer-zh | https://github.com/op7418/humanizer-zh |
| taste-skill / design-taste-frontend | https://github.com/Leonxlnx/taste-skill |
| impeccable | https://github.com/pbakaus/impeccable （文档 https://impeccable.style ） |
| AI Design Skills | https://github.com/elayadesign/ai-design-skills |

## 方法与参考站（摘要）

- 方法：Vercel Web Design Guidelines；截图复刻。
- 站点/组件库：allan.xin、elaya.design、slopscan.co、motionsites.ai、Aceternity UI、React Bits、aura.build、Page Flows、Mobbin、Uiverse 等（细节与用法见 `SKILL.md`）。
- Orla：原抖音合集未确认独立官网；来源备注见抖音链接 `https://v.douyin.com/HIYoYfjSUe4/`，**不要编造官方 URL**。

## 归因（Attribution）

本包聚合并路由到多家上游作者的 skills 与公开参考站，**版权与行为规则仍归各上游仓库/站点所有**。使用嵌套 skill 时请遵守其各自 LICENSE 与说明。本仓库仅提供编排、中文工作流与提示词示例；MIT 仅覆盖本仓库原创文本与结构。

特别致谢：各嵌套 skill 作者（见上表链接）、Vercel Design Guidelines、以及合集中列出的组件库与参考站维护者。合集线索来自公开抖音分享（见 Orla 来源备注），整理为可安装 skill 包以便 Codex 使用。

## 贡献与更新

- 发现上游安装命令变更：请开 PR 更新 `SKILL.md` 对应小节，勿臆造新工具。
- 新增嵌套 skill 或参考站：须提供可验证的官方链接，并补充「何时用 / 怎么用 / 提示词」。

## License

[MIT](./LICENSE) © 2026 booksiyi777-678
