# Smoke Test

- 执行日期：2026-07-04
- 结论：通过
- 结果类型：一次通过

## 1. 结构检查
| 检查项 | 结果 | 备注 |
| --- | --- | --- |
| `name` 为 lowercase-hyphen | 通过 | `figma-plugin-path-selector` |
| `description` 长度 50-150 字符 | 通过 | 140 字符 |
| 包含 `核心定位 / 触发场景 / 工作流 / 输出格式 / Gotchas` | 通过 | 五个必需章节齐全 |
| 工作流 3-8 步 | 通过 | 6 步 |
| Gotchas 至少 4 条 | 通过 | 6 条 |
| 无未填充占位符 | 通过 | 未发现 `TODO / PLACEHOLDER / 待补充` |

## 2. README 检查
| 检查项 | 结果 | 备注 |
| --- | --- | --- |
| 安装路径与仓库名一致 | 通过 | 使用 `~/.claude/skills/figma-plugin-path-selector` |
| 文件树与实际文件一致 | 通过 | `SKILL.md / README.md / smoke-test.md / publish-checklist.md` |
| 示例触发词与 skill 名称一致 | 通过 | 中英文触发均指向 Figma 路径选择 |
| 未误把本地中文目录名写成安装目录 | 通过 | README 仅把中文目录名作为本地归档说明 |

## 3. 触发干运行
### 中文真实触发词

```text
帮我判断：设计团队每周要把同一套活动页做成 6 个尺寸和 3 种品牌语气，这种需求该做成 Figma generative plugin、custom skill 还是普通 plugin？
```

**预期落点**

- 先抽取重复流程、输入输出和频率
- 再比较 `generative plugin / custom skill / plugin`
- 输出 Top 1 路径、理由、MVP 边界和权限风险

**实际干运行结果**

- 能自然进入路径比较而不是泛泛聊 Figma 新功能
- 会把“生成多版本视觉结果”识别为生成式插件候选
- 会保留传统 plugin 作为批量规范化备选，而不是直接一刀切

### English variant

```text
Pick the right Figma surface for our repeated hero-banner cleanup workflow. We need to rename layers, swap text styles, and export assets fast.
```

**预期落点**

- 进入 surface-selection 报告
- 给出 why plugin / why not skill / why not code layer
- 输出 brief 而不是停在抽象建议

**实际干运行结果**

- 稳定收敛到 classic plugin 为主路径
- 能解释该任务为什么不需要生成式能力
- 输出格式与 README 中承诺一致

## 4. 发布前结论

- 当前可发布：是
- GitHub 发布结果：已发布
- 仓库地址：https://github.com/ReiSei0824/figma-plugin-path-selector
- 备注：2026-07-04 已创建公开仓库并推送 `main`
