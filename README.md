# Agent Laziness Guard

一套面向 AI Agent 的执行纪律、诊断指南与验收模板，帮助排查任务漏做、引用错误文件、缺少执行证据以及 NL2SQL 结果不稳定等问题。

“偷懒”在这里描述的是可观察的结果，并不意味着模型具有主观意图。项目由使用者提出实际需求，借助 AI 整理而成。

## 适用场景

- **文件处理**：更换文件后结果仍引用旧内容，或缺少原文依据。
- **NL2SQL**：修好一条 SQL 后，换表、时间范围或过滤条件又出现错误。
- **开发任务**：遗漏需求、声称已运行但没有证据、只修复单个样例。

## 内容结构

```text
SKILL.md                              技能入口及使用场景
assets/constraint-rules.md            可复制并按系统能力裁剪的规则
references/checklists.md              执行、验收和回归检查清单
references/file-context-diagnosis.md  文件处理诊断
references/nl2sql-diagnosis.md        NL2SQL 诊断
references/dev-anti-patterns.md       开发任务中的常见问题
```

## 使用方法

1. 阅读 [SKILL.md](SKILL.md)，选择执行纪律、根因诊断或生成规则模板的模式。
2. 根据具体任务阅读 `references/` 中对应的指南。
3. 如需复用规则，可从 [约束模板](assets/constraint-rules.md) 选择相关内容，按实际系统能力裁剪后放入你的 Agent 配置或项目规范。
4. 使用 [检查清单](references/checklists.md) 核对工具结果、失败路径和回归范围，并记录未验证部分。

支持技能目录的 Agent 平台可以按其文档配置该目录；不同平台的导入路径和触发方式可能不同。也可以手动阅读并选用规则。此仓库是文档和规则模板，不包含自动检查程序。

## 使用边界

提示词不能保证 Agent 正确执行，也不能替代文件读取、数据库只读权限、工具返回检查和回归测试。请根据实际任务的风险选择验证范围，并用可观察的证据报告结果。本项目未提供经过验证的通用准确率或效果数据。
