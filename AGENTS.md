# AGENTS.md

给编码 Agent 的项目总则。人看 README，Agent 先看本文，再按阅读顺序打开同目录下的职责文档。

新开的 Agent 窗口必须先读完根目录这份文件，再读即将改动路径上最近的 `AGENTS.md`（如有），然后才改代码。每个需求单独开一个 Agent；本窗口只处理用户这一次提出的需求。

本文件是唯一入口。不要再创建 `AGENT.md`。项目细节写在同目录的各职责文档中，不要写回本文。本文只保留文档地图、阅读顺序和固定规则。所有使用本模板的项目保持这些部分一致：不要删、不要改标题、不要调换章节顺序、不要把填写内容写进本文。

## 文档地图

- [overview.md](./overview.md)：项目是什么、不是什么。
- [architecture.md](./architecture.md)：模块、边界、数据流、不变量。
- [repo-map.md](./repo-map.md)：目录和入口文件职责。
- [commands.md](./commands.md)：环境、安装、运行、构建、测试、检查命令。
- [constraints.md](./constraints.md)：行为约束和本项目特有限制。
- [conventions.md](./conventions.md)：本仓库代码写法。
- [progress.md](./progress.md)：当前任务进度、阻塞和下一步。
- [pitfalls.md](./pitfalls.md)：本仓库真实踩过的坑。
- [verification.md](./verification.md)：声称完成前必须实际执行的验证。
- [testing.md](./testing.md)：测试策略、目录和必要覆盖。
- [security.md](./security.md)：密钥、权限、外发、不可逆操作。
- [git.md](./git.md)：分支、提交说明、PR 约定。
- [decisions.md](./decisions.md)：已做出的关键技术决策和理由。
- [interfaces.md](./interfaces.md)：对外接口与兼容性承诺。
- [operations.md](./operations.md)：部署、回滚、环境与运维。
- [glossary.md](./glossary.md)：领域术语。
- [owners.md](./owners.md)：模块责任人。

某项在本项目确实不存在时，保留文件，正文「填写」部分写「本项目暂无」，不要删文件或改名。不要把这些文件放进子文件夹。

---

## 阅读顺序

### 每次开工必读

1. 本文
2. `overview.md`
3. `constraints.md`
4. `progress.md`
5. `pitfalls.md`

### 按任务选读

先看将要改动的代码，再读与本次改动相关的文件。不要把所有职责文档逐份精读一遍。

- 改结构或跨模块行为：`architecture.md`、`interfaces.md`、`decisions.md`
- 找不到文件或入口：`repo-map.md`
- 要安装、运行或复现：`commands.md`、`testing.md`
- 写代码：`conventions.md`
- 涉及密钥、权限、外发、生产数据：`security.md`
- 要提交或开 PR：`git.md`
- 涉及部署或环境：`operations.md`
- 术语不清：`glossary.md`
- 需要找人确认：`owners.md`

### 结束前必做

1. 按 `verification.md` 把相关命令真正跑完。
2. 更新 `progress.md` 里自己负责任务的状态。
3. 若本次确认了新的踩坑点，追加到 `pitfalls.md`。
4. 只有在命令、目录、约束或验证方式确实变了，或用户明确要求时，才改对应职责文档里的填写内容。

---

## 固定规则

### 1. 开工前

1. 读根目录 `AGENTS.md`，以及工作路径上更近的 `AGENTS.md`。近的优先；用户当次对话里的明确要求压过文档。
2. 用自己的话复述本次需求的范围和验收标准。先对照 `progress.md`，避免重复已完成的工作；先对照 `pitfalls.md`，避免再踩已记录的坑。范围不清时先问一句，不要扩大任务。
3. 先读将改动的代码和现有测试，再动手。不要猜测不存在的 API、文件或配置。

### 2. 改动时

1. 只做本次需求。不顺手重构、不顺便升级依赖、不清理无关文件。
2. 遵循 `constraints.md`、`conventions.md` 和仓库现有写法。新写法与旧写法冲突时，跟现有代码，不要另起风格。
3. 不要提交密钥、令牌、证书和本地绝对路径。不要改 `.env`、密钥文件，除非用户明确要求。细节见 `security.md`。
4. 不要改生成目录（如 `dist`、`build`、`out`、`.next`）里的文件。
5. 不要为了「更完整」重写或扩写本套文档的结构、文件名或章节顺序。不要自行把职责文档放进子文件夹，不要再创建 `AGENT.md`，也不要自行拆出新的 Agent 文档，除非用户明确要求改这套骨架。

### 3. 结束前

1. 按 `verification.md` 把相关命令真正跑完。失败就修，直到通过，或明确写出失败原因和已尝试的步骤。
2. 没跑过的检查，不要写成已经通过。
3. 交付时说明：改了什么、怎么验证、还有什么没做。
4. 更新 `progress.md`。有新的已确认踩坑点时，追加到 `pitfalls.md`。

### 4. 子项目

单仓多包时，在子目录放增量 `AGENTS.md`，只写与根目录不同的命令和约定，并链接该子项目需要覆盖的职责文档。不要把根文件全文复制过去。

### 5. 进度与踩坑

1. `progress.md` 只记录真实状态。不要把计划写成已完成。不要删除或改写他人进行中的条目，只能更新自己负责的任务。
2. `pitfalls.md` 只追加本仓库真实遇到、且已确认的问题。不要写入通用编程建议或尚未验证的猜测。更正旧条目时保留原记录，在下方追加更正。

### 6. 文档维护

1. 填写内容只写在各职责文档的「填写」部分。各文件开头的「用途 / 何时阅读 / 规则」不要改。
2. 某项不适用时，在「填写」部分写「本项目暂无」，不要删文件、不要改文件名、不要改章节标题、不要把文件移进子文件夹。
3. 不要把 README（给人看的）和本套 Agent 文档混成一篇。
