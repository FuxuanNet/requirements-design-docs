# 贡献与维护

## 修改原则

- 保持 `SKILL.md` 精简，只放触发信息、执行流程和必须始终遵守的规则；详细规范放入 `references/`。
- `overview.md` 只放需求和设计共用的规则，`requirements.md` 与 `design.md` 分别维护各自的文档要求。
- 新增规则应说明适用对象、目的和边界。避免把个人偏好写成普遍事实，也不要与现有规则重复或冲突。
- 示例和术语应使用自然、直接的中文；修改说明不要出现空泛宣传语。

## 审阅清单

- `SKILL.md` frontmatter 仅包含 `name` 与 `description`，名称、目录名和安装时显示的技能名一致。
- 每个 `SKILL.md` 链接的参考文件存在，引用路径正确。
- 需求规则仍坚持用户视角，设计规则仍强调架构、模块、高内聚、低耦合和可扩展性。
- README、`agents/openai.yaml` 和 `CHANGELOG.md` 与实际内容一致。
- 规则变更没有要求模型虚构项目事实或替代用户决策。

## 发布前检查

1. 使用可用的 Agent Skill 校验工具检查 `SKILL.md` 的 YAML frontmatter 和目录结构。
2. 在仓库根目录执行 `npx skills add <仓库地址> --list`，确认外部安装器可以发现该 skill；此命令只列出可安装内容。
3. 检查 README 中的安装链接、示例和目录树。
4. 在 `CHANGELOG.md` 记录本次版本变化，提交后创建对应 Git 标签。
