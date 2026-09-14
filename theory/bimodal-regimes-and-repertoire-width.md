# Bimodal Regimes and Repertoire Width

**Date:** 2026-09-14  
**Status:** active tactics brainstorm

## Trigger

USER_MEMORY from Drew's HEMA sparring history:

Drew remembers a small HEMA group in which Kenneth was the strongest adaptive fighter and teacher; David was highly competent and could nearly fight Kenneth to a draw; Drew was less technically skilled than David but created an unusually awkward matchup through size, reach, commitment, and willingness to accept contact.

David summarized Drew's repertoire as essentially two moves:

> "you have two moves, a really overcommitted zornhau and a very cautious but extremely long range due to those stupid long arms poke."

The important tactical feature is not the literal move count. It is that the two actions occupy opposite tactical regimes.

## Bimodal policy

```text
REGIME A — MAXIMUM MEASURE
long cautious poke
preserve distance
force expensive entry

REGIME B — MAXIMUM COMMITMENT
overcommitted Zornhau
collapse measure
accept contact risk
force the exchange
```

This resembles a bang-bang control analogy: rather than continuously occupying moderate commitment states, the policy spends much of its decision authority at opposite extremes.

Treat the control-theory language as analogy, not a claim that human sparring literally implements a bang-bang controller.

## Core law

> **Repertoire width need not equal decision-space width.**

A fighter, unit, game character, or control system with very few actions can still impose a broad decision problem if those actions dominate different regimes.

So evaluate both:

```text
ACTION COUNT
and
REGIME COVERAGE
```

A narrow repertoire with wide regime coverage can be tactically expensive to answer.

## Matchup nontransitivity

A scalar skill ordering does not fully determine pairwise outcomes.

Useful abstract model:

```text
Kenneth = adaptive / opponent-sensitive policy
David   = broad high-skill conventional policy
Drew    = narrow extreme-state policy
```

Even if David is technically superior to Drew, Drew can still create a difficult matchup if David's preferred middle regime is repeatedly denied or overloaded.

This does not imply the narrow policy is universally stronger. An adaptive opponent may identify the regime switch, exploit recovery, bait commitment, or otherwise restructure the encounter.

## Tactical design implication

When designing doctrine, agents, game characters, or autonomous behaviors, do not ask only:

> How many options does this actor have?

Also ask:

> How many qualitatively different problems can those options force the opponent to solve?

A useful conceptual quantity:

```text
DECISION BURDEN PER ACTION
≈ distinct opponent response regimes / available actions
```

This is a heuristic, not a scientific metric.

## Relation to safe action envelopes

Earlier tactics work emphasized designing systems where imperfect local choices remain useful. Bimodal regime control adds a complementary idea:

- a safe action envelope asks whether local mistakes still contribute;
- regime coverage asks whether a small action set still controls qualitatively different parts of the state space.

Robust systems may benefit from both:

```text
few actions
+ broad regime coverage
+ graceful degradation inside each regime
```

## Compact laws

> **Few actions are enough when they control different regimes.**

> **Technical breadth and matchup pressure are separate variables.**

> **A narrow policy can be strategically expensive to answer when it denies the opponent a comfortable middle.**

Status: strong cross-domain tactics candidate; derived from USER_MEMORY and should be tested against additional examples before promotion.
