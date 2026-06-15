# Role Creation Protocol

## Purpose

Roles are durable operating instructions for AI participants in the project.
They should be created only when the project needs them and when their scope is
clear.

## State Machine

Every proposed role follows this state machine:

```text
UNASSESSED
  -> PROJECT_GOVERNOR_RECOMMENDED
  -> REPO_GOVERNOR_REVIEWED
  -> USER_APPROVED / USER_REJECTED / USER_REQUESTED_CHANGES
  -> CREATED
  -> ACTIVE
  -> DEPRECATED / MERGED / SPLIT
```

If the user rejects a role, no role file is created.
If the user requests changes, return to Project Governor discussion and revise
the role proposal before another review.

## Responsibilities

- Project Governor: identifies role needs, drafts role proposals, and explains
  why each role is necessary.
- Repo Governor: audits the proposal against repository reality, existing
  conventions, active risks, and overlap with other roles.
- User: owns final approval. No role file may be created without explicit user
  approval.

## Proposal Requirements

Before user approval, a role proposal must include:

- role name;
- purpose;
- scope and non-scope;
- expected inputs;
- expected outputs;
- authority limits;
- files it may read or update;
- interaction with Codex and other roles;
- overlap risks;
- activation criteria;
- deprecation, merge, or split criteria.

## State Definitions

- `UNASSESSED`: a possible role has been mentioned but not evaluated.
- `PROJECT_GOVERNOR_RECOMMENDED`: the Project Governor has proposed the role.
- `REPO_GOVERNOR_REVIEWED`: repository reality has been audited.
- `USER_APPROVED`: the user approved creation.
- `USER_REJECTED`: the user rejected creation.
- `USER_REQUESTED_CHANGES`: the user requested revision before approval.
- `CREATED`: the role file exists.
- `ACTIVE`: the role is approved for use in live work.
- `DEPRECATED`: the role remains for history but should not be used for new work.
- `MERGED`: the role has been combined into another role.
- `SPLIT`: the role has been divided into more specific roles.

## Creation Rules

- Do not create a role file before `USER_APPROVED`.
- Do not create roles merely because a template exists.
- Do not create duplicate roles with overlapping authority unless the overlap is
  explicit and approved.
- Do not let Codex create role files unless the role proposal has already been
  approved by the user.
- After creation, the role becomes `ACTIVE` only when the user accepts the file
  contents or the bootstrap flow explicitly activates it.

## Revision Rules

- User disagreement returns the process to Project Governor discussion.
- Repository audit concerns must be resolved or explicitly accepted by the user.
- Role splits and merges are role changes and require the same approval standard.
- Deprecated roles should remain readable unless the user explicitly requests
  deletion.
