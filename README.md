# 标准 AGENTS.md 模板

这是一份跨项目复用的编码 Agent 说明骨架。新项目复制根目录的 `AGENTS.md` 和各功能文件夹，只填写各文件中标记为「填写」的部分，不要让 AI 重新生成整套结构。

## 为什么是这一套文件

行业与 Cursor 当前约定的自动加载文件名是 `AGENTS.md`（有 s）。Cursor、Codex 等会自动加载它。本模板只保留这一个入口，不再使用 `AGENT.md`。其余规则按功能归类到不同文件夹，避免每个项目、每个窗口各写一套，也避免把所有内容堆在单一文件或全部平铺在根目录。

官方说明：

- https://agents.md
- https://cursor.com/docs/rules

## 文件结构

- `AGENTS.md`：唯一入口，也是自动加载的总则。文档地图、阅读顺序和固定规则，所有项目保持一致。
- 功能文件夹：一份文件只承担一种职责，并按功能放进对应文件夹。某项不适用就写「本项目暂无」，不要删文件，也不要平铺到根目录。

文件夹划分：

- `project/`：`overview.md`、`repo-map.md`、`glossary.md`、`owners.md`
- `architecture/`：`architecture.md`、`decisions.md`、`interfaces.md`
- `development/`：`commands.md`、`constraints.md`、`conventions.md`、`testing.md`、`verification.md`、`git.md`
- `handoff/`：`progress.md`、`pitfalls.md`
- `operations/`：`security.md`、`operations.md`

## 新项目怎么用

1. 把 `AGENTS.md` 和上述五个功能文件夹一起放到仓库根目录。不要把职责文档平铺在根目录，也不要再创建 `AGENT.md`。
2. 只改各文件的「填写」部分。先填 `project/overview.md`、`project/repo-map.md`、`development/commands.md`、`development/constraints.md`、`development/verification.md`、`development/git.md`；其余没有内容的写「本项目暂无」。
3. `AGENTS.md` 的文档地图、阅读顺序和固定规则，以及各文件开头的「用途 / 何时阅读 / 规则」不要改，不要删标题，不要调换章节、文件或文件夹。
4. 每个需求开一个新的 Agent 窗口；窗口开始后先读根目录 `AGENTS.md`，再按阅读顺序读必读文件。若在子目录工作，再读离文件最近的那份 `AGENTS.md`。
5. 子项目需要不同约定时，在该目录再放一份增量 `AGENTS.md`，只写差异，不要复制根文件全文。更近的文件优先，用户在对话里的明确要求压过文档。
6. 任务结束后更新 `handoff/progress.md`；确认了新的踩坑点，再追加到 `handoff/pitfalls.md`。

## 这份文件不能保证什么

它能减少「每个窗口各写一套规则」造成的漂移，并要求改完必须跑通验证命令、回写进度和已确认的踩坑。它不能代替测试、审查和你对需求的确认。

## 不要做的事

- 不要每开一个项目就让 AI 从零再写一份 AGENT 文档。
- 不要把 README（给人看的）和 AGENTS.md（给 Agent 看的）混成一篇。
- 不要在功能开发任务里顺手改这套骨架的文件划分或章节结构。
- 不要再创建 `AGENT.md`，不要把职责文档平铺到仓库根目录。
- 不要把架构、进度、踩坑、约束重新写回 `AGENTS.md`。
