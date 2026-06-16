# RepoMind OS

RepoMind OS 是一个可以嵌入软件仓库的 AI 治理启动模板。它不是自动运行的 agent runtime（智能体运行时），而是一套复制即用的项目协作协议，帮助用户和 AI 在仓库中管理项目角色、上下文、规则、偏好和回写机制。

它的目标是让项目 AI 状态可恢复、可审查、可控制：即使 GPT 网页窗口丢失上下文或被删除，也可以通过重新读取仓库中的治理文件恢复工作状态。

RepoMind OS 不是固定多角色框架。它只提供一个小型治理内核和启动协议；每个项目自己决定需要哪些角色、规则和协作方式。

## 它解决什么问题

- GPT 网页窗口失忆：重要项目状态不只保存在聊天记录里，而是写入仓库文件。
- 灵活 AI 协作：用户可以使用最小设置，也可以导入已有角色、prompt、项目笔记或工作习惯，再由 AI 按项目需要生成自定义角色。
- Codex 越权风险：Codex 任务必须明确 allowed files（允许修改文件）、forbidden files（禁止修改文件）、validation（验证命令）、commit rules（提交规则）和 stop conditions（停止条件）。
- 上下文回写：重要决策、交接状态、用户偏好和可复用经验可以通过可审查协议写回仓库。

## 当前状态

RepoMind OS 目前是 `v0.1-alpha candidate` / `pre-alpha` 模板。它已经可以用于手动试跑，但还不是稳定框架，也不应被理解为完整自动化系统。

当前没有 CLI、云服务、后台 agent，也没有自动 GitHub 集成。

## 3 步开始使用

1. 把 `template/.ai-governance/` 复制到你的项目根目录。
2. 如果有需要，把 `template/AGENTS.md` 复制或合并到你的项目根目录。
3. 打开 GPT 网页窗口，按照 `docs/quickstart.md` 启动。

第一个 GPT 窗口可以使用这句简短启动语：

```text
请读取 `.ai-governance/BOOT.md`，并继续执行 first-window bootstrap flow（第一窗口启动流程）。
不要停在总结 BOOT.md。请直接询问初始 bootstrap 问题。
```

`template/.ai-governance/START_HERE.md` 是可选辅助文件，只是给想要更短启动说明的用户看的清单。它不是 runtime entrypoint（运行时入口）。

## 灵活角色模型

RepoMind OS 不要求使用固定角色集合。

你可以：

- 从 minimal governance（最小治理）开始，不创建额外专家角色；
- 使用 Project Governor / Repo Governor 作为推荐启动核心；
- 导入已有角色、prompt、项目笔记或工作习惯；
- 让 Project Governor 评估并提出项目专属角色；
- 在使用前拆分、合并、重写或拒绝角色提案；
- 只使用当前项目需要的协议。

角色文件是可持久化的工作指令，不是固定产品分类。只创建项目真正需要、且用户明确批准的角色。

## 最小使用流程

1. 把 `template/` 里的内容复制到目标项目根目录，使目标项目拥有 `.ai-governance/` 目录。
2. 打开一个新的 GPT 网页窗口。
3. 让 GPT 先读取 `.ai-governance/BOOT.md`，并继续执行 first-window bootstrap flow（第一窗口启动流程）。
4. 根据项目情况和已有上下文，选择 minimal setup（最小设置）或 custom roles（自定义角色）。
5. 在完成启动流程前，不要让 Codex 或专家角色修改仓库文件。

第一个 GPT 窗口应该先识别项目目的、评估可用上下文、只提出必要角色、请求用户批准长期治理变更，然后再路由有边界的执行任务。

## 仓库结构

- `template/.ai-governance/BOOT.md`：启动协议。
- `template/.ai-governance/CONTEXT_INDEX.md`：上下文读取路由表。
- `template/.ai-governance/roles/`：角色模板和已批准角色说明。
- `template/.ai-governance/prompts/`：任务包、结果包和 Codex prompt 模板。
- `template/.ai-governance/handoff/`、`memory/`、`decisions/`：项目交接、经验和决策状态。

## 安全说明

- 不要把 secrets、token、API key、原始私密聊天记录或不必要的个人信息写进治理文件。
- 不要让 Codex 修改任务 allowed files 之外的文件。
- 不要把旧聊天总结当成已验证项目事实，除非有仓库证据或用户明确确认。
- 当前还没有选择开源许可证；公开复用或再分发前需要选择 license。
