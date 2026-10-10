<div align="center">
  <p><strong>谁是专家 · 视觉实验室</strong></p>
  <h1>Top22 漫画肖像 Skill</h1>
  <p>为 Codex 和 GPT Image 2.5 打造的漫画头像风格选择与生成 Skill。</p>
  <p><a href="./style-gallery.html"><strong>浏览 22 张风格卡片 →</strong></a></p>
</div>

**先看效果，再选风格。** 上传肖像并调用 Skill 后，如果没有指定风格，它会先打开 22 张风格卡片，请你按编号或名称选择，再开始生成。

## 能做什么

- 把用户提供的肖像转成漫画头像，并尽量保留可辨认的身份特征。
- 根据原工程的完整 `promptData` 字段逐项构建风格提示，保留线条、明暗、造型、配色、纹理、构图、氛围和排除项。
- 为 GPT Image 2.5 加入通用画面降噪约束，减少随机颗粒、彩色噪点、脏斑和杂乱微纹理，同时保留风格需要的排线、网点或纸纹。
- 提供可搜索、可筛选的独立 HTML 风格图册，方便直接比较 22 种效果。

## 快速开始

把本仓库完整放入 Codex 的个人 Skill 目录，目录名使用 `top22comic-image-2-5`。默认位置是 `$HOME/.codex/skills/`；如果你自定义了 `CODEX_HOME`，则使用 `$CODEX_HOME/skills/`。

```bash
gh repo clone mizzlelover/shui-shi-zhuan-jia-top22comic-skill "$HOME/.codex/skills/top22comic-image-2-5"
```

在 Codex 中调用 `top22comic-image-2-5`，附上肖像并说明想生成漫画头像。未给出风格时，Skill 会先请你浏览图册并选择；明确指定风格后，它会读取对应的完整配方再生成。

## 仓库内容

| 路径 | 内容 |
| --- | --- |
| `SKILL.md` | Codex Skill 入口、选择流程、提示词规则和降噪约束 |
| `references/style-catalog.md` | 22 个视觉方向的索引 |
| `references/source-prompt-recipes.md` | 原工程完整 `promptData` 字段与值 |
| `style-gallery.html` | 可搜索和筛选的 22 张风格图册 |
| `style-references-v02-original-prompts/` | 按原工程完整配方生成的图册样张 |

本仓库只打包 Codex Skill、风格配方和图册资源，不包含原工程的 Gemini 应用代码。样张基于项目维护者提供的肖像生成；未收录原始肖像。

## 运行边界

Skill 仅针对 GPT Image 2.5 的自然语言提示进行适配。图像生成依赖当前 Codex 会话提供的图像生成或编辑能力；如果不可用，Skill 会提供可复制的提示词，并说明没有生成图像。

项目品牌：**谁是专家**。
