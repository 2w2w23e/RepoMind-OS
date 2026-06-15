# Global User Preferences

Use this file for cross-project user preferences that should apply broadly
across RepoMind OS roles and future repositories.

Do not store project facts, secrets, private chat transcripts, or temporary task
instructions here.

## Entry Template

```text
- scope: USER_GLOBAL_PREFERENCE
- rule: <reusable preference>
- source: <user confirmation summary, not raw chat>
- status: active | needs_review | superseded | rejected
- applies_to: <all roles or broad task class>
- example: <short generic example>
- revisit_trigger: <when to review or remove>
```

## Example Entries

```text
- scope: USER_GLOBAL_PREFERENCE
- rule: Prefer the user's requested response language for final answers.
- source: Example only.
- status: needs_review
- applies_to: all roles
- example: If the user asks in Chinese, answer in Chinese unless the task needs English text.
- revisit_trigger: User asks for a different language policy.

- scope: USER_GLOBAL_PREFERENCE
- rule: Command names, file names, code identifiers, and API names may stay in English.
- source: Example only.
- status: needs_review
- applies_to: all roles
- example: Keep `git status`, `README.md`, and function names unchanged.
- revisit_trigger: User asks for localized technical naming.
```

## Active Entries

```text
- scope: USER_GLOBAL_PREFERENCE
- rule: After completing repository changes, commit them and push the current branch unless the user explicitly says not to.
- source: User explicitly requested future direct commit and upload.
- status: active
- applies_to: Codex repository-change tasks
- example: After editing governance docs, create a commit and push to the tracked remote branch.
- revisit_trigger: User asks to review before commit, avoid push, or keep changes local.
```
