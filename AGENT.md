# AGENT.md

本仓库给编码 Agent 的入口。请立即阅读根目录的 [AGENTS.md](./AGENTS.md)，并按其中的阅读顺序打开 `agents/` 下对应文档，然后再查看或修改代码。

- 规范自动加载的文件名是 `AGENTS.md`。Cursor、Codex 等会自动加载它。
- 本文件只做入口和文档地图。不要在这里复制完整规则，也不要在这里填写项目细节。
- 每个需求开一个新的 Agent 窗口，不要在旧窗口里继续做下一个需求。

## 文档地图

根目录：

- [AGENTS.md](./AGENTS.md)：自动加载的总则。阅读顺序、固定规则、子项目约定。所有项目保持一致，不要改结构。
- [README.md](./README.md)：给人看的模板使用说明，不是给 Agent 的操作手册。

`agents/` 按职责拆分，项目细节写在对应文件里，不要写回本文件：

- [agents/overview.md](./agents/overview.md)：项目是什么、不是什么。
- [agents/architecture.md](./agents/architecture.md)：模块、边界、数据流、不变量。
- [agents/repo-map.md](./agents/repo-map.md)：目录和入口文件职责。
- [agents/commands.md](./agents/commands.md)：环境、安装、运行、构建、测试、检查命令。
- [agents/constraints.md](./agents/constraints.md)：行为约束和本项目特有限制。
- [agents/conventions.md](./agents/conventions.md)：本仓库代码写法。
- [agents/progress.md](./agents/progress.md)：当前任务进度、阻塞和下一步。
- [agents/pitfalls.md](./agents/pitfalls.md)：本仓库真实踩过的坑。
- [agents/verification.md](./agents/verification.md)：声称完成前必须实际执行的验证。
- [agents/testing.md](./agents/testing.md)：测试策略、目录和必要覆盖。
- [agents/security.md](./agents/security.md)：密钥、权限、外发、不可逆操作。
- [agents/git.md](./agents/git.md)：分支、提交说明、PR 约定。
- [agents/decisions.md](./agents/decisions.md)：已做出的关键技术决策和理由。
- [agents/interfaces.md](./agents/interfaces.md)：对外接口与兼容性承诺。
- [agents/operations.md](./agents/operations.md)：部署、回滚、环境与运维。
- [agents/glossary.md](./agents/glossary.md)：领域术语。
- [agents/owners.md](./agents/owners.md)：模块责任人。

某项在本项目确实不存在时，保留文件，正文「填写」部分写「本项目暂无」，不要删文件或改名。
