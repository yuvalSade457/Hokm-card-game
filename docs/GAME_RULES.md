# Game Rules

**Status:** v0.1 — core rules agreed  
**Purpose:** This document is the authoritative description of the game itself. Product/UI decisions that are not game rules belong elsewhere.

## 1\. General Structure

The game is played by exactly four players using a standard 52-card deck with no jokers.

The four players sit **in a circle** and are divided into two fixed teams. Partners sit diagonally opposite one another in the circle.

The game has three levels:

* **Trick** — four cards, one played by each player.
* **Round / Gamelet** — the first team to win 7 tricks wins the round.
* **Full Game** — the first team to reach 7 or more points wins the full game.

A Hand is the set of cards currently held by a player.
A normal round win is worth 1 point. A 7–0 round can be worth 2 or 3 points as described below.

## 2\. Card Ranking

Within every suit, cards rank from strongest to weakest:

A, K, Q, J, 10, 9, 8, 7, 6, 5, 4, 3, 2.

In every round, one suit is selected as the **Hook** (trump suit).

Any Hook card beats any card from a non-Hook suit. Therefore, even the 2 of Hook beats an Ace of another suit.

## 3\. "Aces" — Choosing Teams and Initial Roles

At the beginning of a full game, the players perform the **Aces** procedure.

Cards are dealt one at a time clockwise.

The first four cards — one card to each player — do not count for choosing the Aces.

If an Ace appears among these first four cards, it is ignored.

### Special case: three or four initial Aces

If three or four of the first four cards are Aces:

* collect all dealt cards,
* reshuffle the complete deck,
* restart the Aces procedure from the beginning.

Starting with the fifth dealt card, Aces count.

The first player to receive a counted Ace becomes the **Kem**.

Once a player receives that Ace, cards are no longer dealt to that player. Dealing continues clockwise among the remaining three players, skipping the Kem.

The next remaining player to receive an Ace becomes the Kem's partner.

The two players who received the counted Aces form one team. The other two players form the second team.

The Kem remains in the same seat.

If the Kem's partner is not already seated diagonally opposite the Kem, the Kem's partner swaps seats with the player currently seated opposite the Kem.

After this adjustment, partners sit diagonally opposite each other in the circle.

The player immediately to the **right of the Kem** is the **Amal**.

In the physical game, the Amal is responsible for shuffling and dealing.

After the Aces procedure:

* collect all cards,
* reshuffle the complete deck,
* begin the first round.

The Aces procedure happens only at the start of a full game. It is not repeated between rounds.

## 4\. Dealing a Round

At the start of each round, the Amal shuffles the deck.

Dealing starts with the Kem and proceeds clockwise.

Cards are dealt in packets:

1. 5 cards to each player.
2. 4 additional cards to each player.
3. 4 additional cards to each player.

Each player therefore receives exactly 13 cards.

## 5\. Card Visibility and Choosing the Hook

The Kem must choose the Hook **using only the first 5 cards received**.
Once the Kem has received the first 5 cards, the Kem may declare the Hook at any time while the remaining cards continue to be dealt.

The Kem may not see the remaining 8 cards before declaring the Hook.

The Kem's partner may not look at their cards until the Kem has declared the Hook.

The two players on the opposing team may view all 13 of their cards as soon as those cards have been dealt.

After the Kem declares the Hook:

* the Kem may view all 13 cards,
* the Kem's partner may view all 13 cards.

The Kem may choose **any of the four suits** as the Hook, including a suit that does not appear among the Kem's first five cards.

Once declared, the Hook cannot be changed during that round.

## 6\. Starting a Trick

The Kem always leads the first trick of a round.

The lead player plays one card. Each other player then plays one card in clockwise order.

At the end of a trick, exactly four cards are on the table.

## 7\. Following Suit

The first card played determines the lead suit.

If a player holds at least one card of the lead suit, that player **must** play a card of the lead suit.

There is no requirement to play a higher card when following suit.

Example: if 10♥ is led and a player holds both A♥ and 2♥, the player may legally play 2♥.

## 8\. Cutting and Passing

If a player has no card of the lead suit, the player may:

* **Cut** — play a Hook card.
* **Pass** — play a card from a non-Hook suit.

A player who has a Hook card is not required to cut.

If an earlier player has already cut, later players are not required to cut or overtrump.

If the player has neither the lead suit nor a Hook card, the player may play a card from another suit.

## 9\. Determining the Trick Winner

After all four players have played:

* If no Hook card was played, the highest card of the **lead suit** wins.
* Cards of other non-Hook suits cannot win that trick, regardless of rank.
* If one or more Hook cards were played, the highest Hook card wins.

The player who wins the trick leads the next trick.

Therefore, the Kem is guaranteed to lead only the first trick of a round.

## 10\. Viewing the Previous Trick

After a trick ends, its four cards are collected and placed face down next to one of the players on the team that won the trick.

Any player may request to view the **four cards from the immediately previous trick only**, provided the next trick has not yet started.

Older tricks may not be viewed.

Once the next trick starts, the previous trick may no longer be viewed.

## 11\. Winning a Round

Every trick won counts toward the winning player's team.

The first team to win 7 tricks immediately wins the round.

The round ends at that moment even if players still hold unused cards.

A normal round win awards **1 point**.

If the round ends 7–0:

* If the Kem's team wins 7–0, that team receives **2 points**.
* If the non-Kem team wins 7–0, that team receives **3 points**.

## 12\. Roles in the Next Round

If the Kem's team wins the round:

* the Kem remains the Kem,
* the Amal remains the Amal.

If the opposing team wins the round:

* the player immediately to the **left of the current Kem** becomes the new Kem,
* the previous Kem becomes the new Amal.

The Amal is always the player immediately to the right of the Kem.

Teams remain fixed for the entire full game.

Cards are collected, reshuffled, and dealt again for the next round.

The Aces procedure is not repeated.

## 13\. Winning the Full Game

Points accumulate between rounds.

The first team to reach **7 or more points** wins the full game immediately.

A team does not need to land on exactly 7.

Example: a team on 6 points that receives 2 points for a 7–0 round reaches 8 points and wins.

If a new full game begins, the Aces procedure is performed again.

## 14\. Information Privacy

The game depends on private card information.

A digital implementation must ensure that a player cannot access information about cards that the player is not currently allowed to see.

This should be treated as a correctness and security requirement, not merely as a visual UI rule.

For a future multiplayer implementation, hidden card information should not be sent to an unauthorized player's client merely to be visually concealed there.

## 15\. Digital-Product Note

The physical role of the Amal is defined above. The exact user-facing role of the Amal in a digital application is still an open product decision and is tracked in `OPEN\_DECISIONS.md`.

