# RepoMind OS

RepoMind OS is an embeddable AI governance starter for software repositories.
It is a copy-and-start template that helps users and AI collaborators define
project-specific roles, context, rules, preferences, and writeback mechanisms
inside a repository.

The goal is recoverability and controlled execution: a GPT web window may lose
context or be deleted, but the project's AI operating state can be restored by
reading the governance files again.

RepoMind OS is not a fixed multi-role framework and not an automatic agent
runtime. It provides a small governance kernel and starter protocols; each
project decides which roles and rules are actually needed.

## What It Helps With

- GPT web window memory loss: important project state lives in files, not only
  in chat history.
- Flexible AI collaboration: users may use a minimal setup, import existing
  roles or prompts, generate project-specific roles, or use only selected
  protocols.
- Codex overreach: Codex tasks must name allowed files, forbidden files,
  validation, commit rules, and stop conditions.
- Context writeback: useful decisions, handoff state, preferences, and lessons
  can be written back through a reviewable protocol.

## Current Status

RepoMind OS is a `v0.1-alpha candidate` / `pre-alpha` template. It is usable for
manual trial runs, but it is not a stable framework and should not be treated as
complete automation.

It does not currently provide a CLI, cloud service, background agent, or
automatic GitHub integration.

## Use It In 3 Steps

1. Copy `template/.ai-governance/` into your project root.
2. If useful, copy or merge `template/AGENTS.md` into your project root.
3. Open a GPT web window and follow `docs/quickstart.md`.

For the first window, the short instruction is:

```text
Read `.ai-governance/BOOT.md` and continue the first-window bootstrap flow.
Do not stop at a summary. Ask the initial bootstrap questions.
```

`template/.ai-governance/START_HERE.md` is an optional helper for users who want
a shorter first-window checklist. It is not a runtime entrypoint.

## Flexible Role Model

RepoMind OS does not require a standard role set.

You can:

- start with minimal governance and no extra specialist roles;
- use Project Governor / Repo Governor as the recommended startup core;
- import existing roles, prompts, project notes, or working habits;
- ask the Project Governor to evaluate and propose project-specific roles;
- split, merge, rewrite, or reject role proposals before they are used;
- use only the protocols that fit the current project.

Role files are durable instructions, not a product taxonomy. Create only the
roles that the project actually needs and the user approves.

## Minimal Use Flow

1. Copy the contents of `template/` into the root of your project so the project
   has a `.ai-governance/` directory.
2. Open a new GPT web window.
3. Ask GPT to read `.ai-governance/BOOT.md` first and continue the first-window
   bootstrap flow.
4. Choose minimal setup or custom roles based on the project and any existing
   prompts or context.
5. Follow the bootstrap flow before asking Codex or specialist roles to modify
   repository files.

The first GPT window should identify project purpose, assess available context,
propose only necessary roles, request user approval for durable governance
changes, and route bounded implementation tasks only after approval.

## Repository Layout

- `template/.ai-governance/BOOT.md`: startup protocol.
- `template/.ai-governance/CONTEXT_INDEX.md`: context routing table.
- `template/.ai-governance/roles/`: role templates and approved role
  instructions.
- `template/.ai-governance/prompts/`: packet and task templates.
- `template/.ai-governance/handoff/`, `memory/`, and `decisions/`: durable
  project coordination state.

## Safety Notes

- Do not store secrets, tokens, API keys, raw private chat transcripts, or
  unnecessary personal information in governance files.
- Do not let Codex edit files outside the task's allowed file list.
- Do not treat old chat summaries as verified project facts without repository
  evidence or explicit user confirmation.
- License selection is not included yet; choose a license before public reuse or
  redistribution.
