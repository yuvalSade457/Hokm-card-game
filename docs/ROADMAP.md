# Development Roadmap

**Status:** v0.1  
This is a staged plan, not a fixed contract. Each phase should end with a usable, explainable milestone.

## Phase 0 — Specification & Repository Setup

Goals:
- Establish GitHub repository.
- Add README and project documentation.
- Finalize core game rules.
- Extract testable requirements.
- Track unresolved product decisions.
- Decide initial Git workflow.
- Discuss architecture and technology choices without prematurely implementing them.

Deliverable:
- A clean repository that explains what is being built and how decisions will be made.

## Phase 1 — Core Game Engine + CLI Harness

Goals:
- Model cards, suits, players/seats, teams, roles, deck, rounds, tricks, and scoring.
- Implement legal move validation.
- Implement Hook selection.
- Implement trick resolution.
- Implement round and full-game scoring.
- Build a simple CLI harness in which one human can act as all four players.

Testing:
- Add automated unit tests alongside the rule engine.
- Use the CLI for exploratory/end-to-end manual play.
- Use unit tests for precise repeatable rule cases.

Deliverable:
- A fully playable local CLI version whose core game logic does not depend on a web UI.

Suggested release:
- `v0.1-cli`

## Phase 2 — Local Web UI

Goals:
- Add a basic graphical card-table interface.
- Reuse the existing game engine rather than rewriting the rules inside the UI.
- Support local/single-machine play for development and demonstration.
- Keep visuals simple; correctness matters more than polish.

Deliverable:
- A locally running web application with basic graphics.

Suggested release:
- `v0.2-web-local`

## Phase 3 — First Public Deployment

Goals:
- Deploy the web application to a public URL.
- Establish a repeatable build/deployment process.
- Verify configuration and environment handling.

Important:
- Public deployment does not yet imply true four-device multiplayer.

Deliverable:
- A public demo URL for the current version.

## Phase 4 — Real-Time Multiplayer

Goals:
- Allow four people on separate devices to participate in the same game.
- Define server-authoritative game state.
- Synchronize actions and state.
- Enforce information privacy.
- Define room creation/join flow.
- Handle basic invalid actions and network timing.

Likely product decisions to resolve before/during this phase:
- Room codes/links.
- Reconnection behavior.
- Turn timeout behavior.
- Amal's digital role.

Deliverable:
- Four real players can complete a game from separate devices.

Suggested release:
- `v0.3-multiplayer`

## Phase 5 — Accounts & Persistence

Goals:
- Add authentication if still justified.
- Store users and relevant persistent data.
- Decide what game history/statistics should be stored.
- Introduce a database based on actual persistence requirements.

Deliverable:
- Persistent user experience rather than anonymous temporary sessions only.

## Phase 6 — Security, Reliability & UX

Goals:
- Review authorization and hidden-card exposure.
- Harden reconnect and concurrency behavior.
- Improve error handling.
- Add logging/observability where useful.
- Improve accessibility and responsive design.
- Refine visuals and interactions.
- Consider optional social features such as between-round chat.

## Phase 7 — Portfolio Polish

Goals:
- High-quality README.
- Architecture overview/diagram.
- Clear setup instructions.
- Screenshots or short demo.
- Meaningful release history.
- Tests and CI visible in the repository.
- ADRs for major technical decisions.
- Document interesting engineering challenges and trade-offs.

Deliverable:
- A project that can be demonstrated and discussed confidently in interviews.

## Ongoing Across All Phases

These are not separate end-stage tasks:

- Automated tests for core rules and regressions.
- Small branches and understandable commits.
- Issues for meaningful work.
- Pull Requests even when self-reviewing important changes.
- Documentation updates when an accepted decision changes project behavior.
- AI-assisted review without delegating ownership of key decisions.
