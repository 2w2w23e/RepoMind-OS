# Quickstart

This is the 5-minute path for trying RepoMind OS in a repository.

RepoMind OS starts from a minimal governance setup. It does not require a fixed
role set; custom roles are created only when the project and user justify them.

## 1. Copy The Template

Copy the contents of `template/` into the root of your target project.

After copying, the target project should contain:

```text
.ai-governance/BOOT.md
.ai-governance/CONTEXT_INDEX.md
.ai-governance/roles/
.ai-governance/prompts/
```

## 2. Start The First GPT Window

Open a new GPT web window and paste this startup prompt:

```
You are the Project Governor Bootstrap Window for this repository.

Read `.ai-governance/BOOT.md` first, then use
`.ai-governance/CONTEXT_INDEX.md` to select the minimum additional context.
If this is the first GPT window for the project, follow
`.ai-governance/FIRST_WINDOW_PROTOCOL.md`.

Do not write implementation code.
Do not ask Codex to modify files yet.
```

The first window should become the Project Governor Bootstrap Window. It should
not immediately create roles, ask Codex to code, or turn old chat summaries into
project truth.

## 3. Complete Bootstrap

The Project Governor should:

- ask whether the user wants minimal setup or custom roles;
- ask whether existing roles, prompts, context, or preferences should be
  imported and evaluated;
- identify project purpose, maturity, constraints, users, and immediate goal;
- classify available context as verified, unverified, stale, or missing;
- propose only roles justified by the repository and user intent;
- use Repo Governor review or a limited repository audit before durable role
  changes;
- ask the user to approve role creation, role changes, project-state updates,
  and major direction decisions.

Minimal setup means the first window can keep governance lightweight, using the
core protocols and only the roles needed to route decisions and safe execution.
Custom roles can be imported, rewritten, split, merged, or generated after
review.

## 4. Open A Specialist Role Window

When the Project Governor wants another role to work, it prepares a Role Task
Packet using:

```
.ai-governance/prompts/role_task_packet.md
```

Open a new GPT window for the target role and paste a prompt like:

```
You are the <ROLE NAME> for this repository.

Read `.ai-governance/BOOT.md`, `.ai-governance/CONTEXT_INDEX.md`, your role
file under `.ai-governance/roles/`, and the Role Task Packet below.

Do not assume hidden chat history.
Do not edit repository files from this role window.
Return a Role Result Packet using `.ai-governance/prompts/role_result_packet.md`.

<paste Role Task Packet here>
```

## 5. Run A Codex Task

Use Codex only after the task is approved and bounded.

## 6. Use Writeback When Needed

Use `.ai-governance/WRITEBACK_PROTOCOL.md` when durable state must be stored.

Writeback is not needed for every message. Keep it minimal and verified.

## 7. Mandatory First Window Behavior

The first GPT window MUST NOT stop after summarizing BOOT.md.
It must actively enter bootstrap mode:

- detect first-window vs existing-session state;
- ask whether user has existing roles/context/preferences;
- proceed into FIRST_WINDOW_PROTOCOL if first window;
- output next actionable bootstrap step instead of waiting passively.
