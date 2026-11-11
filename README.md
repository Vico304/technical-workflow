# 技术协作与中文写作

将工程协作与中文技术表达组合为一个 Codex 插件，保留两个技能入口，分别维护工程规则与写作规则。

| 技能 | 用途 | 源文件 |
| --- | --- | --- |
| `technical-collaboration` | 技术选型、方案设计、代码实现与审查、部署操作、验证和工程结果判断 | [技术判断与工程协作](skills/technical-collaboration/SKILL.md) |
| `chinese-technical-writing` | 起草、改写、审阅和解释中文技术内容，保持语义、证据强度与自然表达 | [中文技术表达](skills/chinese-technical-writing/SKILL.md) |

工程任务附带文档交付时，由工程技能提供实际结果与依据，写作技能组织文字。详细写作规则统一维护在 `chinese-technical-writing`；工程细则维护在 `technical-collaboration/references/engineering.md`。两个技能通过相对链接互相引用，作为插件共同分发。

## 安装

使用支持 `plugin` 命令的 Codex CLI：

```bash
codex plugin marketplace add Vico304/technical-workflow --ref main
codex plugin add technical-workflow@technical-workflow
```

安装后在新会话中使用“技术协作与中文写作”。如果已经通过其他 marketplace 安装了同一插件，迁移时只保留一个启用的副本。

## 维护

`skills/` 保存技能说明、参考资料、界面配置及长期偏好片段。修改技能内容时同步检查入口说明与相对链接；长期偏好片段仅在用户明确要求安装或更新偏好时合并到个人指令。

- [plugin.json](plugin.json)：插件基础信息及 OpenAI 界面信息。
- [.codex-plugin/plugin.json](.codex-plugin/plugin.json)：Codex 插件清单，指定技能目录。
- [.agents/plugins/marketplace.json](.agents/plugins/marketplace.json)：指向本仓库 `main` 分支的 marketplace 清单。

两个插件清单中的名称、版本、描述和界面信息保持一致。本仓库以现有插件 `0.1.0` 为初始版本，保留两个技能各自的版本记录。

公开内容只包含通用技能及插件材料。本机绑定、导入备份、凭据和临时文件放在被忽略的 `.local/` 等位置。
