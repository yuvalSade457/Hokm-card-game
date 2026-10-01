# Architecture Decision Records (ADRs)

An **Architecture Decision Record (ADR)** is a short document that records an important technical decision and why it was made.

The goal is not bureaucracy. The goal is to preserve the reasoning that would otherwise disappear after a few weeks.

## When to Create an ADR

Use an ADR for decisions that:
- significantly shape the architecture,
- are difficult/costly to reverse,
- affect multiple parts of the system,
- involve meaningful alternatives/trade-offs.

Examples for this project may include:
- programming language and primary backend/runtime,
- client/server state ownership,
- real-time communication approach,
- persistence/database choice,
- authentication strategy.

Do **not** create an ADR for every small coding decision.

## Numbering

Use sequential files:

- `0001-initial-language-and-runtime.md`
- `0002-server-authoritative-game-state.md`
- `0003-realtime-transport.md`

## Status Values

Typical values:
- Proposed
- Accepted
- Superseded
- Rejected
