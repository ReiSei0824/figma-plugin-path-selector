# Figma插件路径规划师 | Figma Plugin Path Selector

面向设计团队、设计工程师、产品负责人和 AI 工作流负责人。它专门处理一个正在快速变难的问题：同样都是“把重复设计工作交给 AI”，到底该做成 Figma `custom skills`、`generative plugins`、`code layers`、传统 `plugins`，还是干脆放到 Figma 外部。

## 适用场景

- 你已经发现某段设计流程每周都在重复，但不知道该落在哪个 Figma 表面
- 团队准备做 AI 设计能力立项，需要先做 MVP 收敛、权限判断和发布 brief
- 你想避免一上来就做复杂插件，先判断是否值得产品化

## 触发词

- `帮我判断这个设计流程该做成 Figma skill 还是 plugin`
- `这个需求更适合 generative plugin 还是 code layer`
- `评估一下我们的设计团队 AI 工作流该落在哪个 Figma 表面`
- `Should this workflow become a Figma custom skill or a plugin?`
- `Pick the right Figma surface for this repeated design task`

## 工作流

1. 锁定一个可重复、可演示、可衡量的设计工作流。
2. 拆分动作、输入输出、数据来源和权限约束。
3. 对照 `custom skills / generative plugins / code layers / plugins / outside Figma` 做路径比较。
4. 按价值、复杂度、闭环程度、风险和两周落地性评分。
5. 产出 Top 1 建议与实施 brief。
6. 补齐 README、仓库名、演示素材和风控提醒。

## 输出结果

- 一份路径比较表
- 一个 Top 1 建议
- 一份可直接交给团队推进的实施 brief
- 一组发布建议：仓库名、README 结构、演示素材、MVP 边界

## 示例

### 中文触发

```text
帮我判断：设计团队每周批量改活动页素材尺寸和文案样式，这个需求更适合做 Figma generative plugin、custom skill，还是普通 plugin？
```

### English trigger

```text
Should our repeated landing-page variant workflow become a Figma generative plugin, a custom skill, or a classic plugin?
```

## 安装

对外发布时，推荐安装目录统一使用英文 slug：

```bash
git clone https://github.com/ReiSei0824/figma-plugin-path-selector.git ~/.claude/skills/figma-plugin-path-selector
```

本地中文归档目录可以保留为 `Figma插件路径规划师（figma-plugin-path-selector）`，但 README、仓库名和安装路径都应统一使用 `figma-plugin-path-selector`。

## 文件结构

```text
figma-plugin-path-selector/
├── SKILL.md
├── README.md
├── smoke-test.md
└── publish-checklist.md
```

## 发布说明

- 推荐仓库名：`figma-plugin-path-selector`
- 推荐可见性：`public`
- 发布前先跑 `smoke-test.md`
- 若需要真正实现插件代码，应在该 brief 基础上另开仓库或子目录，不要把需求判断和实现代码混写
