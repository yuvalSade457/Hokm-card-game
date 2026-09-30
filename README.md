# Card Game Project

> Working title. The final product/game name has not been chosen yet.

## Vision

Build a portfolio-quality implementation of a four-player team card game, progressing from a small, testable game engine to a deployed real-time multiplayer web application.

The project is intentionally developed in stages so that each architectural decision and capability can be understood, tested, and explained.

## Current Status

**Phase 0 — Specification & Project Setup**

At this stage:
- The core game rules are defined.
- Core software requirements are being extracted from the rules.
- Product questions that are not yet decided are tracked separately.
- The technology stack and final architecture are intentionally **not yet selected**.

## Documentation

- [`docs/GAME_RULES.md`](docs/GAME_RULES.md) — authoritative description of the game rules.
- [`docs/REQUIREMENTS.md`](docs/REQUIREMENTS.md) — testable software requirements derived from the rules.
- [`docs/ROADMAP.md`](docs/ROADMAP.md) — staged development plan.
- [`docs/OPEN_DECISIONS.md`](docs/OPEN_DECISIONS.md) — unresolved product/design questions.
- [`docs/AI_WORKFLOW.md`](docs/AI_WORKFLOW.md) — rules for using AI during development.
- [`docs/adr/`](docs/adr/) — Architecture Decision Records for important technical decisions.

## Development Principles

1. The Git repository is the source of truth.
2. Development is incremental; each milestone should leave the project in a working state.
3. Important architectural decisions are discussed before implementation and recorded when appropriate.
4. AI assists with planning, review, implementation, and testing; it does not silently make major product or architecture decisions.
5. Core game logic should remain independent from the user interface as far as practical.
6. Tests are added alongside rule implementation rather than being postponed until the end.

## Planned High-Level Milestones

1. Specification and repository setup.
2. Core game engine + CLI harness.
3. Local web UI.
4. Public deployment.
5. Real-time multiplayer.
6. Accounts and persistence.
7. Security, UX improvements, and portfolio polish.

See [`docs/ROADMAP.md`](docs/ROADMAP.md) for details.

## Git Workflow

Initial recommendation:

- `main` should remain in a working state.
- Work is done on short-lived branches such as:
  - `feature/game-engine`
  - `feature/trick-validation`
  - `feature/cli-game`
  - `fix/trump-resolution`
- A meaningful change should normally be associated with an Issue and merged through a Pull Request.
- Tags/releases can mark portfolio milestones such as:
  - `v0.1-cli`
  - `v0.2-web`
  - `v0.3-multiplayer`

A separate `develop` branch is not required at the beginning of a single-developer project.

## Technology Stack

**TBD.**

The stack should be selected only after the initial requirements, product scope, and first architectural decisions are reviewed.
