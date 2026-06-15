# Development Plan

RepoMind OS should stay small until v0.1-alpha is usable in real repositories.
Do not expand indefinitely before the release pack is understandable,
deployable, startable, customizable, and dogfooded.

## P0 Release Pack

Purpose: make the project understandable and manually usable by an external
early user.

Scope:

- README explains RepoMind OS, current status, and minimal use flow.
- Quickstart shows how to start the first GPT window and use role packets.
- Development plan defines a finite path to v0.1-alpha.
- The starter governance loop can run with minimal roles.
- Users can import existing roles or generate project-specific roles after
  review and approval.
- Template files avoid secrets, private chat transcripts, and unsupported
  product claims.

## P1 Dogfood Test

Purpose: prove the governance loop works in one real repository.

Scope:

- Copy the template into a target repository.
- Run the Project Governor Bootstrap Window.
- Choose minimal setup or custom roles for that project.
- Prepare at least one Role Task Packet and Role Result Packet.
- Prepare one bounded Codex task prompt.
- Run validation and produce a final report.
- Decide whether any writeback is needed through the Writeback Protocol.

## P2 Optional Role Templates

Purpose: provide useful examples without turning RepoMind OS into a fixed role
catalog.

Scope:

- Refine role boundaries from dogfood evidence.
- Keep Project Governor and Repo Governor as recommended startup core roles.
- Treat other roles as optional templates or project-specific outputs.
- Support importing, splitting, merging, or rewriting user-provided roles.
- Add or revise role templates only when real repository use justifies them.
- Do not build a large built-in role library for completeness.

## P3 Examples

Purpose: make common flows easier to understand without adding automation.

Scope:

- Example first-window bootstrap transcript summary.
- Example Role Task Packet and Role Result Packet.
- Example Codex task prompt.
- Example writeback classification.

Examples must be generic and must not include secrets, private chat transcripts,
or project-specific confidential information.

## P4 Optional CLI

Purpose: consider lightweight tooling only after the manual workflow is proven.

Possible scope:

- Copy template files into a repository.
- Check required governance files exist.
- Validate packet and Codex prompt completeness.

This is optional. RepoMind OS v0.1-alpha must not depend on a CLI, cloud
service, or automatic GitHub integration.

## v0.1-alpha Completion Conditions

v0.1-alpha is complete when:

- README, quickstart, and development plan are clear enough for an external
  early user.
- The template can bootstrap a first GPT web window.
- The first window can ask about existing roles, prompts, context, preferences,
  and setup mode.
- A project can choose minimal setup or custom roles.
- Role Task Packet and Role Result Packet relay works manually.
- Prompt Architect can create concise, goal-oriented, verifiable Codex prompts.
- Codex can execute bounded repository file tasks without owning direction or
  bypassing approval.
- The writeback protocol is clear enough to preserve decisions, handoff,
  memory, and preferences without storing forbidden content.
- Dogfood testing has produced at least one completed governance loop.

## Non-Goals Before v0.1-alpha

- Large role libraries.
- Fixed mandatory role sets.
- Endless role-template expansion.
- Automatic repository mutation.
- CLI-first workflows.
- Cloud service behavior.
- Automatic GitHub issue, PR, or CI integration.
- Claims of stability or production readiness.
