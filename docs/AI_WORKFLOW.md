# AI-Assisted Development Workflow

**Purpose:** Use AI heavily while preserving the developer's understanding, ownership, and ability to explain the project.

## Source of Truth

The Git repository and its accepted documentation/code are the source of truth.

A chat conversation is not the authoritative project record.

## Recommended Roles

### Developer / Project Owner

The human developer:
- chooses product priorities,
- approves architecture,
- understands significant code,
- decides trade-offs,
- owns merges and releases.

### Lead Planning Chat

Use one main project chat for:
- roadmap,
- requirements,
- architecture discussions,
- reviewing alternatives,
- deciding what the next Issue should be,
- checking whether project documentation remains coherent.

The lead chat should not silently make major decisions. For meaningful choices it should:
1. explain the decision to be made,
2. present reasonable alternatives,
3. explain trade-offs,
4. obtain/record the developer's decision.

### Coding Agent / IDE Assistant

Use a coding tool (for example Codex or GitHub Copilot) for bounded implementation tasks such as:
- implement one approved Issue,
- write or improve tests,
- refactor a small area,
- diagnose a bug,
- review a diff,
- explain unfamiliar code.

Do not initially delegate broad prompts such as:
> Build the whole game.

Prefer:
> Implement FR-025 through FR-029 in the existing game engine. Do not change public APIs without explaining why. Add tests for each rule and summarize the changes.

## One Task at a Time

Before coding:
1. Choose an Issue or tightly defined task.
2. Confirm relevant requirements.
3. Create a branch.
4. Ask AI to plan the implementation if needed.
5. Implement.
6. Run tests.
7. Review the diff.
8. Commit.
9. Open/review a PR.
10. Merge when understood and accepted.

## AI Guardrails

AI should:
- read relevant project docs before making substantial changes,
- avoid changing requirements to make implementation easier,
- not choose a new dependency/framework without discussion,
- explain significant design choices,
- keep changes scoped,
- add/update tests where appropriate,
- point out uncertainty instead of inventing project rules.

## Understanding Rule

Before merging AI-generated code, the developer should be able to explain:
- what changed,
- why it changed,
- the main data/control flow,
- important trade-offs,
- what the tests prove.

This does not mean manually typing every line of code.

## Multiple Chats

Recommended structure:
- **1 lead project chat** — planning, requirements, architecture, next steps.
- **Optional short-lived specialist chats** — only when useful for a deep isolated topic, e.g. database design, UI critique, security review.

Important conclusions from specialist chats must be copied into the repository documentation or ADRs. They should not remain hidden only in a chat history.

## Agents

Agents are useful when they can operate on the actual repository, run commands/tests, inspect multiple files, and iterate.

Start conservatively:
- one agent,
- one branch,
- one bounded task,
- review the diff before merging.

Parallel agents become useful later when the repository is larger and tasks are genuinely independent. They are not required for the first CLI milestone.
