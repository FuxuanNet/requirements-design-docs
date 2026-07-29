# 需求与设计文档

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](./LICENSE)
[![Language](https://img.shields.io/badge/language-简体中文-red.svg)](#)

用于编写、改写和审阅中文需求规格说明书、概要设计文档的 Agent Skill。它将需求文档的用户视角与设计文档的架构视角分开处理，避免把代码实现直接写成功能需求。

## 能做什么

- 按用户可理解的能力划分功能模块和功能点，并补全功能描述、输入和输出。
- 组织产品概述、范围边界、用户业务流程、UML 活动图和功能模块分解图。
- 组织技术路线、总体架构、模块关系、内部与外部接口、数据结构和 ER 图。
- 审阅需求和设计文档的一致性，检查图、表、功能点、接口与验收项是否同步。
- 使用自然、直接的简体中文，避免空泛套话和先否后肯的强调句式。

## 不处理的事项

- 不代替项目事实核实、领域专家评审、合规审查或最终产品决策。
- 不把未经确认的代码行为、接口字段或技术约束写成既有事实。
- 不要求需求功能模块与代码架构或设计模块一一对应。

## 安装

发布到 GitHub 后，将下面的 `<OWNER>` 替换为仓库所有者：

```bash
npx skills add https://github.com/FuxuanNet/requirements-design-docs
```

仅安装到 Codex：

```bash
npx skills add https://github.com/FuxuanNet/requirements-design-docs -a codex
```

安装器从 GitHub 仓库根目录读取 `SKILL.md`。因此发布时应将当前目录的内容作为仓库根目录，不要再包一层 `skills/requirements-design-docs`。

## 使用

可直接用自然语言提出任务，也可显式调用：

```text
使用 $requirements-design-docs，依据现有代码和项目资料编写需求规格说明书。

使用 $requirements-design-docs，审阅这份概要设计文档的模块关系和接口设计。
```

需求任务会加载用户视角、功能点和业务流程规则；设计任务会加载架构、模块关系和接口规则。两类任务都会应用中文语言风格与图文一致性检查。

## 目录

```text
.
├── SKILL.md                 # Agent 读取的入口与工作流程
├── agents/openai.yaml       # Codex 界面元数据
├── references/
│   ├── overview.md          # 共同语言风格、边界和检查规则
│   ├── requirements.md      # 需求文档规则
│   └── design.md            # 设计文档规则
├── CHANGELOG.md
├── CONTRIBUTING.md
└── LICENSE
```

## 维护与发布

1. 修改规则前，先判断它属于总览、需求或设计；将规则放入唯一的参考文件，避免三处重复。
2. 改动 `SKILL.md` 或 `references/` 后，核对 README 的能力说明、术语和目录是否仍然准确。
3. 保持 `SKILL.md` 的 YAML frontmatter 仅含 `name` 和 `description`；`description` 需要覆盖实际触发场景。
4. 运行可用的 skill 校验工具，确认 frontmatter、技能名和相对链接有效；发布前以 `npx skills add <仓库地址> --list` 验证安装器能发现该 skill。
5. 对用户可感知的规则变更更新 `CHANGELOG.md`，再提交并发布版本标签。

详细的贡献与审阅要求见 [CONTRIBUTING.md](./CONTRIBUTING.md)。

## 许可证

MIT，见 [LICENSE](./LICENSE)。
