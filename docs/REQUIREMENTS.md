# Software Requirements

**Status:** v0.2  
**Scope: Agreed software requirements derived from core game rules and resolved product decisions.
Important:** Undecided product behavior must remain in `OPEN\_DECISIONS.md` until a decision is made.

## Requirement ID Policy

Requirement IDs are **stable identifiers, not sequence numbers**.

Format:

* `FR-<AREA>-NNN` — Functional Requirement
* `NFR-<AREA>-NNN` — Non-Functional Requirement

Examples:

* `FR-ACES-003`
* `FR-HISTORY-004`
* `NFR-SEC-001`

Rules for maintaining IDs:

1. Never renumber existing requirements merely because a requirement is inserted, moved, or removed.
2. Add a new requirement using the next unused ID within the relevant area.
3. Do not reuse an ID that belonged to a removed requirement.
4. If a requirement is removed after development has begun, record it in a retired/deprecated section rather than silently reusing its ID.
5. Small wording clarifications keep the same ID. A materially different requirement should normally receive a new ID and supersede the old one.

This keeps references from tests, Issues, Pull Requests, commits, and ADRs stable over time.

\---

## Players, Seats, and Teams

**FR-SEAT-001**  
The system shall model exactly four player seats in a game.

**FR-SEAT-002**  
The system shall model the four seats as positions in a circle with clockwise ordering.

**FR-SEAT-003**  
The system shall support two teams of two players, with partners occupying diagonal seats.

## Deck and Ranking

**FR-DECK-001**  
The system shall use exactly 52 standard playing cards with no jokers.

**FR-DECK-002**  
Within a suit, the system shall rank cards from Ace high to 2 low.

## Aces Procedure

**FR-ACES-001**  
At the start of a full game, the system shall perform the Aces procedure before normal round play.

**FR-ACES-002**  
The first four cards dealt during the Aces procedure shall not count toward team selection.

**FR-ACES-003**  
If three or four of the first four cards dealt during the Aces procedure are Aces, the system shall collect the dealt cards, reshuffle the complete deck, and restart the Aces procedure from the beginning.
**FR-ACES-004**  
Starting from the fifth card, the first player to receive an Ace shall become the Kem.

**FR-ACES-005**  
After the Kem is determined, the Aces procedure shall continue clockwise among the remaining players, skipping the Kem.

**FR-ACES-006**  
The next remaining player to receive an Ace shall become the Kem's partner.

**FR-ACES-007**  
The remaining two players shall form the opposing team.

**FR-ACES-008**  
After any seating adjustment required by the Aces procedure is complete, the Amal shall be the player immediately to the right of the Kem.
**FR-ACES-009**

Once both teams have been determined, the Kem shall remain in the same seat. If the Kem's partner is not already seated diagonally opposite the Kem, the system shall swap the Kem's partner with the player currently seated opposite the Kem.
**FR-ACES-010**

After the Aces procedure is complete, the system shall collect all 52 cards and reshuffle the complete deck before dealing the first round.

## Round Deal

**FR-DEAL-001**  
At the start of a round, the system shall deal starting from the Kem and continue clockwise.

**FR-DEAL-002**  
The deal shall be performed in packets of 5, then 4, then 4 cards per player.

**FR-DEAL-003**  
Each player shall have exactly 13 cards after the deal is complete.

## Visibility and Hook Selection

**FR-VIS-001**  
Before Hook selection, the Kem shall be able to view only the first 5 cards dealt to the Kem.

**FR-VIS-002**  
Before Hook selection, the Kem's partner shall not be able to view their cards.

**FR-VIS-003**  
Before Hook selection, both opposing players shall be allowed to view all cards already dealt to them.

**FR-VIS-004**  
The Kem shall be allowed to select any of the four suits as the Hook, including a suit not present in the Kem's first five cards.

**FR-VIS-005**  
After the Hook is selected, the Kem and the Kem's partner shall be allowed to view their full hands.

