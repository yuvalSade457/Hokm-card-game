# Open Product & Design Decisions

**Status:** active  
This file contains questions that are intentionally **not decided yet**.

An open decision is not a bug and not a requirement. It is a question that must eventually be resolved before the relevant feature is implemented.

When a decision is made:
1. Record the conclusion and rationale.
2. Update the relevant requirements/rules/roadmap.
3. If the decision is architecturally significant, create an ADR.
4. Remove or mark the item resolved here.

---

## OD-001 — Digital Role of the Amal

**Question:**  
What meaningful role should the Amal have in the digital application when shuffling and dealing can be performed automatically by the system?

**Status:** Open.

---

## OD-002 — Chat Between Rounds

**Question:**  
Should players be able to chat between rounds?

**Status:** Open.

---

## OD-003 — Room Entry

How will four players find/join the same game?

**Status:** Open.

---

## OD-004 — Disconnect and Reconnect

What happens if a player disconnects during a game?

**Status:** Open.

---

## OD-005 — Turn Timing

Will turns have a timer?

**Status:** Open.

---

## OD-006 — Accounts vs Guest Play

Should players be allowed to play as guests, and when are accounts required?

**Status:** Open.

---

## OD-007 — Previous Trick Review Timeout

**Question:**  
Should viewing the immediately previous trick automatically end after a maximum duration?

**Already decided:**  
While a player is actively viewing the previous trick, the next trick cannot start.

**Still to decide:**
- Whether the review should have an automatic timeout at all.
- If yes, the maximum duration.
- Whether the timeout is per player or a single global review window.
- What happens if several players request the review at approximately the same time.
- Whether the duration should be configurable rather than hard-coded.

**Reason this is still open:**  
A value such as 10 seconds would currently be arbitrary. The exact timing should be chosen deliberately when the multiplayer interaction is designed.

**Status:** Open.