**FR-VIS-006**  
The selected Hook shall remain unchanged for the duration of the round.
**FR-VIS-007**

Once the Kem has received the first 5 cards, the Kem shall be allowed to declare the Hook while the remaining cards are still being dealt.

## Trick Play

**FR-PLAY-001**  
The Kem shall lead the first trick of every round.

**FR-PLAY-002**  
Players shall play in clockwise order.

**FR-PLAY-003**  
A player who holds at least one card of the lead suit shall be required to play a card of that suit.

**FR-PLAY-004**  
A player following suit shall not be required to play a card that beats cards already played.

**FR-PLAY-005**  
A player who does not hold the lead suit shall be allowed to play a Hook card.

**FR-PLAY-006**  
A player who does not hold the lead suit shall be allowed to play a non-Hook card even when the player holds a Hook card.

**FR-PLAY-007**  
A player shall not be required to overtrump a Hook card already played.

## Trick Resolution

**FR-TRICK-001**  
If no Hook is played in a trick, the highest card of the lead suit shall win.

**FR-TRICK-002**  
If one or more Hook cards are played, the highest Hook card shall win.

**FR-TRICK-003**  
The player who wins a trick shall lead the next trick.

## Previous Trick Review

**FR-HISTORY-001**  
After a trick ends and before the next trick begins, any player shall be allowed to view the four cards from the immediately previous trick.

**FR-HISTORY-002**  
After the next trick begins, the previous trick shall no longer be viewable.

**FR-HISTORY-003**  
The system shall not provide access to tricks older than the immediately previous trick through this rule.

**FR-HISTORY-004**  
While any player is actively viewing the immediately previous trick, the system shall not allow the next trick to start.

> The maximum viewing duration is intentionally not specified yet. See `OD-007` in `OPEN\_DECISIONS.md`.

## Round Scoring

**FR-SCORE-001**  
The first team to win 7 tricks shall immediately win the round.

**FR-SCORE-002**  
The round shall end as soon as one team reaches 7 tricks, even if cards remain unplayed.

**FR-SCORE-003**  
A normal round win shall award 1 point.

**FR-SCORE-004**  
A 7–0 win by the Kem's team shall award 2 points.

**FR-SCORE-005**  
A 7–0 win by the non-Kem team shall award 3 points.

## Role Transition

**FR-ROLE-001**  
If the Kem's team wins a round, the Kem and Amal roles shall remain unchanged for the next round.

**FR-ROLE-002**  
If the non-Kem team wins a round, the player immediately to the left of the current Kem shall become the new Kem.

**FR-ROLE-003**  
When the non-Kem team wins a round, the previous Kem shall become the new Amal.

**FR-ROLE-004**  
Teams shall remain fixed throughout a full game.

## Full Game

**FR-GAME-001**  
The system shall accumulate team points across rounds.

**FR-GAME-002**  
The full game shall end immediately when a team reaches 7 or more points.

**FR-GAME-003**  
A new full game shall perform a new Aces procedure.

## Non-Functional / Security Requirements

**NFR-SEC-001 — Hidden information**  
A player must not be able to obtain card information that the game rules do not currently authorize that player to see.

**NFR-SEC-002 — Client exposure**  
In a multiplayer architecture, hidden opponent cards should not be sent to an unauthorized client merely to be hidden by the UI.

**NFR-TEST-001 — Rule testability**  
Core game-rule logic should be structured so that legal moves, trick resolution, role transitions, and scoring can be tested without requiring a graphical interface.

## Retired / Superseded Requirements

None yet.

## Not Yet Requirements

The following are intentionally not specified here yet because they are product/architecture decisions rather than agreed rules:

* Exact timeout/auto-close behavior when viewing the previous trick.
* Chat between rounds.
* Exact digital purpose of the Amal.
* Turn timers.
* Disconnect/reconnect behavior.
* Room creation/join flow.
* Authentication details.
* Persistent statistics.
* Matchmaking.
* Spectators.

These belong in `OPEN\_DECISIONS.md` until resolved.

